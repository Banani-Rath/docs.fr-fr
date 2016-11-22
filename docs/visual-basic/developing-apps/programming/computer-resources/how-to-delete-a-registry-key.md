---
title: "How to: Delete a Registry Key in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.DeleteSetting"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetSetting function"
  - "registry, deleting values"
  - "GetAllSettings function"
  - "registry keys, deleting"
  - "registry, deleting keys"
  - "examples [Visual Basic], registry"
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Delete a Registry Key in Visual Basic
Les méthodes <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> et <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> peuvent être utilisées pour supprimer des clés de Registre.  
  
## Procédure  
  
#### Pour supprimer une clé de Registre  
  
-   Utilisez la méthode `DeleteSubKey` pour supprimer une clé de Registre.  Cet exemple supprime la clé Software\/TestApp dans la ruche CurrentUser.  Vous pouvez spécifier la chaîne appropriée dans le code ou faire en sorte que celui\-ci repose sur des informations fournies par l'utilisateur.  
  
     [!CODE [VbResourceTasks#19](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#19)]  
  
## Programmation fiable  
 La méthode `DeleteSubKey` retourne une chaîne vide si la paire clé\/valeur n'existe pas.  
  
 Les conditions ci\-dessous peuvent générer une exception.  
  
-   Le nom de la clé est `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   L'utilisateur n'a pas l'autorisation de supprimer des clés de Registre \(<xref:System.Security.SecurityException>\).  
  
-   Le nom de la clé dépasse la limite de 255 caractères \(<xref:System.ArgumentException>\).  
  
-   La clé de Registre est en lecture seule \(<xref:System.UnauthorizedAccessException>\).  
  
## Sécurité .NET Framework  
 Les appels au Registre échouent lorsque l'utilisateur ne dispose pas des autorisations d'exécution nécessaires \(<xref:System.Security.Permissions.RegistryPermission>\) ou de l'accès correct \(tel que déterminé par les listes de contrôle d'accès\) pour créer ou modifier des paramètres.  Par exemple, une application locale disposant d'une autorisation de sécurité d'accès du code peut ne pas avoir une autorisation du système d'exploitation.  
  
## Voir aussi  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey>   
 [Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)