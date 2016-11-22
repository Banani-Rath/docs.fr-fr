---
title: "~, op&#233;rateur (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "~_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "~ (C#), opérateur de complément de bits"
  - "~ (opérateur C#)"
  - "opérateur de complément de bits (C#)"
  - "opérateur de complément à 1 (~) (C#)"
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# ~, op&#233;rateur (r&#233;f&#233;rence C#)
L'opérateur `~` effectue une opération de complément de bits sur son opérande, qui a pour effet d'inverser chaque bit.  Les opérateurs de complément de bits sont prédéfinis pour [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) et [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
> [!NOTE]
>  Le symbole `~` est également utilisé pour déclarer des destructeurs.  Pour plus d'informations, consultez [Destructeurs](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## Notes  
 Les types définis par l'utilisateur peuvent surcharger l'opérateur `~` .  Pour plus d'informations, consultez [operator](../../../csharp/language-reference/keywords/operator.md).  Les opérations sur les types intégraux sont en général autorisées sur énumération.  
  
## Exemple  
 [!CODE [csRefOperators#25](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#25)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)   
 [Destructeurs](../../../csharp/programming-guide/classes-and-structs/destructors.md)