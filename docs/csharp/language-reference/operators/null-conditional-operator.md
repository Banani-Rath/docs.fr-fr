---
title: "?? Op&#233;rateur (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "??_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "?? (opérateur C#)"
  - "coalesce (opérateur C#)"
  - "opérateur conditionnel AND (&&) (C#)"
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# ?? Op&#233;rateur (r&#233;f&#233;rence C#)
L'opérateur `??` est appelé l'l'opérateur de fusion Null.  Il retourne l'opérande de partie gauche si ce dernier n'est pas Null ; dans le cas contraire, il retourne l'opérande de partie droite.  
  
## Notes  
 Un type Nullable peut représenter une valeur à partir du domaine du type, ou la valeur peut être non définie \(auquel cas la valeur est Null\).  Utilisez la simplicité de syntaxe de l'opérateur `??` pour retourner une valeur appropriée \(l'opérande de partie droite\) si l'opérande de partie gauche a un type Nullable dont la valeur est Null.  Si vous essayez d'assigner un type valeur Nullable à un type valeur non Nullable sans utiliser l'opérateur `??`, vous générez une erreur au moment de la compilation.  Si vous utilisez un cast et si le type valeur Nullable est actuellement non défini, une exception `InvalidOperationException` est levée.  
  
 Pour plus d'informations, consultez [Types Nullable](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Le résultat d'un opérateur ?? n'est pas interprété comme une constante même si ses deux arguments sont des constantes.  
  
## Exemple  
 [!CODE [csRefOperators#53](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#53)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)   
 [Types Nullable](../../../csharp/programming-guide/nullable-types/index.md)   
 [Que signifie réellement « Lifted » ?](http://go.microsoft.com/fwlink/?LinkID=112382)