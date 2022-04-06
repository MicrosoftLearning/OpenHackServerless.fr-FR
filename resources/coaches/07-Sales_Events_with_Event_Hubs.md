---
ms.openlocfilehash: 4b47af864a11eb709d6bc2971cc25e0c804666bc
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813645"
---
# <a name="process-pos-sales-events"></a>Traiter les événements de vente du point de vente

## <a name="progress-diagram"></a>Diagramme de progression

![Diagramme de progression du traitement des événements de vente du point de vente](https://serverlessoh.azureedge.net/public/process-pos-sales-event-progress-diagram.jpg)

## <a name="happy-path"></a>Chemin idéal

* Déclencheur Event Hub pour fonction Azure
* Déclencheur de fonction modifié pour recevoir un lot (string[] en C#)
* Host.json modifié pour répondre aux exigences
* Requête App Insights pour le nombre d’instances de rôle par minute

## <a name="coaches-notes"></a>Remarques à l’attention des instructeurs

* Vous devez définir "cardinality": "many" pour les fonctions Azure en JavaScript afin d’activer les réceptions par lots.

* Lors de la publication pour inscrire le hub d’événements, l’équipe doit utiliser un numéro de table unique.  L’API pour la publication est disponible [ici](https://serverlessohmanagementapi.trafficmanager.net/api/definition).  Il est important de savoir que le numéro de table de l’équipe est unique, par exemple seattle-table-1 ou london-table-8.  Il doit s’agir du même numéro de table que celui utilisé par l’équipe lors du défi précédent. Il doit être unique par table/équipe.  En outre, si l’équipe ne parvient pas à inscrire son compte de stockage, il est probable que le hub d’événements ne s’inscrive pas.  Veillez à informer les membres de l’équipe qu’ils doivent inscrire leur compte de stockage.  Certaines personnes ignorent ou diffèrent cette étape en raison de la quantité de trafic qu’elle génère sur le compte de stockage (ou déconnectent le compte de stockage, ce qui interrompt également le flux de ce hack ouvert car il désinscrit leur table).

* Soyez prêt à discuter de l’impact de la définition des paramètres suivants pour l’application de fonction : ```maxBatchSize``` = 64 et ```prefetchCount``` = 256.  Il n’y a rien de spécial à propos de ces chiffres.  Ils constituent un point de départ.  Les participants doivent les utiliser et observer les performances et la scalabilité. En tant qu’instructeur, vous devez aborder le mode de traitement des messages dans le lot, y compris la gestion des erreurs et des exceptions.  

    Informations supplémentaires sur les fonctions :

    * [Exemple de fichier host.json](https://docs.microsoft.com/en-us/azure/azure-functions/functions-host-json)

    * [Host.json - Liaisons Functions à Event Hubs](https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-event-hubs-trigger?tabs=csharp#hostjson-properties)  

        >Remarque : Les fonctions sur la version 1 utilisent une configuration différente, mais cela ne devrait pas poser problème pour les nouveaux développements.

    * [Liaison Functions à Event Hubs](https://docs.microsoft.com/azure/azure-functions/functions-bindings-event-hubs)

    * [Bonnes pratiques relatives à Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/functions-best-practices)  

    * [Azure Functions et Event Hubs : optimisation pour le débit](https://medium.com/@iizotov/azure-functions-and-event-hubs-optimising-for-throughput-549c7acd2b75)  

    * [Fonctionnement de l’hôte de processeur d’événements dans Azure Event Hubs](https://channel9.msdn.com/Shows/On-NET/Understanding-the-Event-Processor-Host-in-Azure-Event-Hubs)

* Il est préférable que les applications de fonction soient associées à un plan de consommation, et non à un plan App Service (ce qui facilite la démonstration de la mise à l’échelle automatique). Sinon, montrez aux participants la configuration de la mise à l’échelle automatique pour un plan App Service avec une mesure de scale-up peu élevée (par exemple, 10 % du processeur).

* Invitez le participant à examiner le nombre de serveurs **avant** d’activer le mode boost (afin qu’il puisse comparer la mise à l’échelle par défaut et la mise à l’échelle des fonctions).

* Pour obtenir le nombre de serveurs actifs pour une fonction spécifique, utilisez soit la vue Métriques temps réel Application Insights, soit une requête Log Analytics telle que la suivante :

    ```sql
    requests
    | where name == "ProcessSalesEventBatch"
    | summarize count() by cloud_RoleInstance  
    | summarize count()
    ```

* Si vous utilisez une application de fonction Python, les métriques temps réel **n’indiquent pas** le nombre correct de serveurs après le scale-out de l’application de fonction (la valeur 1 est toujours affichée). Il s’agit d’un [problème connu](https://github.com/Azure/azure-functions-python-worker/issues/35). Au lieu de cela, récupérez le nombre d’instances actives en utilisant une requête Log Analytics telle que la suivante :

    ```sql
    requests
    | where operation_Name  == ""
    | distinct cloud_RoleInstance
    | count
    ```

* Examinez la configuration dans host.json pour valider le nombre de lots et de prérécupérations.

* Si vous utilisez Cosmos DB, vérifiez que les RU sont suffisamment élevées pour gérer le débit (sinon, les demandes peuvent être limitées).
    * [Unités de requête dans Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/request-units)
    * [Estimer le nombre d’unités de requête/seconde à l’aide du planificateur de capacité Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/estimate-ru-with-capacity-planner)

## <a name="why-event-hub-azure-functions-and-azure-application-insights"></a>Pourquoi Event Hub, Azure Functions et Azure Application Insights

### <a name="event-hub"></a>Event Hub

* Recevoir et traiter des millions d’événements par seconde
* Transformer un magasin en utilisant l’analytique en temps réel ou des adaptateurs de traitement par lot/stockage

### <a name="azure-functions"></a>Azure Functions

* Les fonctions Azure permettent à vos équipes d’écrire moins de code, de maintenir une infrastructure moins importante et de réduire les coûts.
* Les fonctions Azure sont légères et autonomes.  Les fonctions permettent de diviser facilement des applications monolithiques et de réduire vos délais/durées de cycle. Vos équipes peuvent donc faire passer le code en production de manière beaucoup plus rapide et efficace.

### <a name="azure-application-insights"></a>Azure Application Insights

* Service APM (Application Performance Management) extensible permettant de monitorer les applications en temps réel
* Détecter automatiquement les anomalies liées aux performances, tirer profit d’outils d’analytique puissants et améliorer en permanence les performances et la convivialité
