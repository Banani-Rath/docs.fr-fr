---
title: "typeof (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "typeof"
  - "typeof_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "typeof (mot clé C#)"
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# typeof (r&#233;f&#233;rence C#)
Sert à obtenir l'objet `System.Type` d'un type.  Une expression `typeof` prend la forme suivante :  
  
```  
System.Type type = typeof(int);  
```  
  
## Notes  
 Pour obtenir le type d'exécution d'une expression, vous pouvez utiliser la méthode <xref:System.Object.GetType%2A> du .NET Framework, comme dans l'exemple suivant :  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 L'opérateur `typeof` ne peut pas être surchargé.  
  
 L'opérateur `typeof` peut également être utilisé sur les types génériques ouverts.  Les types ayant plusieurs paramètres de type doivent présenter le nombre approprié de virgules dans leur spécification.  L'exemple suivant indique comment déterminer si le type de retour d'une méthode est un <xref:System.Collections.Generic.IEnumerable%601> générique.  Supposez que la méthode est une instance de type MethodInfo :  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## Exemple  
 [!CODE [csrefKeywordsOperator#12](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#12)]  
  
## Exemple  
 Cet exemple utilise la méthode <xref:System.Object.GetType%2A> pour déterminer le type utilisé pour contenir le résultat d'un calcul numérique.  Cela dépend des besoins en mémoire du nombre résultant.  
  
 [!CODE [csrefKeywordsOperator#13](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#13)]  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 <xref:System.Type?displayProperty=fullName>   
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Mots clés C\#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Mots clés des opérateurs](../../../csharp/language-reference/keywords/operator-keywords.md)