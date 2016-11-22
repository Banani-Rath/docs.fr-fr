---
title: "Comment&#160;: g&#233;rer des valeurs Null dans des expressions de requ&#234;te (Guide de programmation&#160;C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "valeurs null (LINQ en C#)"
  - "requêtes (LINQ en C#), valeurs null"
  - "expressions de requête (LINQ en C#), valeurs null"
ms.assetid: cb34f7a1-7ef5-466a-90ba-91da30ab525d
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: g&#233;rer des valeurs Null dans des expressions de requ&#234;te (Guide de programmation&#160;C#)
Cet exemple indique comment gérer des valeurs Null éventuelles dans les collections sources.  Une collection d'objets telle qu'un <xref:System.Collections.Generic.IEnumerable%601> peut contenir des éléments dont la valeur est [Null](../../../csharp/language-reference/keywords/null.md).  Si une collection source est Null ou contient un élément dont la valeur est Null, et que votre requête ne gère pas les valeurs Null, une <xref:System.NullReferenceException> sera levée lorsque vous exécuterez la requête.  
  
## Exemple  
 Vous pouvez coder de manière défensive pour éviter une exception de référence Null comme indiqué dans l'exemple suivant :  
  
 [!CODE [csProgGuideLINQ#82](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#82)]  
  
 Dans l'exemple précédent, la clause `where` élimine par filtrage tous les éléments Null dans la séquence de catégories.  Cette technique est indépendante du contrôle de valeur Null dans la clause join.  Dans cet exemple, l'expression conditionnelle avec Null fonctionne parce que `Products.CategoryID` est de type `int?` qui est un raccourci pour `Nullable<int>`.  
  
## Exemple  
 Dans une clause de jointure, si seule l'une des clés de comparaison est un type valeur Nullable, vous pouvez caster l'autre en un type Nullable dans l'expression de requête.  Dans l'exemple suivant, supposons que `EmployeeID` soit une colonne qui contient des valeurs de type `int?` :  
  
 [!CODE [csProgGuideLINQ#83](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#83)]  
  
## Voir aussi  
 <xref:System.Nullable%601>   
 [Expressions de requête \(LINQ\)](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Types Nullable](../../../csharp/programming-guide/nullable-types/index.md)