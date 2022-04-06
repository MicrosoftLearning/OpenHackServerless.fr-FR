---
ms.openlocfilehash: 9612e7d41daa7faee6fa345d092564fd280c322b
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813688"
---
# <a name="serverless-openhack"></a>OpenHack serverless

## <a name="scenarios"></a>Scénarios

Les défis de ce Serverless OpenHack sont basés sur des scénarios réels et validés rencontrés par des clients :

* **Backend d’application/hébergement d’API** : scénario très courant, utilisant Azure Functions et Logic Apps pour implémenter une API complète pour une solution. Parfois, l’API elle-même est la solution principale que le client vend ; elle peut être associée au service Gestion des API Azure.

* **Intégration des activités et des systèmes avec un flux de travail** : un scénario récurrent avec les clients consiste à créer un flux de travail entre plusieurs systèmes (intégration de systèmes). Certains sont souvent des flux de travail professionnels avec interaction humaine (flux de travail d’entreprise).

* **Traitement des données d’utilisateur ou de télémétrie** : utilisation d’Azure Functions pour traiter, fractionner ou transférer des données d’utilisateur et de télémétrie externes entrant via Event Hubs, IoT Hub ou autre ; et exécution d’un flux de travail utilisant Logic Apps pour des alertes spécifiques. Adapté aux solutions avec moins de 100 000 messages par seconde sans aucune exigence de modèle d’acteur.

Il existe bien sûr de nombreux autres scénarios serverless. Nous ne couvrons que ceux qui ont été validés par CSE avec plusieurs clients. Cela devrait permettre au public d’avoir une bonne compréhension de l’approche serverless sur Azure et de son fonctionnement avec les autres services Azure.

## <a name="target-audience"></a>Public visé

L’événement cible tous les développeurs, mais met l’accent sur les développeurs qui créent des solutions professionnelles et d’entreprise. Ces défis sont également très intéressants pour les éditeurs de logiciels indépendants, car ils sont adaptés à l’architecture de microservices avec un plan basé sur la consommation.

Les participants n’ont pas besoin d’une connaissance préalable des offres Azure ou serverless Azure. Il est préférable de disposer d’une connaissance de base de C# ou de Node.js, mais cela n’est pas obligatoire.

Il peut y avoir des participants qui ne sont pas familiarisés avec le développement d’applications, et qui souhaitent se concentrer sur l’infrastructure et la connectivité des offres Azure. Dirigez ces participants vers les tâches de support « bonus » tout au long des défis, qui se concentrent sur le développement de l’infrastructure en tant que code requise pour déployer et configurer les offres serverless.  Ils peuvent également être encouragés à mener des discussions sur la meilleure façon de sécuriser chacun des composants.

À mesure que les défis progressent, en fonction de la vitesse des développeurs qui travaillent avec les composants serverless, il peut être difficile de coder et de déployer l’ensemble de l’infrastructure en mode « lock step » avec les développeurs. Encouragez les « codeurs d’infrastructure » à démontrer au moins l’approche qu’ils peuvent choisir pour incorporer chaque nouveau service à mesure qu’il entre en action dans le cadre du défi.  Cela peut être aussi simple que de rechercher de la documentation ou des références d’exemples de code.

## <a name="goals"></a>Objectifs

En plus des objectifs généraux de l’OpenHack pour améliorer les services Azure, améliorer la documentation et faire la promotion de ces technologies, nous nous concentrons sur les autres objectifs suivants :

* Mettre l’accent sur le délai de mise sur le marché et la facilité d’obtention des applications créées à l’aide de l’approche serverless

* En quoi l’approche serverless peut apporter un ensemble varié de services PaaS avec une facilité d’intégration

* Développer l’intégration pour les scénarios d’entreprise pour rassembler des applications métier

* Aider les participants à gagner en compétences sur la manière dont l’approche serverless peut résoudre des problèmes réels lors de la communication avec différents modules

## <a name="challenges-summary"></a>Résumé des défis

| Titre | Présentation des défis | Technologies possibles |
|-------|--------------------|-----------------------|
| 1 - Configuration de l’environnement de développement | Configurer les environnements de développement des équipes pour les défis à venir |
| 2 - Créer votre première fonction et votre premier workflow serverless | Créez et déboguez une fonction Azure localement, déployez-la dans Azure, testez-la à l’aide de Postman ou autre. Créer la première application logique | Functions, Logic Apps
| 3 - Finalisation de l’API de notation des crèmes glacées, et intégration continue et déploiement continu | Créer l’application de fonction d’évaluation pour finaliser l’API de la société lors de l’implémentation d’un pipeline CI/CD à utiliser par l’équipe | Functions, Cosmos DB, Azure DevOps, Jenkins, Kudu, autres solutions CI/CD
| 4 - Télémétrie système et Gestion des API | Activez les données de télémétrie pour l’API, affichez l’utilisation et les durées d’appel moyennes pour la dernière heure. Consolider toutes les applications de fonction derrière une seule URL de base, implémenter des stratégies de limitation de débit tout en exposant des API comme différentes suites de produits | Application Insights, AI Analytics, Gestion des API
| 5 - Notification du distributeur | Itérer au sein des distributeurs et leur envoyer des e-mails avec les détails de la nouvelle gamme de crèmes glacées | Logic Apps, Azure Functions
| 6 - Traiter les fichiers de commandes par lots du distributeur | Attendre l’arrivée d’un lot de fichiers et les traiter une fois que tous les fichiers d’un lot sont arrivés | Stockage, Event Grid, Logic Apps, Durable Functions, Functions
| 7 - Traiter les événements de vente du point de vente | Traiter les événements de vente du point de vente à mesure qu’ils arrivent en lots. Gérez un grand nombre d’événements et surveillez la mise à l’échelle automatique. | Event Hubs, Functions, Cosmos DB
| 8 - Pub/Sub et intégration réseau | Stockez des données d’URL de réception différentes pour une analyse plus poussée au sein d’un réseau virtuel privé. | Service Bus, Premium Functions, Comptes de stockage
| 9 - Alertes et notifications | Ajouter l’analyse des sentiments aux commentaires utilisateur à partir des évaluations et générer des alertes par e-mail quand un certain nombre de mauvaises évaluations de la part des clients arrivent au cours des 5 dernières minutes | Logic Apps, Functions
| 10 - Récapitulatif | Combinaison des données de toutes les sources pour créer des insights pour la gestion | Cosmos DB, Stream Analytics, Power BI

