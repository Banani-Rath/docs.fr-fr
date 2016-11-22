---
title: "%= Operator (C# Reference) | Microsoft Docs"
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
  - "%=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "modulus assignment operator (=%) [C#]"
  - "%= assignment operator (modulus assignment) [C#]"
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# %= Operator (C# Reference)
l'opérateur d'assignation de reste.  
  
## Notes  
 Expression utilisant l'opérateur d'assignation `%=`, comme  
  
```  
x %= y  
```  
  
 est équivalent à  
  
```  
x = x % y  
```  
  
 si ce n'est que `x` n'est évalué qu'une seule fois.  L'[opérateur %](../../../csharp/language-reference/operators/modulus-operator.md) est prédéfini pour les types numériques afin de calculer le reste d'une division.  
  
 L'opérateur `%=` ne peut pas être surchargé directement, mais les types définis par l'utilisateur peuvent surcharger l'opérateur [%](../../../csharp/language-reference/operators/modulus-operator.md) \(consultez [d'opérateur](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Exemple  
 [!CODE [csRefOperators#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#4)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)