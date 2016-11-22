---
title: "!=, op&#233;rateur (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "!=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "!= (opérateur C#)"
  - "opérateur d'inégalité (!=) (C#)"
  - "opérateur différent de (!=) (C#)"
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# !=, op&#233;rateur (r&#233;f&#233;rence C#)
L'opérateur d'inégalité \(`!=`\) retourne false si les opérandes sont égaux et true dans le cas contraire.  Les opérateurs d'inégalité sont prédéfinis pour tous les types, y compris les chaînes et les objets.  Les types définis par l'utilisateur peuvent surcharger l'opérateur `!=`.  
  
## Notes  
 Pour les types valeur prédéfinis, l'opérateur d'inégalité \(`!=`\) retourne true si les valeurs des opérandes sont différentes et false dans le cas contraire.  Pour les types référence autres que `string`, `!=` retourne true si ses deux opérandes font référence à des objets différents.  Pour le type `string`, `!=` compare les valeurs des chaînes.  
  
 Les types valeur définis par l'utilisateur peuvent surcharger l'opérateur `!=` \(consultez [opérateur](../../../csharp/language-reference/keywords/operator.md)\).  Les types référence définis par l'utilisateur peuvent faire de même, même si par défaut, `!=` se comporte comme décrit ci\-dessus pour les types référence prédéfinis et définis par l'utilisateur.  Si `!=` est surchargé, [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) doit l'être également.  Les opérations sur les types intégraux sont en général autorisées sur énumération.  
  
## Exemple  
 [!CODE [csRefOperators#33](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#33)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)