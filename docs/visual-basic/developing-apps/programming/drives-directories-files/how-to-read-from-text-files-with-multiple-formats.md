---
title: "How to: Read From Text Files with Multiple Formats in Visual Basic | Microsoft Docs"
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
  - "TextFieldParser object, reading from a file"
  - "TextFieldType enumeration"
  - "My.Computer.FileSystem.WriteAllText method, parsing structured text files"
  - "WriteAllText method, parsing structured text files"
  - "PeekChars method, determining format of text"
  - "reading text files, multiple formats"
  - "I/O [Visual Basic], reading text files"
  - "text files, reading"
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Read From Text Files with Multiple Formats in Visual Basic
L'objet <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> permet d'analyser facilement et efficacement les fichiers texte structurés, tels que les journaux.  Vous pouvez traiter un fichier à plusieurs formats à l'aide de la méthode `PeekChars` pour déterminer le format de chaque ligne à mesure que vous analysez le fichier.  
  
### Pour analyser un fichier texte avec plusieurs formats  
  
1.  Ajoutez un fichier texte nommé testfile.txt à votre projet.  Ajoutez le contenu suivant au fichier texte.  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2.  Définissez le format attendu et le format utilisé lorsqu'une erreur est signalée.  La dernière entrée dans chaque tableau étant \-1, le champ est supposé être à largeur variable.  Cela se produit lorsque la dernière entrée dans le tableau est inférieure ou égale à 0.  
  
     [!CODE [VbFileIORead#4](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#4)]  
  
3.  Créez un objet <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> en définissant la largeur et le format.  
  
     [!CODE [VbFileIORead#5](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#5)]  
  
4.  Parcourez les lignes en testant le format avant la lecture.  
  
     [!CODE [VbFileIORead#6](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#6)]  
  
5.  Écrivez les erreurs dans la console.  
  
     [!CODE [VbFileIORead#7](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#7)]  
  
## Exemple  
 Voici l'exemple complet qui lit le fichier `testfile.txt`.  
  
 [!CODE [VbFileIORead#8](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#8)]  
  
## Programmation fiable  
 Les conditions ci\-dessous peuvent générer une exception.  
  
-   Une ligne ne peut pas être analysée avec le format spécifié \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  Le message d'exception spécifie la ligne qui provoque l'exception, tandis que la propriété <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> est assignée au texte contenu dans la ligne.  
  
-   Le fichier spécifié n'existe pas \(<xref:System.IO.FileNotFoundException>\).  
  
-   Une situation de niveau de confiance partiel dans laquelle l'utilisateur n'a pas les autorisations suffisantes pour accéder au fichier.  \(<xref:System.Security.SecurityException>\).  
  
-   Le chemin d'accès est trop long \(<xref:System.IO.PathTooLongException>  
  
-   L'utilisateur n'a pas les autorisations suffisantes pour accéder au fichier \(<xref:System.UnauthorizedAccessException>\).  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 [How to: Read From Comma\-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [How to: Read From Fixed\-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)