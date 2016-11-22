---
title: "Passage de param&#232;tres de type valeur (Guide de programmation C#) | Microsoft Docs"
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
  - "paramètres de méthode (C#), types valeur"
  - "paramètres (C#), valeur"
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Passage de param&#232;tres de type valeur (Guide de programmation C#)
Une variable de [type valeur](../../../csharp/language-reference/keywords/value-types.md) contient directement les données, contrairement à une variable de [type référence](../../../csharp/language-reference/keywords/reference-types.md), qui contient une référence aux données.  Passez une variable de type valeur à une méthode par valeur signifie passer une copie de la variable à la méthode.  En se transforme en paramètre qui ont lieu dans la méthode n'ont aucune incidence sur les données d'origine stockées dans la variable d'arguments.  Si vous souhaitez que la méthode appelée pour modifier la valeur du paramètre, vous devez le passer par référence, à l'aide de le mot clé de [référence](../../../csharp/language-reference/keywords/ref.md) ou de.  Par souci de simplicité, les exemples qui suivent utilisent `ref`.  
  
## Passage de types valeur par valeur  
 L'exemple suivant illustre le passage de paramètres de type valeur par valeur.  La variable `n` est passée par valeur à la méthode `SquareIt`.  Les modifications intervenant au sein de la méthode n'affectent en rien la valeur d'origine de la variable.  
  
 [!CODE [csProgGuideParameters#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideParameters#3)]  
  
 `n` variable est un type valeur.  il contient ses données, la valeur `5`.  Lorsque la méthode `SquareIt` est appelée, le contenu de la variable `n` est copié dans le paramètre `x`, qui est mis au carré au sein de la méthode.  Dans `Main`, toutefois, la valeur d' `n` est identique après avoir appelé la méthode d' `SquareIt` comme initial.  La modification qui a lieu à l'intérieur de la méthode affecte uniquement la variable locale `x`.  
  
## Passage de types valeur par référence  
 L'exemple suivant est identique à l'exemple précédent, mais que l'argument est passé comme paramètre d' `ref` .  La valeur de l'argument sous\-jacent, `n`, change lorsque `x` est modifié dans la méthode.  
  
 [!CODE [csProgGuideParameters#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideParameters#4)]  
  
 Dans cet exemple, ce n'est pas la valeur de la variable `n` qui est passée, mais une référence de `n`.  Le paramètre `x` n'est pas [int](../../../csharp/language-reference/keywords/int.md) ; il s'agit d'une référence à `int`, dans ce cas, une référence à `n`.  Par conséquent, lorsque `x` est élevée au carré dans la méthode, ce qui est élevée au carré réellement ce qu' `x` fait référence, est `n`.  
  
## Permutation de types valeur  
 Un exemple courant de modifier les valeurs des arguments est une méthode d'échange, que vous passez deux variables à la méthode, et la méthode fait passer leur contenu.  Vous devez passer des arguments à la méthode d'échange par référence.  Sinon, vous permute les copies locales des paramètres dans la méthode, et aucune modification n'est effectuée dans la méthode.  L'exemple suivant fait passer des valeurs entières.  
  
 [!CODE [csProgGuideParameters#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideParameters#5)]  
  
 Lorsque vous appelez la méthode d' `SwapByRef` , utilisez le mot clé d' `ref` dans l'appel, comme indiqué dans l'exemple suivant.  
  
 [!CODE [csProgGuideParameters#6](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideParameters#6)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Passage de paramètres](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [Passage de paramètres de type référence](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)