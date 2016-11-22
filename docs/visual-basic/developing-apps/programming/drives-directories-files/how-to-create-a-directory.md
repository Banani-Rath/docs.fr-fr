---
title: "How to: Create a Directory in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "directories [Visual Basic], creating"
  - "folders [Visual Basic], creating"
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Create a Directory in Visual Basic
Utilisez la méthode `CreateDirectory` de l'objet `My.Computer.FileSystem` pour créer des répertoires.  
  
 Si le répertoire existe déjà, aucune exception n'est levée.  
  
### Pour créer un répertoire  
  
-   Utilisez la méthode `CreateDirectory` en spécifiant le chemin d'accès complet de l'emplacement où le répertoire doit être créé.  Cet exemple crée le répertoire `NewDirectory` dans `C:\Documents and Settings\All Users\Documents`.  
  
     [!CODE [VbVbcnMyFileSystem#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#2)]  
  
## Programmation fiable  
 Les conditions ci\-dessous peuvent générer une exception.  
  
-   Le chemin d'accès est incorrect.  Il contient par exemple des caractères non valides ou se compose uniquement d'un espace blanc \(<xref:System.ArgumentException>\).  
  
-   Le répertoire parent du répertoire à créer est en lecture seule \(<xref:System.IO.IOException>\).  
  
-   Le chemin d'accès est `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Le nom de répertoire est trop long \(<xref:System.IO.PathTooLongException>\).  
  
-   Le nom de répertoire est formé du signe deux points « : » \(<xref:System.NotSupportedException>\).  
  
-   L'utilisateur n'est pas autorisé à créer le répertoire \(<xref:System.UnauthorizedAccessException>\).  
  
-   L'utilisateur n'a pas les autorisations nécessaires dans une situation de niveau de confiance partiel \(<xref:System.Security.SecurityException>\).  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>   
 [Creating, Deleting, and Moving Files and Directories](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)