---
ms.openlocfilehash: c6694e2c6cf365c501015b03c02036be37ce1e1d
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813655"
---
# <a name="alerting-and-notification"></a>Alertes et notifications

## <a name="progress-diagram"></a>Diagramme de progression

![Diagramme de progression des alertes et des notifications](https://serverlessoh.azureedge.net/public/alerting-and-notification-progress-diagram.jpg)

## <a name="happy-path"></a>Chemin idéal

* Modifier la fonction CreateRating existante et placer userNotes dans, au choix :
    * Appels de l’API Cognitive Services Analyse de texte
    * Bibliothèque [TextBlob](https://textblob.readthedocs.io/en/dev/index.html#) avec des fonctions Python
* Créer une télémétrie personnalisée pour écrire dans la même instance App Insights que la fonction chaque fois qu’il y a une mauvaise évaluation
* Utiliser la fonctionnalité Alertes de journal pour Application Insights afin de générer une alerte et un e-mail lorsque le seuil est atteint

[Guide pratique - Analyse des sentiments](https://docs.microsoft.com/fr-fr/azure/cognitive-services/text-analytics/how-tos/text-analytics-how-to-sentiment-analysis?tabs=version-3).  

## <a name="why-cognitive-services-azure-functions-azure-logic-apps-and-application-insights"></a>Pourquoi Cognitive Services, Azure Functions, Azure Logic Apps et Application Insights

### <a name="cognitive-services---text-analyticssentiment-analysis"></a>Cognitive Services - Analyse de texte/Analyse des sentiments

* Analyser le texte non structuré avec le traitement du langage naturel (NLP) pour mieux comprendre les opinions des clients
* Identifier les phrases clés, classifier la terminologie et évaluer dans toutes les langues

### <a name="azure-functions"></a>Azure Functions

* Les fonctions Azure permettent à vos équipes d’écrire moins de code, de maintenir une infrastructure moins importante et de réduire les coûts.
* Les fonctions Azure sont légères et autonomes.  Les fonctions permettent de diviser facilement des applications monolithiques et de réduire vos délais/durées de cycle. Vos équipes peuvent donc faire passer le code en production de manière beaucoup plus rapide et efficace.

### <a name="azure-logic-apps"></a>Azure Logic Apps

* Grâce à plus de 200 connecteurs, les applications logiques peuvent se connecter à presque n’importe quoi être déclenchées à volonté, selon une planification ou en réponse à un événement.
* Les applications logiques sont faciles à utiliser, avec des workflows qui peuvent être créés en quelques configurations seulement par glisser-déplacer dans un éditeur puissant, ce qui permet à votre équipe d’orchestrer rapidement et facilement des logiques complexes.

### <a name="application-insights"></a>Application Insights  

* Les alertes permettent de notifier rapidement les parties intéressées d’un événement ou d’un éventuel temps d’arrêt du service.
* Service APM (Application Performance Management) extensible permettant de monitorer les applications en temps réel
* Détecter automatiquement les anomalies liées aux performances, tirer profit d’outils d’analytique puissants et améliorer en permanence les performances et la convivialité
