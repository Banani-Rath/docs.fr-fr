---
title: "Comment&#160;: impl&#233;menter des conversions d&#233;finies par l&#39;utilisateur entre des structs (Guide de programmation C#) | Microsoft Docs"
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
  - "conversions définies par l'utilisateur (C#)"
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: impl&#233;menter des conversions d&#233;finies par l&#39;utilisateur entre des structs (Guide de programmation C#)
L'exemple suivant définit deux structures, `RomanNumeral` et `BinaryNumeral`, et décrit les conversions entre ces deux structures.  
  
## Exemple  
 [!CODE [csProgGuideStatements#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#13)]  
  
## Programmation fiable  
  
-   Dans l'exemple précédent, l'instruction :  
  
     [!CODE [csProgGuideStatements#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#14)]  
  
     convertit un `RomanNumeral` en `BinaryNumeral`.  Étant donné qu'il n'existe pas de conversion directe de `RomanNumeral` vers `BinaryNumeral`, un cast est utilisé pour convertir un `RomanNumeral` en un `int` et un autre cast pour convertir ce dernier en un `BinaryNumeral`.  
  
-   L'instruction  
  
     [!CODE [csProgGuideStatements#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#15)]  
  
     convertit un `BinaryNumeral` en `RomanNumeral`.  Étant donné que `RomanNumeral` définit une conversion implicite d'un `BinaryNumeral`, aucun cast n'est requis.  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Conversion, opérateurs](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)