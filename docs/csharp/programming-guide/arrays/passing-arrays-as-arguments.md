---
title: "Passage de tableaux en tant qu&#39;arguments (Guide de programmation&#160;C#) | Microsoft Docs"
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
  - "tableaux (C#), passer en tant qu'arguments"
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Passage de tableaux en tant qu&#39;arguments (Guide de programmation&#160;C#)
Les tableaux peuvent être passés en tant qu'arguments aux paramètres de méthode.  Étant donné que les tableaux sont des types référence, la méthode peut modifier la valeur des éléments.  
  
## Passage de tableaux unidimensionnels en tant qu'arguments  
 Vous pouvez passer un tableau unidimensionnel initialisé à une méthode.  Par exemple, l'instruction suivante envoie un tableau à une méthode Print.  
  
 [!CODE [csProgGuideArrays#34](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#34)]  
  
 Le code suivant illustre une implémentation partielle de la méthode Print.  
  
 [!CODE [csProgGuideArrays#33](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#33)]  
  
 Vous pouvez initialiser et passer un nouveau tableau en une seule étape, comme illustré dans l'exemple suivant.  
  
 [!CODE [CsProgGuideArrays#35](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#35)]  
  
## Exemple  
  
### Description  
 Dans l'exemple suivant, un tableau de chaînes est initialisé et passé en tant qu'argument à une méthode `PrintArray` pour des chaînes.  La méthode affiche les éléments du tableau.  Ensuite, les méthodes `ChangeArray` et `ChangeArrayElement` sont appelées pour montrer que l'envoi d'un argument de tableau par valeur n'empêche pas les modifications apportées aux éléments de tableau.  
  
### Code  
 [!CODE [csProgGuideArrays#30](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#30)]  
  
## Passage de tableaux multidimensionnels en tant qu'arguments  
 Vous pouvez passer un tableau multidimensionnel initialisé à une méthode comme un tableau unidimensionnel.  
  
 [!CODE [csProgGuideArrays#41](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#41)]  
  
 Le code suivant illustre une déclaration partielle d'une méthode Print qui accepte un tableau à deux dimensions en tant qu'argument.  
  
 [!CODE [csProgGuideArrays#36](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#36)]  
  
 Vous pouvez initialiser et passer un nouveau tableau en une seule étape, comme illustré dans l'exemple suivant.  
  
 [!CODE [csProgGuideArrays#32](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#32)]  
  
## Exemple  
  
### Description  
 Dans l'exemple suivant, un tableau à deux dimensions d'entiers est initialisé et passé à la méthode `Print2DArray`.  La méthode affiche les éléments du tableau.  
  
### Code  
 [!CODE [csProgGuideArrays#31](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#31)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Tableaux](../../../csharp/programming-guide/arrays/index.md)   
 [Tableaux unidimensionnels](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Tableaux multidimensionnels](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Tableaux en escalier](../../../csharp/programming-guide/arrays/jagged-arrays.md)