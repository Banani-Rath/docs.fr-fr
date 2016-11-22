---
title: "new, contrainte (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "new constraint (mot clé C#)"
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# new, contrainte (r&#233;f&#233;rence C#)
La contrainte `new` spécifie que tout argument de type dans une déclaration de classe générique doit avoir un constructeur sans paramètre public.  Pour pouvoir utiliser la nouvelle contrainte, le type ne peut pas être abstrait.  
  
## Exemple  
 Appliquez la contrainte `new` à un paramètre de type lorsque votre classe générique crée des instances du type, comme le montre l'exemple suivant :  
  
 [!CODE [csrefKeywordsOperator#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#5)]  
  
## Exemple  
 Lorsque vous utilisez la contrainte `new()` avec d'autres contraintes, elle doit être spécifiée en dernier :  
  
 [!CODE [csrefKeywordsOperator#6](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#6)]  
  
 Pour plus d'informations, consultez [Contraintes sur les paramètres de type](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 <xref:System.Collections.Generic>   
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Mots clés C\#](../../../csharp/language-reference/keywords/index.md)   
 [Mots clés des opérateurs](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Génériques](../../../csharp/programming-guide/generics/index.md)