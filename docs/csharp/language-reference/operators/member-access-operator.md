---
title: ". Op&#233;rateur (r&#233;f&#233;rence&#160;C#) | Microsoft Docs"
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
  - "._CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ". opérateur (C#)"
  - "opérateur point (.) (C#)"
  - "opérateur d'accès aux membres (.) (C#)"
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# . Op&#233;rateur (r&#233;f&#233;rence&#160;C#)
L'opérateur point \(`.`\) est utilisé pour l'accès aux membres.  L'opérateur point spécifie un membre d'un type ou d'un espace de noms.  Par exemple, l'opérateur point est utilisé pour accéder aux méthodes spécifiques figurant dans les bibliothèques de classes .NET Framework :  
  
 [!CODE [csRefOperators#16](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#16)]  
  
 Par exemple, considérons la classe suivante :  
  
 [!CODE [csRefOperators#17](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#17)]  
  
 [!CODE [csRefOperators#18](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#18)]  
  
 La variable `s` possède deux membres, `a` et `b`. Pour accéder à ces membres, utilisez l'opérateur point :  
  
 [!CODE [csRefOperators#19](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#19)]  
  
 Le point est aussi utilisé pour former des noms qualifiés, c'est\-à\-dire des noms qui spécifient l'espace de noms ou l'interface, par exemple, auquel ils appartiennent.  
  
 [!CODE [csRefOperators#20](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#20)]  
  
 La directive using rend facultative la qualification de certains noms :  
  
 [!CODE [csRefOperators#21](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#21)]  
  
 En revanche, lorsqu'un identificateur est ambigu, il doit être qualifié :  
  
 [!CODE [csRefOperators#22](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#22)]  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)