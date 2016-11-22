---
title: "Tableaux en escalier (Guide de programmation C#) | Microsoft Docs"
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
  - "tableaux (C#), en escalier"
  - "tableaux en escalier (C#)"
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Tableaux en escalier (Guide de programmation C#)
Un tableau en escalier est un tableau dont les éléments sont des tableaux.  Les éléments d'un tableau en escalier peuvent être de dimensions et de tailles différentes.  Un tableau en escalier est parfois appelé « tableau de tableaux ». Les exemples suivants indiquent comment déclarer, initialiser et accéder à des tableaux en escalier.  
  
 L'exemple suivant est une déclaration de tableau à une dimension qui possède trois éléments, chacun étant un tableau unidimensionnel d'entiers :  
  
 [!CODE [csProgGuideArrays#19](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#19)]  
  
 Avant de pouvoir utiliser `jaggedArray`, vous devez initialiser ses éléments.  Vous pouvez procéder ainsi :  
  
 [!CODE [csProgGuideArrays#20](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#20)]  
  
 Chaque élément est un tableau unidimensionnel d'entiers.  Le premier élément est un tableau de cinq entiers, le deuxième est un tableau de quatre entiers et le troisième est un tableau de deux entiers.  
  
 Il est également possible d'utiliser des initialiseurs pour attribuer des valeurs aux éléments du tableau, auquel cas vous n'avez pas besoin de la taille du tableau.  Par exemple :  
  
 [!CODE [csProgGuideArrays#21](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#21)]  
  
 Vous pouvez également initialiser le tableau dans la déclaration, comme ceci :  
  
 [!CODE [csProgGuideArrays#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#22)]  
  
 Vous pouvez utiliser la forme abrégée suivante.  Vous ne pouvez pas omettre l'opérateur `new` dans les éléments d'initialisation car aucune initialisation n'est prévue par défaut pour eux :  
  
 [!CODE [csProgGuideArrays#23](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#23)]  
  
 Un tableau en escalier est un tableau de tableaux, et par conséquent ses éléments sont des types référence et sont initialisés à `null`.  
  
 Vous pouvez accéder aux différents éléments du tableau comme dans ces exemples :  
  
 [!CODE [csProgGuideArrays#24](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#24)]  
  
 Il est possible de combiner tableaux en escalier et tableaux multidimensionnels.  Ce qui suit est une déclaration et une initialisation d'un tableau en escalier unidimensionnel qui contient trois éléments de tableau à deux dimensions de tailles différentes :  Pour plus d'informations sur les tableaux à deux dimensions, consultez [Tableaux multidimensionnels](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!CODE [csProgGuideArrays#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#25)]  
  
 Vous avez accès aux différents éléments comme le montre cet exemple, qui affiche la valeur de l'élément `[1,0]` du premier tableau \(valeur `5`\) :  
  
 [!CODE [csProgGuideArrays#26](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#26)]  
  
 La méthode `Length` retourne le nombre de tableaux contenu dans le tableau en escalier.  Par exemple, si vous avez déclaré le tableau précédent, cette ligne :  
  
 [!CODE [csProgGuideArrays#27](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#27)]  
  
 retourne la valeur 3.  
  
## Exemple  
 Cet exemple génère un tableau, dont les éléments sont eux\-mêmes des tableaux.  Chacun des éléments du tableau a une taille différente.  
  
 [!CODE [csProgGuideArrays#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#18)]  
  
## Voir aussi  
 <xref:System.Array>   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Tableaux](../../../csharp/programming-guide/arrays/index.md)   
 [Tableaux unidimensionnels](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Tableaux multidimensionnels](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)