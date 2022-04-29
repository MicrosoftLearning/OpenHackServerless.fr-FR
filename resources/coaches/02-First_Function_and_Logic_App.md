---
ms.openlocfilehash: 4e45123a01531ded30f70c3a32249b252149cab4
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813650"
---
# <a name="create-your-first-serverless-function--workflow"></a>Créer votre première fonction et votre premier workflow serverless

## <a name="happy-path"></a>Chemin idéal

Choisissez l’une de ces trois options :

* Utiliser la dernière version de Visual Studio avec la dernière extension Functions et Webjobs pour créer l’application de fonction et les fonctions, les tester localement et les publier sur Azure

* Utiliser Visual Studio Code avec la dernière extension Azure Functions pour créer l’application de fonction et les fonctions, les tester localement et les publier sur Azure

* Utiliser l’IDE préféré (Java/Python) avec la dernière version d’Azure Functions Core Tools et d’Azure CLI pour créer l’application de fonction et les fonctions, les tester localement et les publier sur Azure

## <a name="python-developer-notes"></a>Remarques à l’attention des développeurs Python

* Les utilisateurs de VS Code peuvent utiliser l’[extension Functions](https://docs.microsoft.com/azure/python/tutorial-vs-code-serverless-python-05) pour déployer l’application de fonction, les développeurs ne pourront pas voir ce qui se passe pendant le déploiement. Encouragez les développeurs à utiliser les [outils Azure Function Core](https://docs.microsoft.com/azure/azure-functions/functions-reference-python#publishing-to-azure) pour le déploiement. Ils bénéficieront ainsi d’une plus grande visibilité sur la build à distance dans le cloud.

## <a name="coaches-notes"></a>Remarques à l’attention des instructeurs

* C’est le seul défi qui a des exigences individuelles ; pour tous les autres, les participants devront travailler ensemble ou créer des sous-équipes, puis partager les leçons et fusionner le travail.

* Si l’équipe comprend un membre spécialisé dans l’infrastructure, ce dernier doit se concentrer sur les outils IaC et le déploiement d’une fonction Azure et d’une application logique pendant ce temps. De cette façon, l’équipe sera sur la bonne voie pour aider les développeurs d’applications et les membres se spécialisant dans l’infrastructure à travailler ensemble lors de défis ultérieurs.

* Aidez et guidez chaque membre de l’équipe tout au long du processus d’installation (Visual Studio, VS Code, dépendances, etc.) et répondez à toutes leurs questions sur Functions et Logic Apps.

* Passez un peu de temps à expliquer que ce défi porte principalement sur le réglage de niveau (défi 0, essentiellement), et présentez aux participants Functions et Logic Apps. Le reste des défis leur donnera une meilleure idée du concept serverless d’un point de vue métier et technique.

* Vérifiez que le résultat est correct et que les participants appellent la fonction avec GET et l’application logique avec POST.

* N’hésitez pas à leur expliquer les différentes options permettant de créer une fonction localement, orientez-les si possible vers VS Code et VS, à moins qu’ils ne souhaitent vraiment essayer quelque chose qui ne figure pas dans C# ou dans Node (comme Java ou Python).

* Vérifiez qu’ils disposent des dernières versions de VS et des extensions.

* VS Code pose problème si vous n’avez pas la bonne version du runtime des fonctions ou de .NET Core. Pour remédier à cela, désinstallez .NET Core en totalité et installez le dernier SDK, et installez également le dernier runtime.
* Si vous utilisez l’extension Logic Apps dans VS Code, notez que le concepteur est _en lecture seule_.  La [page d’extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-logicapps) de VS Code indique (au moyen d’un GIF animé) que le concepteur est en lecture seule.  Pour une expérience d’édition graphique complète, utilisez Visual Studio ou le portail Azure.

* Faites attention lors de l’installation de Functions Core Tools avec Chocolatey. Il semble qu’il installe la version 32 bits contenant un bogue.

* Si vous utilisez Node avec des fonctions, vérifiez que la version de Node dans les paramètres de l’application pour la fonction est définie sur 8.4.0 au minimum.  Dans l’idéal, cela correspond à la version actuelle de Node (par exemple, v12).

* Packages d’exécution et NuGet qui fonctionnent bien :

    Produit | Version
    ------- | -------
    Visual Studio | 16.3.2
    Extension Functions et WebJobs pour VS | V15.0.40502
    SDK .NET Core | [.NET Core](https://dotnet.microsoft.com/download/visual-studio-sdks)
    Function Core Tools | 2.7.1633
    Autres bibliothèques NuGet | ...
    Microsoft.ApplicationInsights | 2.11.0
    Microsoft.NET.Sdk.Functions | 1.0.28
    CsvHelper | 12.1.2
    Microsoft.Azure.WebJobs.Extension.CosmosDB | 3.0.3
    Microsoft.Azure.WebJobs.Extensions.DurableTask | 1.8.2
    Microsoft.Azure.WebJobs.Extensions.EventHubs | 3.0.3

## <a name="why-azure-functions-and-logic-apps"></a>Pourquoi Azure Functions et Logic Apps

### <a name="azure-functions"></a>Azure Functions

* Les fonctions Azure permettent à vos équipes d’écrire moins de code, de maintenir une infrastructure moins importante et de réduire les coûts.
* Les fonctions Azure sont légères et autonomes.  Les fonctions permettent de diviser facilement des applications monolithiques et de réduire vos délais/durées de cycle. Vos équipes peuvent donc faire passer le code en production de manière beaucoup plus rapide et efficace.
* Azure Functions peut tirer parti des [conteneurs Docker personnalisés](https://docs.microsoft.com/fr-fr/azure/azure-functions/functions-create-function-linux-custom-image) pour respecter des exigences spécifiques liées à une version de langage ou à une dépendance qui ne sont pas fournies par l’image intégrée.

    > **Informations supplémentaires** Le service Azure Functions se compose de deux composants clés : un runtime et un contrôleur de mise à l’échelle. Le runtime Functions s’exécute et exécute votre code. Le runtime inclut une logique sur le déclenchement, la consignation et la gestion des exécutions de fonction. Le runtime Azure Functions peut s’exécuter n’importe où. L’autre composant est un contrôleur d’échelle. Le contrôleur d’échelle supervise le taux d’événements qui ciblent votre fonction et met proactivement à l’échelle le nombre d’instances exécutant votre application.

* Vous pouvez déployer n’importe quelle application de fonction sur un [cluster Kubernetes exécutant KEDA](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).

### <a name="azure-logic-apps"></a>Azure Logic Apps

* Grâce à plus de 200 connecteurs, les applications logiques peuvent se connecter à presque n’importe quoi être déclenchées à volonté, selon une planification ou en réponse à un événement.
* Les applications logiques sont faciles à utiliser, avec des workflows qui peuvent être créés en quelques configurations seulement par glisser-déplacer dans un éditeur puissant, ce qui permet à votre équipe d’orchestrer rapidement et facilement des logiques complexes.

## <a name="infrastruture-notes"></a>Notes sur l’infrastructure

* De nombreux modèles de démarrage rapide Azure incluent des versions Bicep dans les dépôts GitHub.
* Nous vous recommandons vivement d’effectuer cette tâche en parallèle une fois les efforts de développement accomplis pour réussir le défi principal. L’exécution séquentielle de contenu supplémentaire peut compromettre la capacité de l’équipe à relever le nombre minimum de défis.
