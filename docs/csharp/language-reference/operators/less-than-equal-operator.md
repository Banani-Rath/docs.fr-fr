---
title: "&lt;=, op&#233;rateur (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "<=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<= (opérateur C#)"
  - "opérateur inférieur ou égal à (<=) (C#)"
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;=, op&#233;rateur (r&#233;f&#233;rence C#)
Tous les types numériques et d'énumération définissent un opérateur relationnel « inférieur ou égal à » \(`<=`\) qui retourne `true` si le premier opérande est inférieur ou égal au second, et `false` dans le cas contraire.  
  
## Notes  
 Les types définis par l'utilisateur peuvent surcharger l'opérateur `<=`.  Pour plus d'informations, consultez [operator](../../../csharp/language-reference/keywords/operator.md).  Si `<=` est surchargé, [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) doit l'être également.  Les opérations sur les types intégraux sont en général autorisées sur énumération.  
  
## Exemple  
 [!CODE [csRefOperators#32](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#32)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)   
 [explicites](../../../csharp/language-reference/keywords/explicit.md)