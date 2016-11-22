---
title: "Parsing Text Files with the TextFieldParser Object (Visual Basic) | Microsoft Docs"
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
  - "TextFieldParser object, using"
  - "I/O [Visual Basic], parsing files"
  - "files, parsing"
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Parsing Text Files with the TextFieldParser Object (Visual Basic)
L'objet `TextFieldParser` vous permet d'analyser et de traiter de très gros fichiers structurés sous forme de colonnes de texte à largeur délimitée, tels que les fichiers journaux ou les informations sur les bases de données héritées \(legacy\).  Analyser un fichier texte avec le `TextFieldParser` revient à itérer sur un fichier texte, alors que la méthode d'analyse pour extraire des champs de texte correspond aux méthodes de manipulation des chaînes utilisées pour réinitialiser les chaînes délimitées.  
  
## Analyse de différents types de fichiers texte  
 Les fichiers texte peuvent avoir des champs à largeur différente, délimités par un caractère tel qu'une virgule ou un espace de tabulation.  Définissez `TextFieldType` et le séparateur, comme dans l'exemple suivant, qui utilise la méthode `SetDelimiters` pour définir un fichier texte délimité par des tabulations :  
  
 [!CODE [VbVbalrTextFieldParser#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTextFieldParser#21)]  
  
 D'autres fichiers texte peuvent avoir des largeurs de champ fixes.  Dans de tels cas, vous devez affecter le `TextFieldType` à `FixedWidth` et définir les largeurs de chaque champ, comme dans l'exemple suivant.  Cet exemple utilise la méthode `SetFieldWidths` pour définir les colonnes de texte : la première colonne a une largeur de 5 caractères, la deuxième de 10, la troisième de 11, tandis que la quatrième a une largeur variable.  
  
 [!CODE [VbVbalrTextFieldParser#22](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTextFieldParser#22)]  
  
 Une fois le format défini, vous pouvez parcourir le fichier à l'aide de la méthode `ReadFields` pour traiter tour à tour chaque ligne.  
  
 Si un champ ne correspond pas au format spécifié, une exception <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> est levée.  Dans ce cas, les propriétés `ErrorLine` et `ErrorLineNumber` contiennent le texte à l'origine de l'exception et le numéro de ligne de celui\-ci.  
  
## Analyse de fichiers à plusieurs formats  
 La méthode `PeekChars` de l'objet `TextFieldParser` peut être utilisée pour vérifier chaque champ avant de le lire en vous permettant de définir plusieurs formats pour les champs et de réagir en conséquence.  Pour plus d'informations, consultez [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>   
 [Dépannage des exceptions : Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)