---
ms.openlocfilehash: 902d75e6c4dc819c0bcfbbbbb5b5acbcf1d8d488
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813687"
---
# <a name="high-availability"></a>Haute disponibilité

## <a name="progress-diagram"></a>Diagramme de progression

![Diagramme de progression final](https://serverlessoh.azureedge.net/public/final-progress-diagram.jpg)

## <a name="happy-path"></a>Chemin idéal

* Modifier CosmosDB avec plusieurs maîtres ou au moins la géoréplication avec lecture secondaire dans une deuxième région
* Déployer le même code de fonction dans une deuxième région
* Ajouter Traffic Manager devant eux

## <a name="why-cosmos-db"></a>Pourquoi Cosmos DB

### <a name="cosmos-db"></a>Cosmos DB

* Hautement scalable et distribué à l’échelle mondiale, il offre une disponibilité, un débit et une redondance élevés.
* Avec des temps de réponse courts de l’ordre de la milliseconde, il permet aux applications d’obtenir rapidement des informations et de répondre, augmentant ainsi la satisfaction des utilisateurs tout en maintenant des résultats précis.
