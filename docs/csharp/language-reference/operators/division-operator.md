---
title: "/, op&#233;rateur (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "/_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/ (opérateur C#)"
  - "opérateur de division (C#)"
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# /, op&#233;rateur (r&#233;f&#233;rence C#)
L'opérateur de division \(`/`\) divise le premier opérande par le second opérande.  Tous les types numériques disposent d'opérateurs de division prédéfinis.  
  
## Notes  
 Les types définis par l'utilisateur peuvent surcharger l'opérateur `/` \(consultez [opérateur](../../../csharp/language-reference/keywords/operator.md)\).  Une surcharge de l'opérateur `/` surcharge implicitement l'opérateur [\/\=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md).  
  
 Lorsque vous divisez deux entiers, le résultat est toujours un entier.  Par exemple, le résultat de 7\/3 est 2.  Pour déterminer le reste du 7 \/ 3, utilisez l'opérateur de reste \([%](../../../csharp/language-reference/operators/modulus-operator.md)\).  Pour obtenir un quotient sous la forme d'un nombre rationnel ou d'une fraction, affectez le type `float` ou `double` au dividende ou au diviseur.  Vous pouvez attribuer un type implicitement si vous exprimez le dividende ou un diviseur d'un nombre décimal en plaçant un chiffre à droite de la virgule décimale, comme le montre l'exemple suivant.  
  
## Exemple  
 [!CODE [csRefOperators#42](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#42)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)