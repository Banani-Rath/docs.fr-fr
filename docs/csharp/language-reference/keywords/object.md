---
title: "object (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "object_CSharpKeyword"
  - "object"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "object (mot clé C#)"
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# object (r&#233;f&#233;rence C#)
Le type `object` est un alias pour <xref:System.Object> dans .NET Framework.  Dans le système de type unifié de C\#, tous les types, prédéfinis et définis par l'utilisateur, les types référence et les types valeur, héritent directement ou indirectement de <xref:System.Object>.  Vous pouvez assigner des valeurs de tout type à des variables de type `object`.  Lorsqu'une variable d'un type valeur est convertie en objet, elle est dite *boxed*.  Lorsqu'une variable de type objet est convertie en un type valeur, elle est dite *unboxed*.  Pour plus d'informations, consultez [Conversion boxing et unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## Exemple  
 L'exemple suivant illustre comment les variables de type `object` peuvent accepter des valeurs de tout type de données et comment les variables de type `object` peuvent utiliser des méthodes sur <xref:System.Object> à partir du .NET Framework.  
  
 [!CODE [csrefKeywordsTypes#16](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#16)]  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Mots clés C\#](../../../csharp/language-reference/keywords/index.md)   
 [Types référence](../../../csharp/language-reference/keywords/reference-types.md)   
 [Types valeur](../../../csharp/language-reference/keywords/value-types.md)