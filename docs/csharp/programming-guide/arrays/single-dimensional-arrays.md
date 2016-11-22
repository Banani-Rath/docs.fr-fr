---
title: "Tableaux unidimensionnels (Guide de programmation C#) | Microsoft Docs"
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
  - "tableaux (C#), unidimensionnel"
  - "tableaux unidimensionnels (C#)"
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Tableaux unidimensionnels (Guide de programmation C#)
Vous pouvez déclarer un tableau unidimensionnel de cinq entiers comme indiqué dans l'exemple suivant :  
  
 [!CODE [csProgGuideArrays#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#4)]  
  
 Ce tableau contient les éléments de `array[0]` à `array[4]`.  L'opérateur [new](../../../csharp/language-reference/keywords/new.md) est utilisé pour créer le tableau et initialiser ses éléments à leurs valeurs par défaut.  Dans cet exemple, tous les éléments du tableau sont initialisés à zéro.  
  
 Un tableau qui stocke des éléments de type chaîne peut être déclaré de la même façon.  Par exemple :  
  
 [!CODE [csProgGuideArrays#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#5)]  
  
## Initialisation des tableaux  
 Il est possible d'initialiser un tableau lors de sa déclaration, auquel cas le spécificateur de rang n'est pas nécessaire, car il est déjà fourni par le nombre d'éléments dans la liste d'initialisation.  Par exemple :  
  
 [!CODE [csProgGuideArrays#6](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#6)]  
  
 Un tableau de chaînes peut être initialisé de la même manière.  Ce qui suit est la déclaration d'un tableau de chaînes où chaque élément du tableau est initialisé par un nom du jour de la semaine :  
  
 [!CODE [csProgGuideArrays#7](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#7)]  
  
 Lorsque vous initialisez un tableau lors de sa déclaration, vous pouvez utiliser les raccourcis suivants :  
  
 [!CODE [csProgGuideArrays#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#8)]  
  
 Il est possible de déclarer une variable de tableau sans initialisation, mais vous devez alors utiliser l'opérateur `new` quand vous assignez un tableau à cette variable.  Par exemple :  
  
 [!CODE [csProgGuideArrays#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#9)]  
  
 C\# 3.0 introduit les tableaux implicitement typés.  Pour plus d'informations, consultez [Tableaux implicitement typés](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## Tableaux de types valeur et de types référence  
 Considérons la déclaration de tableau suivante :  
  
 [!CODE [csProgGuideArrays#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#10)]  
  
 Le résultat de cette instruction varie selon que `SomeType` est un type valeur ou un type référence.  S'il s'agit d'un type de valeur, l'instruction crée un tableau de 10 éléments, chacun ayant le type `SomeType`.  Si `SomeType` est un type référence, l'instruction crée un tableau de 10 éléments dont chacun est initialisé à une référence null.  
  
 Pour plus d'informations sur les types valeur et les types référence, consultez [Types](../../../csharp/language-reference/keywords/types.md).  
  
## Voir aussi  
 <xref:System.Array>   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Tableaux](../../../csharp/programming-guide/arrays/index.md)   
 [Tableaux multidimensionnels](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Tableaux en escalier](../../../csharp/programming-guide/arrays/jagged-arrays.md)