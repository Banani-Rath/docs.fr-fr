---
title: "How to: Create a String from An Array of Char Values (Visual Basic) | Microsoft Docs"
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
  - "examples [Visual Basic], arrays"
  - "examples [Visual Basic], Char data type"
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Create a String from An Array of Char Values (Visual Basic)
Cet exemple crée la chaîne "abcd" en utilisant des caractères isolés.  
  
## Exemple  
 [!CODE [VbVbalrStrings#61](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#61)]  
  
## Compilation du code  
 Cette méthode n'a aucune exigence particulière.  
  
 La syntaxe `"a"c`, où un seul `c` suit un caractère unique entre guillemets, est utilisé pour créer un littéral de caractère.  
  
## Programmation fiable  
 Les caractères Null \(`Chr(0)`\) faisant partie de la chaîne produisent des résultats inattendus lors de l'utilisation de la chaîne.  Le caractère Null sera inclus dans la chaîne, mais dans certains cas les caractères suivants ne seront pas affichés.  
  
## Voir aussi  
 <xref:System.String>   
 [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Types de données](../../../../visual-basic/programming-guide/language-features/data-types/index.md)