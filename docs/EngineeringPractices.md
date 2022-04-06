---
ms.openlocfilehash: 74e5dd66ad1939639c5006e15ea0fe7ea441d882
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813640"
---
# <a name="engineering-practices"></a>Pratiques d’ingénierie

## <a name="definition-of-done"></a>Définition de Terminé

- [ ] Modifications du code révisées et validées
- [ ] La documentation existante est mise à jour (Lisez-moi, .md)
- [ ] La nouvelle documentation nécessaire pour prendre en charge la modification est créée
- [ ] Modifications du code archivées dans document principal
- [ ] Tous les tests automatisés existants (unité et/ou e2e) réussissent, de nouveaux tests sont ajoutés en fonction des besoins
- [ ] CI se termine correctement
- [ ] CD se termine correctement
- [ ] Déploiement de production du test de vérification de build pendant au moins 2 semaines
- [ ] Nouvelles modifications du test de vérification de build pendant 48 heures (en cours)
- [ ] Créer une tâche pour les artefacts requis

Manuel d’ingénierie [Définition de Terminé](https://github.com/microsoft/code-with-engineering-playbook/blob/master/team-agreements/definition-of-done/readme.md)

## <a name="markdown-md-files"></a>Markdown (fichiers md)

- Utiliser le complément [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) pour VS Code
- Utiliser « - » pour les listes non triées
- Ajouter une ligne vide avant et après « ' » pour la visualisation

## <a name="kanban-management-best-practices"></a>Bonnes pratiques de gestion Kanban

### <a name="triage"></a>Tri

Tous les problèmes net-new doivent être triés, tirer parti des notes pour les points de discussion en fonction des besoins

- Créer le problème dans le tableau et le modèle appropriés
- Ajouter un projet au problème (par exemple, Helium) - il s’agit d’un ajout automatique au tableau maître
- Ajouter toutes les balises pertinentes (langue, opportunité, bogue, révision de la conception, bogue, etc.)
- Ne pas ajouter de taille, de priorité ou de personne responsable
- Tous les problèmes seront triés à la fin de l’appel debout

### <a name="backlog"></a>Backlog

Une fois que le problème a été trié, déplacez-vous dans le Backlog

- Une fois le problème trié, ajoutez la balise de priorité appropriée et ajoutez des étiquettes net-new
- Ne pas ajouter de taille ou de personne responsable

### <a name="sprint-backlog"></a>Journal des travaux en souffrance des sprints

Les problèmes identifiés lors de la planification du sprint seront déplacés dans le backlog des sprints

- Nécessité d’examiner et de mettre à jour la priorité et d’ajouter des étiquettes de dimensionnement estimé

### <a name="in-progress"></a>En cours

Problèmes sur lesquels l’équipe de développement travaille activement

- Ajouter une personne responsable et des balises de taille et s’assurer que toutes les balises appropriées sont ajoutées
- Si une révision de conception est requise, planifier une réunion lors du déplacement du problème dans le Backlog
- Si la tâche est supérieure à « Taille : L », décomposer en tâches plus petites pour garantir l’achèvement pendant le sprint de la semaine

### <a name="review-in-progress"></a>Vérification en cours

Requêtes de tirage pour créer ou mettre à jour du code, de la documentation, des modèles, etc., ainsi que les problèmes qui doivent être révisés

- Compléter le modèle PR (assurez-vous que le problème d’origine est fermé ou référencé)
- Affecter des réviseurs, vous attribuer vous-même, ajouter un tableau de project
- Si le problème présente plusieurs problèmes pour fermer et/ou référencer, signalez chaque référence/clôture # sur une ligne distincte pour garantir un lien correct

### <a name="review-approved"></a>Révision approuvée

Demandes de tirage qui ont reçu leur approbation et qui sont prêtes à être fusionnées

- Fusionner les changements
- Fermer la demande de tirage (pull request)
- Supprimer la branche si elle n’est pas utilisée

### <a name="done"></a>Terminé

- Le problème est terminé, aucune action supplémentaire n’est requise
- Vérifier que la liste de contrôle des tâches est complète
