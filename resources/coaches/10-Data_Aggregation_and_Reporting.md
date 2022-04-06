---
ms.openlocfilehash: 5109c8ffa5df36a921e6c02108b2b3a59c877914
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813644"
---
# <a name="putting-it-all-together"></a>Récapitulatif

## <a name="progress-diagram"></a>Diagramme de progression

![Diagramme de progression final](https://serverlessoh.azureedge.net/public/final-progress-diagram.jpg)

## <a name="happy-path"></a>Chemin idéal

* Modifier le flux et les fonctions à transférer vers un nouveau hub d’événements ou modifier la fonction CreateRating avec une deuxième liaison de sortie au hub d’événements
* Créer une solution Stream Analytics avec les hubs d’événements POS d’origine et un nouveau hub d’événements comme entrée
* Écrivez une ou plusieurs requêtes Stream Insight, puis envoyez-les à Cosmos ou à Power BI. Exemple :

```sql
WITH
Products AS (
    Select *
    from testdata as t
    CROSS APPLY GetArrayElements(t.items) AS flat
)

SELECT System.TimeStamp AS WindowEnd,
        T.header.locationname,
        flat.ArrayValue.productname,
        sum(flat.ArrayValue.totalcost) as totalCost,
        count(1) as countUnits
INTO prodPowerBi
FROM Products
GROUP BY flat.ArrayValue.productname, T.header.locationname, TumblingWindow(minute, 5)
```

## <a name="why-azure-functions-and-stream-analytics"></a>Pourquoi Azure Functions et Stream Analytics

### <a name="azure-functions"></a>Azure Functions

* Les fonctions Azure permettent à vos équipes d’écrire moins de code, de maintenir une infrastructure moins importante et de réduire les coûts.
* Les fonctions Azure sont légères et autonomes.  Les fonctions permettent de diviser facilement des applications monolithiques et de réduire vos délais/durées de cycle. Vos équipes peuvent donc faire passer le code en production de manière beaucoup plus rapide et efficace.

### <a name="azure-stream-analytics"></a>Azure Stream Analytics

* Créer facilement un pipeline d’analytique de bout en bout avec des requêtes pour convertir et filtrer les données
* Les fonctionnalités de Machine Learning intégrées offrent des solutions avancées
