---
title: "Op&#233;rateur (r&#233;f&#233;rence C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "[]_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "opérateur d'indice (C#)"
  - "crochets [ ], opérateur C#"
  - "[], opérateur C#"
  - "opérateur d'indexation (C#)"
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Op&#233;rateur (r&#233;f&#233;rence C#)
Les crochets \(`[]`\) sont utilisés pour les tableaux, les indexeurs et les attributs.  Ils peuvent aussi être utilisés avec des pointeurs.  
  
## Notes  
 Un type de tableau est un type suivi de `[]` :  
  
 [!CODE [csRefOperators#43](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#43)]  
  
 Pour accéder à un élément d'un tableau, l'index de l'élément souhaité est placé entre crochets :  
  
 [!CODE [csRefOperators#44](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#44)]  
  
 Une exception est levée si un index de tableau est hors limites.  
  
 L'opérateur d'indexation de tableau ne peut pas être surchargé. Toutefois, les types peuvent définir des indexeurs et des propriétés qui acceptent un ou plusieurs paramètres.  Les paramètres d'indexeur sont placés entre crochets, comme des index de tableau, mais ils peuvent être déclarés d'un type quelconque, contrairement aux index de tableau, qui doivent être intégraux.  
  
 Par exemple, le .NET Framework définit un type `Hashtable` qui associe des clés et des valeurs d'un type arbitraire :  
  
 [!CODE [csRefOperators#45](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#45)]  
  
 Des crochets sont également utilisés pour spécifier des [Attributs](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md) :  
  
 [!CODE [csRefOperators#46](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#46)]  
  
 Vous pouvez utiliser des crochets pour ignorer un pointeur dans un index :  
  
 [!CODE [csRefOperators#47](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#47)]  
  
 Aucune vérification des limites n'est effectuée.  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)   
 [Tableaux](../../../csharp/programming-guide/arrays/index.md)   
 [Indexeurs](../../../csharp/programming-guide/indexers/index.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed, instruction](../../../csharp/language-reference/keywords/fixed-statement.md)