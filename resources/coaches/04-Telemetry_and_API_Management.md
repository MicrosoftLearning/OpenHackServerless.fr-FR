---
ms.openlocfilehash: 50b7e0a11a146df5e15ded07704b5120de5b9caa
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813652"
---
# <a name="system-telemetry-and-api-management"></a>Télémétrie système et Gestion des API

## <a name="progress-diagram"></a>Diagramme de progression

![Diagramme de progression de la télémétrie système et de Gestion des API](https://serverlessoh.azureedge.net/public/system-telemetry-and-api-management-progress-diagram.jpg)

## <a name="happy-path"></a>Chemin idéal

### <a name="for-telemetry"></a>Pour la télémétrie

Activez App Insights, puis exécutez la requête fournie dans le répertoire de solutions dans App Insights Analytics :

### <a name="for-api-management"></a>Pour la Gestion des API

* Essayez d’orienter les participants vers Gestion des API. Les fonctionnalités que vous souhaitez exploiter incluent :
    * Proxy inversé
    * Groupes de produits
    * Stratégies de limite de débit
    > L’équipe peut définir des limites de débit trop restrictives pour les tests manuels. Veillez à ce que les chiffres donnés dans le défi soient respectés. À l’origine, nos limites étaient trop restrictives.
* L’équipe peut importer initialement l’intégralité de la fonction dans Gestion des API. Cela convient pour l’apprentissage, mais ce n’est pas suffisant pour atteindre les critères de réussite du défi. Vous devrez peut-être demander aux participants d’importer les API de fonction individuelles afin qu’ils les placent dans les bons groupes de produits.

## <a name="coaches-notes"></a>Remarques à l’attention des instructeurs

* Expliquez à votre équipe les différences entre Gestion des API et Proxies.
* APIM n’accepte pas l’adresse e-mail avec le domaine « onmicrosoft.com » comme adresse e-mail de l’administrateur. L’équipe doit utiliser une adresse e-mail valide dans ce champ.
* Indiquez aux membres de l’équipe la durée de déploiement d’une référence SKU non-Consommation. S’ils veulent suivre cette voie, demandez-leur de créer le compte dès que possible. Sinon, la référence SKU Consommation est beaucoup plus rapide à déployer et contient les fonctionnalités nécessaires pour relever le défi.
* Pour les participants se concentrant sur l’infrastructure, expliquez-leur que le déplacement de tous les paramètres et de la configuration APIM vers IaC peut ne pas être souhaitable. La ligne où IaC se termine et où la gestion de la configuration commence peut être floue et très dépendante des processus au sein d’une organisation. Vous devrez peut-être limiter cette conversation. Le déploiement d’une APIM de base à livrer à l’équipe d’application pour une configuration plus poussée est une solution acceptable.  

## <a name="why-api-management-and-azure-monitor"></a>Pourquoi Gestion des API et Azure Monitor

* Gestion des API est une façade/interface qui intercepte les appels d’API et peut les manipuler pour accomplir diverses tâches (comme la sécurisation des points de terminaison, la limitation, le monitoring, etc.).
* Azure Monitor offre une visibilité sur l’état et l’intégrité de vos ressources Azure.
