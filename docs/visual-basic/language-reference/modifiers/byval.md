---
title: "ByVal (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ByVal"
  - "ByVal"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ByVal keyword, contexts"
  - "ByVal keyword"
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# ByVal (Visual Basic)
Spécifie qu'un argument est passé de telle manière que la procédure ou la propriété appelée ne peut pas changer la valeur d'une variable sous\-jacente à l'argument dans le code appelant.  
  
## Notes  
 Le modificateur `ByVal` peut être utilisé dans les contextes suivants :  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Exemple  
 L'exemple suivant montre l'utilisation du paramètre `ByVal` qui passe le mécanisme avec un argument de type référence.  Dans cet exemple, l'argument est `c1`, une instance de la classe `Class1`.  `ByVal` empêche le code dans les procédures de modifier la valeur sous\-jacente de l'argument de référence, `c1`, mais ne protège pas les champs et les propriétés accessibles de `c1`.  
  
 [!CODE [VbVbalrKeywords#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrKeywords#10)]  
  
## Voir aussi  
 [Mots clés](../../../visual-basic/language-reference/keywords/index.md)   
 [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)