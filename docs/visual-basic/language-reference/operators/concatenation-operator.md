---
title: "&amp; Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.&"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "And (&) operator"
  - "ampersand operator (&)"
  - "& operator"
  - "concatenation operators, syntax"
  - "strings [Visual Basic], concatenating"
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &amp; Operator (Visual Basic)
Génère une concaténation de chaînes de deux expressions.  
  
## Syntaxe  
  
```  
  
result = expression1 & expression2  
```  
  
## Composants  
 `result`  
 Obligatoire.  Toute variable `String` ou `Object`.  
  
 `expression1`  
 Obligatoire.  Toute expression avec un type de données qui s'étend à `String`.  
  
 `expression2`  
 Obligatoire.  Toute expression avec un type de données qui s'étend à `String`.  
  
## Notes  
 Si le type de données de `expression1` ou `expression2` n'est pas `String`, mais s'étend à `String`, il est converti en `String`.  Si l'un des types de données ne s'étend pas à `String`, le compilateur génère une erreur.  
  
 Le type de données de `result` est `String`.  Si une ou deux expressions correspondent à [Rien](../../../visual-basic/language-reference/nothing.md) ou ont une valeur de <xref:System.DBNull.Value?displayProperty=fullName>, elles sont traitées comme une chaîne avec une valeur de "".  
  
> [!NOTE]
>  L'opérateur `&` peut être *surchargé*, ce qui signifie qu'une classe ou une structure peut redéfinir son comportement lorsqu'un opérande a le type de cette classe ou de cette structure.  Si votre code utilise cet opérateur sur une telle classe ou structure, assurez\-vous que vous comprenez son comportement redéfini.  Pour plus d'informations, consultez [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  Le caractère & peut également être utilisé pour identifier des variables comme type `Long`.  Pour plus d'informations, consultez [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## Exemple  
 Cet exemple utilise l'opérateur `&` pour forcer la concaténation de chaînes.  Le résultat est une valeur de chaîne représentant la concaténation des deux opérandes de chaîne.  
  
 [!CODE [VbVbalrOperators#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#2)]  
  
## Voir aussi  
 [&\= Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Concatenation Operators](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Concatenation Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)