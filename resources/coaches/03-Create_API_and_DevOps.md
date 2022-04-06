---
ms.openlocfilehash: 878b8fc0072cee4d28adca8898cf38c90ba06b90
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813656"
---
# <a name="finish-the-ice-cream-ratings-api"></a>Terminer l’API Ice Cream Ratings

## <a name="progress-diagram"></a>Diagramme de progression

![Diagramme de progression de l’API Ratings](https://serverlessoh.azureedge.net/public/ratings-api-progress-diagram.jpg)

## <a name="happy-path"></a>Chemin idéal

* Placer le code dans GitHub, Azure DevOps ou d’autres sources Git
* Créer une application de fonction Azure et déployer en continu sur celle-ci
* Utiliser Azure Functions avec Cosmos DB, utiliser les liaisons d’entrée et de sortie des fonctions
* Possibilité également d’utiliser les kits SDK clients CosmosDB, non associés aux liaisons
* Pour Node en particulier, la combinaison API CosmosDB Mongo + Mongoose fonctionne bien

## <a name="coaches-notes"></a>Remarques à l’attention des instructeurs

* À la fin de ce défi, vérifiez que votre équipe dispose d’une configuration propice à la collaboration et d’un plan détaillant comment travailler ensemble. Ce plan doit indiquer comment l’équipe va collaborer et où elle va mettre tout le code.
* Dans ce contexte, vous pouvez essayer d’activer Visual Studio Live Share.
* Demandez aux membres de l’équipe de discuter de la façon dont ils peuvent se séparer et se retrouver pour partager leurs connaissances.
* Veillez à tester leur fonction CreateRating en utilisant l’exemple de site web fourni dans le défi. Vous vous assurerez ainsi qu’ils utilisent le bon format JSON qui sera repris dans les défis ultérieurs.
* Demandez-leur d’utiliser le plan Consommation (serverless réel).
* Quand vous essayez d’installer des extensions et que vous obtenez une erreur « dotnet-add introuvable », cela est dû à l’ancienne version de .NET Core. L’installation de la dernière version de .NET devrait résoudre ce problème.
* Pour GetRatings, indiquez userId dans la route et utilisez-le dans le paramètre SQLQuery (au lieu de la chaîne de requête qui ne fonctionne pas).
* Cosmos DB nécessite la définition d’une clé de partition lors de la création du conteneur. En tant qu’instructeur, discutez avec l’équipe du [choix d’une clé de partition](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview#choose-partitionkey) et de l’impact qu’elle peut avoir sur les requêtes. Par exemple, des clés de partition potentielles pour ce défi peuvent être ```userId``` ou ```productId```.
* Utilisateurs à utiliser pour l’envoi d’évaluations :

User Id | User Name | Nom complet
--------| --------- | ---------
cc5581ff-6be1-4418-a8d8-55a29c24b995 | garry.thornburg | Garry Thornburg
6dd3bb49-a5be-41ca-9dac-3b995450f2db | kayla.cobb | Kayla Cobb
ed414804-ed3d-4ec3-a283-f94ee86f3e23 | edna.waters | Edna Waters
d1f80b77-040f-4ec8-a833-90b18da70337 | chester.furlong | Chester Furlong
cc20a6fb-a91f-4192-874d-132493685376 | doreen.riddle | Doreen Riddle

### <a name="storage-notes"></a>Remarques sur le stockage

* CosmosDB
    * Veillez à ce que l’équipe discute de l’obligation d’utiliser une clé de partition pour la collection.
    * L’utilisation de la propriété id de la liaison ne fonctionne pas sans l’utilisation de la propriété de clé de partition. La fonction GetRating nécessite l’utilisation de la requête SQL.

### <a name="node-notes"></a>Remarques sur Node

* Vérifiez le paramètre d’application WEBSITE_NODE_DEFAULT_VERSION. Selon la version des applications de fonction utilisées, vous devrez peut-être mettre à jour la version de Node dans le portail. Pour voir les runtimes de langage pris en charge, reportez-vous au [tableau des langages](https://docs.microsoft.com/azure/azure-functions/functions-versions#languages).
* Pour activer le débogage dans Visual Studio, vous devez ajouter "NODE_OPTIONS": "--inspect=5858" dans le fichier de paramètres locaux.

### <a name="devops-notes"></a>Notes sur DevOps

* L’équipe peut créer un compte AzDo en utilisant les informations d’identification fournies par le portail Opgility.
* Si vous utilisez Azure DevOps pour le code source, mais que vous souhaitez toujours vous y connecter à partir des options de déploiement de Functions, vous devez effectuer la configuration à partir d’une organisation pour laquelle votre connexion a le statut de propriétaire. Pour cela, la configuration du déploiement fait référence à [ces instructions](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization?view=azure-devops).
    * Les plans App Service Linux n’ont pas de service Kudu disponible et ne peuvent donc pas utiliser cette option pour la configuration du déploiement.
* Pour connaître les options de déploiement disponibles en fonction des sélections de plan App Service, consultez [Disponibilité des technologies de déploiement](https://docs.microsoft.com/azure/azure-functions/functions-deployment-technologies#deployment-technology-availability).
* Les utilisateurs Mac et Linux devront soit créer un compte de stockage dans Azure pour connecter leur environnement de développement local, soit installer Azurite v2. [Azurite v3 ne fonctionne pas](https://github.com/mydiemho/blob-trigger-sample), mais les utilisateurs Windows peuvent utiliser l’Émulateur de stockage.

## <a name="why-devops-and-azure-functions"></a>Pourquoi DevOps et Azure Functions

* DevOps permet d’automatiser le déploiement manuel et la publication de code afin de minimiser les erreurs humaines.
* Azure Functions vous permet d’exécuter des fragments de code sans provisionner un environnement d’hébergement entier.

## <a name="infrastruture-notes"></a>Notes sur l’infrastructure

* De nombreux modèles de démarrage rapide Azure incluent des versions Bicep dans les dépôts GitHub.
