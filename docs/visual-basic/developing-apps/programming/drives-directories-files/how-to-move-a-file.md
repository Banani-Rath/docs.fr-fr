---
title: "Comment&#160;: d&#233;placer un fichier dans Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
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
  - "fichiers, déplacer"
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: d&#233;placer un fichier dans Visual Basic
Vous pouvez utiliser la méthode `My.Computer.FileSystem.MoveFile` pour déplacer un fichier vers un autre dossier. Si la structure cible n’existe pas, elle est créée.  
  
### Pour déplacer un fichier  
  
-   Utilisez la méthode `MoveFile` pour déplacer le fichier, en spécifiant le nom et l’emplacement du fichier source et du fichier cible. Dans cet exemple, le fichier nommé `test.txt` est déplacé de `TestDir1` vers `TestDir2`. Notez que le nom du fichier cible est spécifié même s’il est identique à celui du fichier source.  
  
     [!CODE [VbVbcnMyFileSystem#24](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#24)]  
  
### Pour déplacer et renommer un fichier  
  
-   Utilisez la méthode `MoveFile` pour déplacer le fichier, en spécifiant le nom et l’emplacement du fichier source, l’emplacement cible et le nouveau nom du fichier à l’emplacement cible. Dans cet exemple, le fichier nommé `test.txt` est déplacé de `TestDir1` vers `TestDir2`, puis renommé en `nexttest.txt`.  
  
     [!CODE [VbVbcnMyFileSystem#25](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#25)]  
  
## Programmation fiable  
 Les conditions ci\-dessous peuvent générer une exception.  
  
-   Le chemin n’est pas valide pour l’une des raisons suivantes : il s’agit d’une chaîne de longueur nulle, il contient uniquement des espaces blancs, il contient des caractères non valides ou c’est un chemin d’appareil \(commençant par \\\\.\\\) \(<xref:System.ArgumentException>\).  
  
-   Le chemin n’est pas valide, car il a la valeur `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `destinationFileName` est `Nothing` ou une chaîne vide \(<xref:System.ArgumentNullException>\).  
  
-   Le fichier source n’est pas valide ou n’existe pas \(<xref:System.IO.FileNotFoundException>\).  
  
-   Le chemin combiné pointe vers un répertoire existant, le fichier de destination existe et `overwrite` a la valeur `False`, un fichier du répertoire cible portant le même nom est actuellement utilisé, ou l’utilisateur ne dispose pas des autorisations suffisantes pour accéder au fichier \(<xref:System.IO.IOException>\).  
  
-   Un nom de fichier ou de répertoire du chemin contient un signe deux\-points \(:\) ou n'a pas un format correct \(<xref:System.NotSupportedException>\).  
  
-   `showUI` a la valeur `True`, `onUserCancel` a la valeur `ThrowException` et l’utilisateur a annulé l’opération ou une erreur d’E\/S non spécifiée s’est produite \(<xref:System.OperationCanceledException>\).  
  
-   Le chemin dépasse la longueur maximale définie par le système \(<xref:System.IO.PathTooLongException>\).  
  
-   L'utilisateur n'a pas les autorisations nécessaires pour afficher le chemin \(<xref:System.Security.SecurityException>\).  
  
-   L’utilisateur ne dispose pas de l’autorisation nécessaire \(<xref:System.UnauthorizedAccessException>\).  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>   
 [How to: Rename a File](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)   
 [How to: Create a Copy of a File in a Different Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)   
 [Comment : analyser des chemins d'accès](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)