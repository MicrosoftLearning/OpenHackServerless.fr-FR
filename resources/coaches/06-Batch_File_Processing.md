---
ms.openlocfilehash: 4731750397d38964f248b031242f13a6027c0497
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813637"
---
# <a name="process-distributor-order-batch-files"></a>Traiter les fichiers de commandes par lots du distributeur

## <a name="progress-diagram"></a>Diagramme de progression

![Diagramme de progression du traitement des fichiers de commandes par lots du distributeur](https://serverlessoh.azureedge.net/public/order-batch-files-progress-diagram.jpg)

## <a name="happy-path"></a>Façon de procéder idéale

Utilisez l’une des options suivantes :

* Déclencheur Event Grid vers une fonction Azure qui interroge si deux fichiers s’affichent en même temps, cela peut provoquer un problème de lecture des fichiers en même temps à partir du stockage. Créez un fichier supplémentaire pour chaque lot à l’intérieur de la fonction et placez un bail sur le fichier à l’intérieur du code de la fonction, puis ajoutez une nouvelle tentative lorsqu’il existe déjà un bail sur le fichier pour éviter cela
* Event Grid vers une fonction Azure qui charge le contenu d’un fichier dans une base de données SQL/CosmosDB et une fonction séparée qui vérifie de temps en temps s’il n’y a pas de contenu pour les trois, puis les fusionne dans une collection Cosmos distincte
* Event Grid vers Durable Functions qui crée des sous-orchestrateurs pour chaque lot lorsque le premier fichier arrive, puis RaiseEventAsync pour les autres. Le sous-orchestrateur exécute une fonction d’activité avec les détails des trois fichiers, et la fonction d’activité analyse et insère les données (une par commande) dans Cosmos  
* Utilisez Logic Apps avec le déclencheur de lot (une application logique avec un Event Grid qui envoie des informations sur les fichiers à une seconde application logique qui a le déclencheur de lots configuré pour se libérer après 3 messages) et une fonction Azure appelée par l’application logique déclenchée par le lot qui gère le chargement des fichiers, l’analyse et l’insertion dans Cosmos

## <a name="coaches-notes"></a>Remarques à l’attention des instructeurs

* Il est possible que vous ayez besoin de plus de mains pour les aider avec leur approche.

* Lors de la publication pour inscrire le compte de stockage, l’équipe doit utiliser un numéro de table unique.  L’API pour la publication est disponible [ici](https://serverlessohmanagementapi.trafficmanager.net/api/definition).  Il est important de savoir que le numéro de table de l’équipe est unique, par exemple seattle-table-1 ou london-table-8.  Si les numéros de table de l’équipe ne sont pas attribués, encouragez les équipes à utiliser un nom de table unique et à les noter, car elles en auront besoin dans les prochaines étapes.  N’oubliez pas que cette opération envoie une grande quantité de trafic à leur compte de stockage pendant 48 à 72 heures.  Indiquez-leur de ne pas interrompre la connexion pendant que le OpenHack est actif, car elles doivent garder l’inscription active pour les futurs défis et, si elles interrompent la connexion, elles sont désinscrites.

>Remarque : les comptes d’étudiants seront également désinscrits si plus de 72 heures (3 jours) se sont écoulés depuis l’inscription.  Si l’étudiant atteint ce seuil, faites en sorte qu’il inscrive à nouveau son compte de stockage pour redémarrer le traitement.

* L’application *serverlessohmanagementapi* est sensible à la casse. Aussi, tous les paramètres du corps doivent correspondre exactement pour chaque appel, et il ne peut y avoir aucune variation de casse pour les noms de fichiers et les liens vers les fichiers dans le stockage Azure.  Consultez la documentation de Swagger pour connaître les spécifications de composition de corps exactes pour chaque méthode.

* Durable Functions dans Node.js est pris en charge uniquement pour la version 2.x du runtime Azure Functions. Nécessite la version 1.7.0 ou ultérieure de l’extension Durable Functions.

* Python et Java ne prennent actuellement pas en charge les fonctions durables. Ces équipes devront utiliser d’autres méthodes pour mener à bien ce défi.

* Si le conteneur de compte de stockage de l’équipe est privé, les URL fournies au point de terminaison /order/combineOrderContent doivent contenir un jeton SAP.

* La liaison de sortie Cosmos DB n’autorise pas la gestion des exceptions. Selon l’approche de déclenchement utilisée par l’équipe, cela se manifeste de différentes façons lorsque des erreurs se produisent lors de l’enregistrement dans la base de données. Demandez à l’équipe de discuter de cela et de différentes façons de traiter le problème.

* Lorsque la table CosmosDB est inscrite, une clé de partition est utilisée, par exemple « ID », « FileName » ou « filename ».  En supposant que la clé de partition était « FileName », le connecteur d’application logique doit se connecter et suivre les instructions d’installation suivantes :  

    * DatabaseID : sélectionné à partir de la connexion  
    * CollectionID : sélectionné à partir de la connexion  
    * Document : utilisez des accolades gauche et droite, puis chaque champ entre guillemets avec chaque valeur associée, séparés par des virgules.  **N’oubliez pas d’inclure votre clé de partition et sa valeur dans ce document.**  

    * Ajoutez un nouveau paramètre, puis sélectionnez « Valeur de clé de partition ».  Dans la zone de texte résultante, ajoutez la valeur de la clé de partition entre guillemets (pour qu’elle corresponde au document ci-dessus).  Par exemple, le côté gauche serait un texte non modifiable indiquant « Valeur de clé de partition » et il y aurait une zone de texte sur la droite pour entrer des informations.  Dans cette zone de texte, ajoutez la **valeur** de la clé de partition entre guillemets, par exemple : **« myorderfile.xls »** .  Étant donné que la clé est susceptible de changer par exécution, encouragez l’utilisation d’une variable pour stocker la valeur de la clé de partition.  

* Lors de l’écriture dans CosmosDB dans Logic Apps, le paramètre de clé de partition doit être ajouté en tant que nouveau paramètre au connecteur Mettre à jour ou créer le document CosmosDB. La valeur doit être placée entre guillemets.  La partition doit également être envoyée en tant que partie du corps du document à créer.  Si vous ne voyez pas la valeur de votre clé de partition dans le document et dans le paramètre de valeur de clé de partition, la création ou mise à jour de document ne fonctionnera pas.   En outre, vous pouvez passer en revue le JSON du concepteur et vérifier que « x-ms-documentdb-raw-partitionkey » est défini avec une valeur.  

* Si vous recevez une erreur indiquant que le fournisseur de ressources Microsoft.EventGrid n’a pas été inscrit pour l’abonnement du participant, veillez à suivre les étapes d’inscription du fournisseur de ressources EventGrid dans [Activer le fournisseur de ressources Event Grid](https://docs.microsoft.com/fr-fr/azure/event-grid/custom-event-quickstart-portal).  

## <a name="why-azure-functions-azure-logic-apps-azure-event-grid-and-azure-storage"></a>Pourquoi Azure Functions, Azure Logic Apps, Azure Event Grid et Stockage Azure

### <a name="azure-functions"></a>Azure Functions

* Les fonctions Azure permettent à vos équipes d’écrire moins de code, de maintenir une infrastructure moins importante et de réduire les coûts.
* Les fonctions Azure sont légères et autonomes.  Les fonctions permettent de diviser facilement des applications monolithiques et de réduire vos délais/durées de cycle. Vos équipes peuvent donc faire passer le code en production de manière beaucoup plus rapide et efficace.

### <a name="azure-logic-apps"></a>Azure Logic Apps

* Grâce à plus de 200 connecteurs, les applications logiques peuvent se connecter à presque n’importe quoi, être déclenchées à volonté, selon une planification ou en réponse à un événement.
* Les applications logiques sont faciles à utiliser, avec des workflows qui peuvent être créés en quelques configurations seulement par glisser-déplacer dans un éditeur puissant, ce qui permet à votre équipe d’orchestrer rapidement et facilement des logiques complexes.

### <a name="azure-event-grid"></a>Azure Event Grid

* Créer facilement une application avec des architectures basées sur les événements
* Routez des événements spécifiques vers des points de terminaison différents, multidiffusez vers plusieurs points de terminaison et vérifiez que vos événements sont délivrés de façon fiable.

### <a name="azure-storage"></a>Stockage Azure

* Le stockage est durable, scalable et hautement disponible. La redondance garantit la sécurité de vos données en cas de défaillances matérielles temporaires, tout en étant massivement scalable pour répondre aux besoins des applications actuelles
* Le stockage est sécurisé, avec un chiffrement intégré et un contrôle d’accès affiné pour configurer un accès particulier et précis pour que les utilisateurs n’exposent que les données de stockage auxquelles ils doivent être autorisés à accéder.
