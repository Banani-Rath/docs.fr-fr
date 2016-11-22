---
title: "select, clause (R&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "select_CSharpKeyword"
  - "select"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "select (clause C#)"
  - "select (mot clé C#)"
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# select, clause (R&#233;f&#233;rence C#)
Dans une expression de requête, la clause `select` spécifie le type de valeurs qui seront générées lors de l'exécution de la requête.  Le résultat est basé sur l'évaluation de toutes les clauses précédentes et sur toutes les expressions de la clause `select` elle\-même.  Une expression de requête doit se terminer par une clause `select` ou une clause [group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 L'exemple suivant montre une clause `select` simple dans une expression de requête.  
  
 [!CODE [cscsrefQueryKeywords#8](../CodeSnippet/VS_Snippets_VBCSharp/CsCsrefQueryKeywords#8)]  
  
 Le type de la séquence générée par la clause `select` détermine le type de la variable de requête `queryHighScores`.  Dans le cas le plus simple, la clause `select` spécifie uniquement la variable de portée.  La séquence retournée contient alors des éléments du même type que la source de données.  Pour plus d'informations, consultez [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  Toutefois, la clause `select` fournit également un mécanisme puissant pour transformer \(ou *projeter*\) les données source en types nouveaux.  Pour plus d'informations, consultez [Transformations de données avec LINQ \(C\#\)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).  
  
## Exemple  
 L'exemple suivant affiche tous les formulaires différents qu'une clause `select` peut prendre.  Dans chaque requête, notez la relation entre la clause `select` et le type de la *variable de requête* \(`studentQuery1`, `studentQuery2`, etc.\).  
  
 [!CODE [cscsrefQueryKeywords#9](../CodeSnippet/VS_Snippets_VBCSharp/CsCsrefQueryKeywords#9)]  
  
 Comme indiqué dans `studentQuery8` dans l'exemple précédent, vous pouvez parfois souhaiter que les éléments de la séquence retournée contiennent uniquement un sous\-ensemble des propriétés des éléments source.  En limitant au maximum la séquence retournée, vous pouvez réduire les besoins en ressources mémoire et augmenter la vitesse d'exécution de la requête.  Pour ce faire, vous pouvez créer un type anonyme dans la clause `select` et utiliser un initialiseur d'objet pour l'initialiser avec les propriétés appropriées de l'élément source.  Pour obtenir un exemple de cette procédure, consultez [Initialiseurs d'objets et de collections](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Notes  
 À la compilation, la clause `select` est traduite en un appel de méthode à l'opérateur de requête standard <xref:System.Linq.Enumerable.Select%2A>.  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Mots clés de requête \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [from, clause](../../../csharp/language-reference/keywords/from-clause.md)   
 [partielle, méthode \(Référence C\#\)](../../../csharp/language-reference/keywords/partial-method.md)   
 [Types anonymes](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Expressions de requête \(LINQ\)](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)