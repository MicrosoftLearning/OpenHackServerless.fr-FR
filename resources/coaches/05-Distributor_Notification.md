---
ms.openlocfilehash: 0f878ef1c7fc3cce02a829993ac3204ba0c498e2
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813636"
---
# <a name="notify-all-distributors-of-the-new-ice-cream-line"></a>Notifier tous les distributeurs de la nouvelle gamme de glaces

## <a name="progress-diagram"></a>Diagramme de progression

![Diagramme de progression de la notification des distributeurs](https://serverlessoh.azureedge.net/public/distributor-notification-progress-diagram.jpg)

## <a name="happy-path"></a>Chemin idéal

Choisir l’une de ces options

* Utiliser Logic Apps, avec les connecteurs de messagerie Common Data Service et Office 365, et créer l’action Table HTML ou les actions de variables  

* Utiliser Logic Apps et Azure Functions ensemble (Logic Apps pour les connecteurs de messagerie Common Data Service et Office 365, et Azure Functions pour obtenir la liste des produits et générer un code HTML pour celle-ci)  

## <a name="coaches-notes"></a>Remarques à l’attention des instructeurs

* Deux adresses e-mail sont définies pour les contacts CRM. Vous pouvez les utiliser pour valider l’envoi des e-mails. Pour valider, connectez-vous avec les comptes suivants : utilisateur OHCoach1@microsoftopenhack.onmicrosoft.com avec le mot de passe OpenHackCoach1, et utilisateur OHCoach2@microsoftopenhack.onmicrosoft.com avec le mot de passe OpenHackCoach2 sur [Office.com](https://outlook.office.com).

* Quand vous utilisez Logic Apps, le connecteur à utiliser avec les e-mails est `Microsoft Dataverse Connector`. Il liste l’action comme étant héritée : `List rows (legacy)`.  

* N’oubliez pas d’ajouter une nouvelle connexion dans Logic Apps lors de la connexion au connecteur Dataverse et entrez les informations d’identification conformément au défi.  Une fois ces informations entrées correctement, la liste des options s’affiche.  Générez l’application logique autour de cette liste avec le contrôle foreach.

* Utilisez la même connexion pour le connecteur Dataverse et la connexion Office 365 Outlook.

* Utilisez Postman pour indiquer à l’application logique de tester les connexions et les données en dehors du workflow normal.   N’oubliez pas de définir l’en-tête du type de contenu sur `'Content-Type' : 'application/json'`.  

* Aidez les participants à exécuter l’application logique sans la solution complète et à vérifier les entrées/sorties de chaque action afin qu’ils sachent comment extraire l’e-mail de la réponse du connecteur Common Data Service.  Créez facilement une boucle foreach avec un connecteur d’application logique et sélectionnez la propriété `Email` pour chaque contact.

   >REMARQUE : Une solution est disponible à l’emplacement ~/solutions/codeless/Distributor_Notification/logicapp.json

* Demandez aux équipes d’utiliser le connecteur Office 365 Outlook pour envoyer un e-mail. Si elles ont besoin d’une aide supplémentaire, dirigez-les vers l’article [Action Envoyer un e-mail (v2)](https://docs.microsoft.com/en-us/connectors/office365connector/#send-an-email-(v2)).  

* Les participants doivent créer le contenu de l’e-mail avec des variables Logic App, puis insérer la variable dans le corps de l’e-mail.  Pour plus de simplicité, la totalité du corps de l’e-mail peut également être une variable composée.

* Si vous recevez le message « Impossible de récupérer Swagger » lors de l’utilisation de l’action Azure Functions dans Logic Apps, revenez à l’application de fonction, puis, dans les paramètres CORS, supprimez toutes les entrées et ajoutez une entrée pour `*`.  

* Il existe un bogue connu avec Logic Apps et le connecteur Gestion des API : le connecteur ne peut pas récupérer la liste des actions lors de l’utilisation du niveau **Consommation** de la Gestion des API.  Pour plus d’informations, consultez [cette page](https://stackoverflow.microsoft.com/questions/169694/support-for-consumption-tier-apim-instances-in-the-logic-app-connector ) et [cette page](https://social.msdn.microsoft.com/Forums/890b2235-ff66-4186-9aa3-b16909dc81a1/logic-apps-no-showing-azure-api-management-apis?forum=azureapimgmt).

* Si vous recevez une erreur indiquant que le fournisseur de ressources Microsoft.EventGrid n’a pas été inscrit pour l’abonnement du participant, veillez à suivre les étapes d’inscription du fournisseur de ressources EventGrid dans [Inscrire Event Grid en tant que fournisseur de ressources](https://docs.microsoft.com/en-us/azure/event-grid/custom-event-quickstart-portal).

## <a name="why-azure-logic-apps"></a>Pourquoi Azure Logic Apps

* Les applications logiques sont faciles à utiliser, avec des workflows qui peuvent être créés en quelques configurations seulement par glisser-déplacer dans un éditeur puissant, ce qui permet à votre équipe d’orchestrer rapidement et facilement des logiques complexes.
* Les applications logiques ont des coûts de stockage minimes et peuvent être exécutées des centaines de fois selon une approche basée sur la consommation très économique.  

## <a name="infrastructure-as-code"></a>Infrastructure en tant que code

* Il n’y a pas d’objectif ou d’exigence spécifique pour IaC dans ce défi, mais sachez que la création de connecteurs Logic App dans le code est une opération difficile si l’équipe envisage cette approche. Il n’y a pas de ressource Terraform permettant de créer des connecteurs, mais les exemples Bicep et ARM disponibles en dehors de la documentation Microsoft peuvent déboucher sur une solution.

[ARM pour les workflows logiques](https://docs.microsoft.com/en-us/azure/templates/microsoft.logic/workflows?tabs=bicep)
[Guide pratique pour créer un connecteur d’application logique dans un modèle ARM](https://vincentlauzon.com/2017/10/28/how-to-create-a-logic-app-connector-in-an-arm-template/)
[Guide pratique pour utiliser des connecteurs personnalisés d’applications logiques avec ARM et CI/CD](https://mikaelsand.se/2020/11/how-to-use-logic-apps-custom-connectors-with-arm-and-ci-cd/)
[Guide pratique pour déployer une application logique avec le connecteur Office 365 dans un modèle ARM](https://stackoverflow.com/questions/60703570/how-to-deploy-logic-app-with-o365-connector-within-arm-template)
