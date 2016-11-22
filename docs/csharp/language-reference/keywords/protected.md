---
title: "protected (r&#233;f&#233;rence C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "protected"
  - "protected_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "protected (mot clé C#)"
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# protected (r&#233;f&#233;rence C#)
Le mot clé `protected` est un modificateur d'accès au membre.  Un membre protégé est accessible dans sa classe et depuis les instances de classe dérivée.  Pour obtenir une comparaison entre `protected` et les autres modificateurs d'accès, consultez [Niveaux d'accessibilité](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## Exemple  
 Un membre protégé d'une classe de base est accessible dans une classe dérivée seulement si l'accès s'effectue par le biais du type de la classe dérivée.  Considérons par exemple le segment de code suivant :  
  
 [!CODE [csrefKeywordsModifiers#11](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#11)]  
  
 L'instruction `a.x = 10` génère une erreur car elle figure au sein de la méthode statique Main, et pas dans une instance de la classe B.  
  
 Les membres de struct ne peuvent pas être protégés, car le struct ne peut pas être hérité.  
  
## Exemple  
 Dans cet exemple, la classe `DerivedPoint` est dérivée de `Point`.  Ainsi, vous pouvez accéder aux membres protégés de la classe de base directement à partir de la classe dérivée.  
  
 [!CODE [csrefKeywordsModifiers#12](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#12)]  
  
 Si vous remplacez les niveaux d'accès de `x` et `y` par [private](../../../csharp/language-reference/keywords/private.md), le compilateur affiche les messages d'erreur suivants :  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Mots clés C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificateurs d'accès](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Niveaux d'accessibilité](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificateurs](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [privées](../../../csharp/language-reference/keywords/private.md)   
 [interne](../../../csharp/language-reference/keywords/internal.md)