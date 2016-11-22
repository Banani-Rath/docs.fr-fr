---
title: "How to: Read From Fixed-width Text Files in Visual Basic | Microsoft Docs"
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
  - "fixed-width text file"
  - "reading text files, fixed-width"
  - "files, parsing"
  - "text files, tasks"
  - "text files, reading"
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Read From Fixed-width Text Files in Visual Basic
L'objet `TextFieldParser` permet d'analyser facilement et efficacement les fichiers texte structurés, tels que les journaux.  
  
 La propriété `TextFieldType` définit si le fichier analysé est un fichier délimité ou un fichier dont les champs de texte ont une largeur fixe.  Dans un fichier texte à largeur fixe, le champ à la fin peut avoir une largeur variable.  Pour spécifier que le champ à la fin a une largeur variable, définissez\-le de sorte qu'il ait une largeur inférieure ou égale à zéro.  
  
### Pour lire un fichier texte à largeur fixe  
  
1.  Créez un `TextFieldParser`.  Le code suivant crée le `TextFieldParser` nommé `Reader` et ouvre le fichier `test.log`.  
  
     [!CODE [VbFileIORead#9](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#9)]  
  
2.  Affectez à la propriété `TextFieldType` la valeur `FixedWidth` en définissant la largeur et le format.  Le code suivant définit les colonnes de texte. La première a une largeur de 5 caractères, la deuxième de 10, la troisième de 11, tandis que la quatrième a une largeur variable.  
  
     [!CODE [VbFileIORead#10](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#10)]  
  
3.  Parcourez les champs du fichier.  Si des lignes sont endommagées, signalez une erreur poursuivez l'analyse.  
  
     [!CODE [VbFileIORead#11](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#11)]  
  
4.  Fermez les blocs `While` et `Using` avec `End While` et `End Using`.  
  
     [!CODE [VbFileIORead#12](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#12)]  
  
## Exemple  
 Cet exemple lit le fichier `test.log`.  
  
 [!CODE [VbFileIORead#13](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#13)]  
  
## Programmation fiable  
 Les conditions ci\-dessous peuvent générer une exception.  
  
-   Une ligne ne peut pas être analysée avec le format spécifié \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  Le message d'exception spécifie la ligne qui provoque l'exception, tandis que la propriété <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> est assignée au texte contenu dans la ligne.  
  
-   Le fichier spécifié n'existe pas \(<xref:System.IO.FileNotFoundException>\).  
  
-   Une situation de niveau de confiance partiel dans laquelle l'utilisateur n'a pas les autorisations suffisantes pour accéder au fichier.  \(<xref:System.Security.SecurityException>\).  
  
-   Le chemin d'accès est trop long \(<xref:System.IO.PathTooLongException>  
  
-   L'utilisateur n'a pas les autorisations suffisantes pour accéder au fichier \(<xref:System.UnauthorizedAccessException>\).  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [How to: Read From Comma\-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Dépannage des exceptions : Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)