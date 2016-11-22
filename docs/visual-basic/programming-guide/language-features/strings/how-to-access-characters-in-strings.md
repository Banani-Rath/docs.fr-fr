---
title: "How to: Access Characters in Strings in Visual Basic | Microsoft Docs"
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
  - "strings [Visual Basic], accessing characters"
  - "characters [Visual Basic], accessing in strings"
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Access Characters in Strings in Visual Basic
Cet exemple montre comment utiliser la propriété <xref:System.String.Chars%2A> pour accéder au caractère à l'emplacement spécifié dans une chaîne.  
  
## Exemple  
 Il est parfois utile de posséder des données sur les caractères de votre chaîne ainsi que sur les positions de ces caractères dans la chaîne.  Une chaîne peut être perçue comme un tableau de caractères \(instances de `Char`\) ; vous pouvez récupérer un caractère particulier en faisant référence à l'index de ce caractère par l'intermédiaire de la propriété <xref:System.String.Chars%2A>.  
  
 [!CODE [VbVbalrStrings#49](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#49)]  
  
 Le paramètre `index` de la propriété <xref:System.String.Chars%2A> est à base zéro.  
  
## Programmation fiable  
 La propriété <xref:System.String.Chars%2A> retourne le caractère à la position spécifiée.  Toutefois, certains caractères Unicode peuvent être représentés par plusieurs caractères.  Pour plus d'informations sur l'utilisation des caractères Unicode, consultez [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 La propriété <xref:System.String.Chars%2A> lève une exception <xref:System.IndexOutOfRangeException> si le paramètre `index` est supérieur ou égal à la longueur de la chaîne, ou s'il est inférieur à zéro  
  
## Voir aussi  
 <xref:System.String.Chars%2A>   
 [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)   
 [Converting Between Strings and Other Data Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)   
 [Strings](../../../../visual-basic/programming-guide/language-features/strings/index.md)