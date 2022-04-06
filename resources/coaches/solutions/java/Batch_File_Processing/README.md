---
ms.openlocfilehash: 57d978f77fe641da42b91c80c1a365085e522427
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813658"
---
# <a name="batch-file-processing-solution"></a>Solution de traitement des fichiers par lots

Cet exemple est en lien avec la résolution du défi sur le traitement des fichiers par lots de la façon suivante.

## <a name="event-grid-subscription"></a>Abonnement Event Grid

Un abonnement Event Grid est utilisé sur l’événement de création de blob du compte de stockage pour déclencher la fonction « GridTrigger.java ». Cette fonction analyse le chemin d’accès du fichier et fait deux choses avec ces informations.

1. Elle crée un enregistrement de table de stockage avec la clé de partition égale à la première partie du chemin d’accès et la clé de ligne comme deuxième partie du chemin d’accès.
2. Elle crée un message de file d’attente de stockage dans la file d’attente des « éléments reçus » du même compte de stockage avec les mêmes données stockées dans la table.

## <a name="received-queue-message"></a>Message de file d’attente des éléments reçus

ReceivedQueueTrigger.java est déclenché à partir du message de file d’attente créé précédemment. Cette fonction interroge la table utilisée dans la fonction précédente pour voir s’il existe trois fichiers avec la même clé de partition que le message reçu. Si c’est le cas, elle crée un message dans la file d’attente « des éléments par lots » avec les détails des 3 fichiers.

## <a name="batched-queue-message"></a>Message de file d’attente par lots

La fonction BatchQueueTrigger.java est déclenchée à partir du message créé précédemment. Elle utilise des liaisons d’entrée de blob pour lire les données à partir des trois fichiers blob et transformer le contenu au format JSON.
