---
title: "How to: Read From Text Files in Visual Basic | Microsoft Docs"
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
  - "extended characters, reading"
  - "reading text files"
  - "reading data, text files"
  - "examples [Visual Basic], reading text files"
  - "text files, reading"
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Read From Text Files in Visual Basic
La méthode <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> de l'objet `My.Computer.FileSystem` vous permet de lire un fichier texte.  L'encodage du fichier peut être spécifié si le contenu de ce dernier utilise l'encodage ASCII ou UTF\-8.  
  
 Si vous lisez un fichier avec des caractères étendus, vous devez spécifier son encodage.  
  
> [!NOTE]
>  Pour lire un fichier, une ligne de texte à la fois, utilisez la méthode <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> de l'objet `My.Computer.FileSystem`.  La méthode `OpenTextFileReader` retourne un objet <xref:System.IO.StreamReader>.  Vous pouvez utiliser la méthode <xref:System.IO.StreamReader.ReadLine%2A> de l"objet `StreamReader` pour lire un fichier une ligne à la fois.  Vous pouvez tester la fin du fichier à l'aide de la méthode <xref:System.IO.StreamReader.EndOfStream%2A> de l'objet `StreamReader`.  
  
### Pour lire un fichier texte  
  
-   Utilisez la méthode `ReadAllText` de l'objet `My.Computer.FileSystem` pour lire le contenu d'un fichier texte dans une chaîne en fournissant le chemin d'accès.  L'exemple suivant lit le contenu du fichier test.txt dans une chaîne puis l'affiche dans un message.  
  
     [!CODE [VbFileIORead#2](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#2)]  
  
### Pour lire un fichier texte encodé  
  
-   Utilisez la méthode `ReadAllText` de l'objet `My.Computer.FileSystem` pour lire le contenu d'un fichier texte dans une chaîne en fournissant le chemin d'accès et le type d'encodage du fichier.  L'exemple suivant lit le contenu du fichier UTF32 test.txt dans une chaîne puis l'affiche dans un message.  
  
     [!CODE [VbFileIORead#3](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#3)]  
  
## Programmation fiable  
 Les conditions ci\-dessous peuvent générer une exception.  
  
-   Le chemin d'accès n'est pas valide pour une des raisons suivantes : il s'agit d'une chaîne de longueur nulle ; il ne contient que des espaces blancs ; il contient des caractères non valides ou il s'agit d'un chemin d'accès de périphérique \(<xref:System.ArgumentException>\).  
  
-   Le chemin d'accès n'est pas valide, car il a la valeur `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Le fichier n'existe pas \(<xref:System.IO.FileNotFoundException>\).  
  
-   Le fichier est utilisé par un autre processus, ou une erreur E\/S se produit \(<xref:System.IO.IOException>\).  
  
-   Le chemin d'accès dépasse la longueur maximale définie par le système \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nom de fichier ou de répertoire du chemin d'accès contient un signe deux\-points \(:\) ou n'a pas un format correct \(<xref:System.NotSupportedException>\).  
  
-   Il n'y a pas assez de mémoire pour écrire la chaîne dans la mémoire tampon \(<xref:System.OutOfMemoryException>\).  
  
-   L'utilisateur n'a pas les autorisations nécessaires pour afficher le chemin d'accès \(<xref:System.Security.SecurityException>\).  
  
 Ne vous basez pas sur le nom d'un fichier pour en déterminer le contenu.  Par exemple, il se peut que le fichier nommé Form1.vb ne soit pas un fichier source [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Vérifiez toutes les entrées avant d'utiliser les données dans votre application.  Le fichier n'a peut\-être pas le contenu attendu, et les méthodes utilisées pour lire le fichier peuvent échouer.  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>   
 [Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [How to: Read From Comma\-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [How to: Read From Fixed\-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [File Encodings](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)