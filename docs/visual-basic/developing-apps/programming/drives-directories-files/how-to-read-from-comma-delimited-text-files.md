---
title: "How to: Read From Comma-Delimited Text Files in Visual Basic | Microsoft Docs"
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
  - "files, parsing"
  - "text files, tasks"
  - "reading text files, comma-delimited"
  - "text files, reading"
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Read From Comma-Delimited Text Files in Visual Basic
L'objet `TextFieldParser` permet d'analyser facilement et efficacement les fichiers texte structurés, tels que les journaux.  La propriété `TextFieldType` définit s'il s'agit d'un fichier délimité ou d'un fichier dont les champs de texte ont une largeur fixe.  
  
### Pour analyser un fichier texte séparé par des virgules  
  
1.  Créez un `TextFieldParser`.  Le code suivant crée le `TextFieldParser` nommé `MyReader` et ouvre le fichier `test.txt`.  
  
     [!CODE [VbFileIORead#15](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#15)]  
  
2.  Définissez le type et le séparateur de `TextField`.  Le code suivant définit la propriété `TextFieldType` comme `Delimited` et « , » comme séparateur.  
  
     [!CODE [VbFileIORead#16](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#16)]  
  
3.  Parcourez les champs du fichier.  Si des lignes sont endommagées, signalez une erreur poursuivez l'analyse.  Le code suivant parcourt le fichier et affiche tour à tour chaque champ en signalant ceux qui sont mis en forme incorrectement.  
  
     [!CODE [VbFileIORead#17](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#17)]  
  
4.  Fermez les blocs `While` et `Using` avec `End While` et `End Using`.  
  
     [!CODE [VbFileIORead#18](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#18)]  
  
## Exemple  
 Cet exemple lit le fichier `test.txt`.  
  
 [!CODE [VbFileIORead#19](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#19)]  
  
## Programmation fiable  
 Les conditions ci\-dessous peuvent générer une exception.  
  
-   Une ligne ne peut pas être analysée avec le format spécifié \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  Le message d'exception spécifie la ligne qui provoque l'exception, tandis que la propriété <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> est assignée au texte contenu dans la ligne.  
  
-   Le fichier spécifié n'existe pas \(<xref:System.IO.FileNotFoundException>\).  
  
-   Une situation de niveau de confiance partiel dans laquelle l'utilisateur n'a pas les autorisations suffisantes pour accéder au fichier.  \(<xref:System.Security.SecurityException>\).  
  
-   Le chemin d'accès est trop long \(<xref:System.IO.PathTooLongException>  
  
-   L'utilisateur n'a pas les autorisations suffisantes pour accéder au fichier \(<xref:System.UnauthorizedAccessException>\).  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [How to: Read From Fixed\-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Dépannage des exceptions : Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)