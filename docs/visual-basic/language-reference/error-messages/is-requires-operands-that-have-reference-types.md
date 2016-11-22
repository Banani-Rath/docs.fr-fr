---
title: "&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30020"
  - "vbc30020"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30020"
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;
L'opérateur de comparaison `Is` détermine si deux variables objets font référence à la même instance.  Cette comparaison n'est pas définie pour les types valeur.  
  
 **ID d'erreur :** BC30020  
  
### Pour corriger cette erreur  
  
-   Utilisez l'opérateur de comparaison arithmétique approprié ou l'opérateur `Like` pour comparer deux types valeur.  
  
## Voir aussi  
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)   
 [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md)   
 [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md)