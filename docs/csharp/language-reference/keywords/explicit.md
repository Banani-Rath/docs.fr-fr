---
title: "explicit (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "explicit_CSharpKeyword"
  - "explicit"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "explicit (mot clé C#)"
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# explicit (r&#233;f&#233;rence C#)
Le mot clé `explicit` déclare un opérateur de conversion de type défini par l'utilisateur qui doit être appelé avec un cast.  Par exemple, cet opérateur convertit d'une classe appelée Fahrenheit en une classe appelée Celsius :  
  
 [!CODE [csrefKeywordsConversion#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsConversion#2)]  
  
 Cet opérateur de conversion peut être appelé comme suit :  
  
 [!CODE [csrefKeywordsConversion#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsConversion#3)]  
  
 L'opérateur de conversion convertit un type source en type cible.  Le type source fournit l'opérateur de conversion.  À la différence de la conversion implicite, les opérateurs de conversion explicite doivent être appelés au moyen d'une conversion.  Si une opération de conversion risque de provoquer des exceptions ou de perdre des informations, vous devez la marquer comme `explicit`.  Ceci empêche le compilateur d'appeler en mode silencieux l'opération de conversion, ce qui pourrait entraîner des conséquences imprévisibles.  
  
 L'omission d'une conversion entraîne l'erreur de compilation CS0266.  
  
 Pour plus d’informations, consultez [Utilisation d'opérateurs de conversion](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## Exemple  
 L'exemple suivant fournit une classe `Fahrenheit` et une classe `Celsius`, chacune fournissant un opérateur de conversion explicite à l'autre classe.  
  
 [!CODE [csrefKeywordsConversion#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsConversion#1)]  
  
## Exemple  
 L'exemple ci\-dessous définit un struct, `Digit`, qui représente un seul chiffre décimal.  Un opérateur est défini pour des conversions de `byte` à `Digit`, et comme tous les octets ne peuvent pas être convertis en `Digit`, la conversion est explicite.  
  
 [!CODE [csrefKeywordsConversion#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsConversion#4)]  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Mots clés C\#](../../../csharp/language-reference/keywords/index.md)   
 [implicites](../../../csharp/language-reference/keywords/implicit.md)   
 [d'opérateur](../../../csharp/language-reference/keywords/operator.md)   
 [Comment : implémenter des conversions définies par l'utilisateur entre des structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)   
 [Conversions explicites définies par l'utilisateur liées en C\#](http://go.microsoft.com/fwlink/?LinkId=112384)