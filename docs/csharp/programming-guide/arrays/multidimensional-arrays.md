---
title: "Tableaux multidimensionnels (Guide de programmation C#) | Microsoft Docs"
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
  - "tableaux (C#), multidimensionnels"
  - "tableaux multidimensionnels (C#)"
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Tableaux multidimensionnels (Guide de programmation C#)
Les tableaux peuvent avoir plusieurs dimensions.  Par exemple, la déclaration suivante crée un tableau à deux dimensions de quatre lignes et deux colonnes.  
  
 [!CODE [csProgGuideArrays#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#11)]  
  
 La déclaration suivante crée également un tableau à trois dimensions, 4, 2 et 3.  
  
 [!CODE [csProgGuideArrays#12](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#12)]  
  
## Initialisation des tableaux  
 Vous pouvez initialiser le tableau lors de la déclaration, comme le montre l'exemple suivant :  
  
 [!CODE [csProgGuideArrays#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#13)]  
  
 Vous pouvez également initialiser le tableau sans spécifier le rang :  
  
 [!CODE [csProgGuideArrays#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#14)]  
  
 Si vous décidez de déclarer une variable de tableau sans initialisation, vous devez utiliser l'opérateur `new` pour assigner un tableau à cette variable.  L'utilisation de `new` est présentée dans l'exemple suivant.  
  
 [!CODE [csProgGuideArrays#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#15)]  
  
 L'exemple suivant assigne une valeur à un élément de tableau particulier.  
  
 [!CODE [csProgGuideArrays#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#16)]  
  
 De même, l'exemple suivant obtient la valeur d'un élément de tableau particulier et l'assigne à la variable `elementValue`.  
  
 [!CODE [csProgGuideArrays#42](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#42)]  
  
 L'exemple de code suivant initialise les éléments du tableau à leurs valeurs par défaut \(à l'exception des tableaux en escalier\).  
  
 [!CODE [csProgGuideArrays#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#17)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Tableaux](../../../csharp/programming-guide/arrays/index.md)   
 [Tableaux unidimensionnels](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Tableaux en escalier](../../../csharp/programming-guide/arrays/jagged-arrays.md)