## <a name="what-does-a-coach-do"></a>Rôle d’un coach

### <a name="hacker-teams"></a>Équipes de hackers

* Faciliter la collaboration
* Définir des attentes
* Poser des questions, offrir des ressources plutôt que des réponses
* Encourager la créativité
* Résolution des problèmes : au niveau technique et interpersonnel

### <a name="manage-sentiment"></a>Gérer le sentiment

* Le contenu sera complexe et source de **frustration** à certains moments
* Les mettre au défi mais sans les bloquer
* Vérifier fréquemment et signaler les problèmes ou ce qui fonctionne correctement

### <a name="coach-team"></a>Équipe de coaching

* Partager les défis, les solutions
* Exploiter le canal **Teams**
* Collecter les **commentaires quotidiens** pour la synchronisation des coaches de fin de journée
* **Prendre des pauses** et communiquer avec les coaches qui vous entourent

## <a name="end-of-day-sync"></a>Synchronisation de fin de journée

Pour la synchronisation interne des coaches à la fin de chaque journée, vous devez poser trois questions à chacune de vos équipes :

* Qu’avez-vous accompli aujourd’hui ?
* Quel a été le défi le plus important aujourd’hui ?
* Y a-t-il quelque chose que nous pouvons faire mieux demain ?

## <a name="some-things-to-keep-in-mind"></a>Quelques points à garder à l’esprit

* Aucune instruction pas à pas ou « bonne » réponse
* Tous les points faibles ne sont pas supprimés
* Tout le monde doit apprendre et s’amuser. VOUS y compris !
* Conserver en privé les solutions de référence et le contenu des défis
* Les équipes ne finaliseront probablement pas tous les défis. Bien que nous ayons un classement, il est important qu’elles apprennent et ne prennent pas de raccourcis, elles peuvent rester dans les premiers défis, et l’objectif n’est PAS de finir tous les défis.

## <a name="code-of-conduct"></a>Code de conduite

La mission de Microsoft est de donner à chaque personne et à chaque organisation sur la planète les moyens de gagner en productivité. Cela englobe OpenHack où nous cherchons à créer une expérience respectueuse, conviviale et inclusive pour tous les participants.

Aussi, nous ne tolérons pas de comportement, de messages, d’images ou d’interactions perturbateurs ou irrespectueux de la part des participants à l’événement, sous quelque forme que ce soit, à n’importe quel aspect du programme, y compris les activités professionnelles et sociales, quel que soit le lieu.

Nous ne tolérons aucun comportement qui rabaisse le sexe, la race, l’orientation sexuelle ou le handicap, ou tout autre comportement qui violerait la politique anti-harcèlement et anti-discrimination de Microsoft, la politique d’opportunité d’emploi ou les standards du Code de conduite. En bref, la totalité de l’expérience doit respecter nos standards de culture.

Nous encourageons chacun à contribuer à la création d'un environnement accueillant et sûr. Signalez toute préoccupation, tout comportement de harcèlement ou toute activité suspecte ou perturbatrice pour le personnel du lieu d’accueil, l’hôte ou le propriétaire de l’événement, ou le garde de la sécurité ou le personnel le plus proche. 

Microsoft se réserve le droit de refuser l’admission au OpenHack ou de faire sortir toute personne du OpenHack à tout moment, à sa seule discrétion.

Nous vous demandons de prendre un rôle de leader pour vous assurer que cet événement est un succès pour vos pairs et nos clients. En quoi pouvez-vous aider :

* **Donnez la priorité à la satisfaction de nos clients et partenaires**. Montrez votre gentillesse et votre politesse à tous les autres participants et aidez le personnel de l’événement si besoin.
* Assurez-vous que tous les participants sont **respectueux des autres participants et les encouragent**. Si quelqu’un est exclu, ignoré ou interrompu, prenez le temps d’indiquer poliment au groupe d’être respectueux. Par exemple, « Je ne pense pas qu’il a terminé de partager ses réflexions »
* **Signalez immédiatement au personnel de l’événement tout incident** de harcèlement ou de manque de respect du sexe, de la race, de l’orientation sexuelle ou du handicap.
* N’oubliez pas qu’il y aura un certain nombre d’employés de Microsoft qui participeront aux défis. La majorité des participants sont externes. ** Merci de ne pas partager des informations confidentielles de Microsoft lors de l’événement ou des activités connexes. **
* N’utilisez pas de forums ouverts avec des experts techniques Microsoft (par exemple, lors des présentations à l’heure du déjeuner) pour poser des questions internes ou « complexes ». Les participants Microsoft doivent à la place trouver un moment privé pour poser ces questions ou fournir des commentaires.
