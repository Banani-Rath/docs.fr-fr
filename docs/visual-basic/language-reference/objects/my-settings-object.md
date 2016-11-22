---
title: "My.Settings Object | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.MySettingsProperty.Settings"
  - "My.Settings"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings object"
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# My.Settings Object
Fournit des propriétés et des méthodes pour accéder aux paramètres de l'application.  
  
## Notes  
 L'objet `My.Settings` fournit un accès aux paramètres de l'application et vous permet de stocker et de récupérer de manière dynamique des paramètres de propriété et d'autres informations pour votre application.  Pour plus d'informations, consultez [Gestion des paramètres d'une application \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Propriétés  
 Les propriétés de l'objet `My.Settings` fournissent l'accès aux paramètres de votre application.  Pour ajouter ou supprimer des paramètres, utilisez le **Concepteur de paramètres**.  
  
 Chaque paramètre a un **Nom**, un **Type**, une **Portée** et une **Valeur**, et ces paramètres déterminent l'affichage de la propriété qui accède à chaque paramètre dans l'objet `My.Settings`:  
  
-   **Nom** détermine le nom de la propriété.  
  
-   **Type** détermine le type de la propriété.  
  
-   **Portée** indique si la propriété est en lecture seule.  Si la valeur est **Application**, la propriété est en lecture seule ; si la valeur est **Utilisateur**, la propriété est en lecture\-écriture.  
  
-   **Valeur** est la valeur par défaut de la propriété.  
  
## Méthodes  
  
|||  
|-|-|  
|Méthode|Description|  
|`Reload`|Recharge les paramètres utilisateur à partir des dernières valeurs enregistrées.|  
|`Save`|Enregistre les paramètres utilisateur actuels.|  
  
 L'objet `My.Settings` fournit également des propriétés et des méthodes avancées héritées de la classe <xref:System.Configuration.ApplicationSettingsBase>.  
  
## Tâches  
 Le tableau suivant répertorie des exemples de tâches impliquant l'objet `My.Settings`.  
  
|||  
|-|-|  
|Pour|Consultez|  
|Lire un paramètre d'application|[How to: Read Application Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Modifier un paramètre utilisateur|[How to: Change User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Faire persister les paramètres utilisateur|[How to: Persist User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Créer une grille de propriétés pour les paramètres utilisateur|[How to: Create Property Grids for User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## Exemple  
 Cet exemple affiche la valeur du paramètre `Nickname`.  
  
 [!CODE [VbVbalrMyResources#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyResources#14)]  
  
 Pour que cet exemple fonctionne, votre application doit avoir un paramètre `Nickname` de type `String`.  
  
## Voir aussi  
 <xref:System.Configuration.ApplicationSettingsBase>   
 [How to: Read Application Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [How to: Change User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [How to: Persist User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [How to: Create Property Grids for User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Gestion des paramètres d'une application \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)