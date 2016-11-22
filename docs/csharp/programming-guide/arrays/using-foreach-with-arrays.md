---
title: "Utilisation de foreach avec des tableaux (Guide de programmation C#) | Microsoft Docs"
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
  - "tableaux (C#), foreach"
  - "foreach (instruction C#), utiliser avec des tableaux"
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Utilisation de foreach avec des tableaux (Guide de programmation C#)
C\# fournit également l'instruction [foreach](../../../csharp/language-reference/keywords/foreach-in.md),  Cette instruction offre une méthode simple et appropriée pour itérer au sein des éléments d'un tableau ou de toute collection énumérable.  L'instruction `foreach` traite les éléments dans l'ordre retourné par la tableau ou l'énumérateur du type de collection, en général, du 0e élément au dernier.  Par exemple, le code suivant crée un tableau intitulé `numbers` et itère au sein de ce dernier avec l'instruction `foreach` :  
  
 [!CODE [csProgGuideArrays#28](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#28)]  
  
 Dans le cas de tableaux multidimensionnels, il est possible d'utiliser la même méthode pour itérer au sein de tous les éléments, par exemple :  
  
 [!CODE [csProgGuideArrays#29](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#29)]  
  
 Cependant, dans le cas de tableaux multidimensionnels, l'utilisation d'une boucle [for](../../../csharp/language-reference/keywords/for.md) imbriquée donne davantage de contrôle sur les éléments du tableau.  
  
## Voir aussi  
 <xref:System.Array>   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Tableaux](../../../csharp/programming-guide/arrays/index.md)   
 [Tableaux unidimensionnels](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Tableaux multidimensionnels](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Tableaux en escalier](../../../csharp/programming-guide/arrays/jagged-arrays.md)