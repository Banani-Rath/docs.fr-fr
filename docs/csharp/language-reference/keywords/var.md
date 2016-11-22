---
title: "var (R&#233;f&#233;rence&#160;C#) | Microsoft Docs"
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
  - "var"
  - "var_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "var (mot clé C#)"
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# var (R&#233;f&#233;rence&#160;C#)
À partir de Visual C\# 3.0, les variables déclarées à la portée de la méthode peuvent avoir un type implicite `var`.  Une variable locale implicitement typée est fortement typée comme si vous aviez déclaré le type vous\-même, mais le compilateur détermine le type.  Les deux déclarations suivantes d'`i` sont équivalentes fonctionnellement :  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 Pour plus d'informations, consultez [Variables locales implicitement typées](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) et [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## Exemple  
 L'exemple suivant présente deux expressions de requête.  Dans la première expression, l'utilisation de `var` est autorisée mais n'est pas requise, parce que le type du résultat de la requête peut être déclaré explicitement comme un `IEnumerable<string>`.  Toutefois, `var` doit être utilisé dans la deuxième expression, parce que le résultat est une collection de types anonymes, et le nom de ce type n'est pas accessible sauf par le compilateur.  Notez que dans le deuxième exemple, la variable d'itération `foreach` `item` doit également être typée implicitement.  
  
 [!CODE [csrefKeywordsTypes#18](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#18)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Variables locales implicitement typées](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)