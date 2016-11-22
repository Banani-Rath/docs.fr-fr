---
title: "^, op&#233;rateur (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "^_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "^ (opérateur C#)"
  - "opérateur de bits OR exclusif (C#)"
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# ^, op&#233;rateur (r&#233;f&#233;rence C#)
Les opérateurs `^` binaires sont prédéfinis pour les types intégraux et `bool`.  Pour les types intégraux, `^` effectue l'opération de bits OR exclusif sur les opérandes.  Pour les opérandes `bool`, `^` effectue l'opération logique OR exclusive sur ses opérandes. En conséquence, le résultat est `true` si et seulement si un seul des opérandes correspond à `true`.  
  
## Notes  
 Les types définis par l'utilisateur peuvent surcharger l'opérateur `^` \(consultez [opérateur](../../../csharp/language-reference/keywords/operator.md)\).  Les opérations sur les types intégraux sont en général autorisées sur énumération.  
  
## Exemple  
 [!CODE [csRefOperators#30](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#30)]  
  
 Le calcul de `0xf8 ^ 0x3f` dans l'exemple précédent exécute une opération de bits OR des deux valeurs binaires suivantes, qui correspondent aux valeurs hexadécimales F8 et 3F :  
  
 `1111 1000`  
  
 `0011 1111`  
  
 Le résultat de l'opération de bits OR exclusif est `1100 0111`, qui correspond à C7 en hexadécimal.  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)