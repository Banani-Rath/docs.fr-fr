---
title: "Or Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.Or"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Or operator"
  - "operators [Visual Basic], bitwise"
  - "inclusive Or operator"
  - "bitwise operators, OR operator"
  - "Or keyword"
  - "operators [Visual Basic], inclusive or"
  - "operators [Visual Basic], disjunction"
  - "bitwise comparison"
  - "logical disjunction"
  - "disjunction operator"
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Or Operator (Visual Basic)
Effectue une disjonction logique sur deux expressions `Boolean` ou une disjonction d'opérations de bits sur deux expressions numériques.  
  
## Syntaxe  
  
```  
  
result = expression1 Or expression2  
```  
  
## Composants  
 `result`  
 Obligatoire.  Toute expression `Boolean` ou numérique.  Pour la comparaison `Boolean`, `result` est la disjonction logique inclusive de deux valeurs `Boolean`.  Pour les opérations au niveau du bit, `result` est une valeur numérique qui représente la disjonction de bits inclusive de deux modèles binaires numériques.  
  
 `expression1`  
 Obligatoire.  Toute expression `Boolean` ou numérique.  
  
 `expression2`  
 Obligatoire.  Toute expression `Boolean` ou numérique.  
  
## Notes  
 Pour la comparaison `Boolean`, `result` est `False` si et uniquement si `expression1` et `expression2` ont la valeur `False`.  Le tableau suivant illustre la manière dont `result` est déterminé.  
  
|Si `expression1` est :|Et `expression2` a la valeur|La valeur de `result` est|  
|----------------------------|----------------------------------|-------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  Dans une comparaison `Boolean`, l'opérateur `Or` évalue toujours les deux expressions qui pourraient inclure des appels de procédure.  [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) exécute le *court\-circuit*, ce qui signifie que si `expression1` a la valeur `True`, `expression2` n'est pas évalué.  
  
 Pour les opérations au niveau du bit, l'opérateur `Or` effectue une comparaison de bits de position identique dans deux expressions numériques et définit le bit correspondant dans `result` d'après le tableau suivant :  
  
|Si le bit dans `expression1` a la valeur|Et si le bit dans `expression2` a la valeur|Le bit dans `result` a la valeur|  
|----------------------------------------------|-------------------------------------------------|--------------------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Compte tenu que les opérateurs logiques et de bits ont une priorité inférieure à celle des opérateurs arithmétiques et relationnels, toutes les opérations au niveau du bit doivent être mises entre parenthèses afin de garantir une exécution précise.  
  
## Types de données  
 Si les opérandes se composent d'une expression `Boolean` et d'une expression numérique, Visual Basic convertit l'expression `Boolean` en une valeur numérique \(–1 pour `True` et 0 pour `False`\) et exécute une opération au niveau du bit.  
  
 Pour une comparaison `Boolean`, le type de données du résultat est `Boolean`.  Pour une comparaison de bits, le type de données du résultat est un type numérique approprié pour les types de données de `expression1` et `expression2`.  Consultez le tableau « Relational and Bitwise Comparisons » dans [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## Surcharge  
 L'opérateur `Or` peut être *surchargé*, ce qui signifie qu'une classe ou une structure peut redéfinir son comportement lorsqu'un opérande a le type de cette classe ou de cette structure.  Si votre code utilise cet opérateur sur une telle classe ou structure, assurez\-vous que vous comprenez son comportement redéfini.  Pour plus d'informations, consultez [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Exemple  
 L'exemple suivant utilise l'opérateur `Or` pour effectuer une disjonction logique inclusive sur deux expressions.  Le résultat est une valeur `Boolean` qui indique si l'une des deux expressions est `True`.  
  
 [!CODE [VbVbalrOperators#35](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#35)]  
  
 L'exemple précédent produit respectivement les résultats suivants : `True`, `True` et `False`.  
  
## Exemple  
 L'exemple suivant utilise l'opérateur `Or` pour effectuer une exclusion logique inclusive sur les bits individuels de deux expressions numériques.  Le bit du modèle de résultat est défini si un des bits correspondants dans les opérandes a la valeur 1.  
  
 [!CODE [VbVbalrOperators#36](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#36)]  
  
 L'exemple précédent produit respectivement les résultats suivants : 10, 14 et 14.  
  
## Voir aussi  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)