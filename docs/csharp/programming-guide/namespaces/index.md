---
title: "Espaces de noms (Guide de programmation C#) | Microsoft Docs"
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
  - "langage C#, espaces de noms"
  - "espaces de noms (C#)"
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Espaces de noms (Guide de programmation C#)
Les espaces de noms sont énormément employés en programmation C\#, de deux manières.  Premièrement, le .NET Framework utilise des espaces de noms pour organiser ses nombreuses classes, comme suit :  
  
 [!CODE [csProgGuide#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#22)]  
  
 `System` est un espace de noms et `Console` est une classe dans cet espace de noms.  Le mot clé `using` peut être utilisé pour le nom complet ne soit pas requis, comme dans l'exemple suivant :  
  
 [!CODE [csProgGuide#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#1)]  
  
 [!CODE [csProgGuide#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#25)]  
  
 Pour plus d'informations, consultez [using, directive](../../../csharp/language-reference/keywords/using-directive.md).  
  
 Deuxièmement, déclarer ses propres espaces de noms peut vous aider à contrôler la portée des noms de classes et de méthodes dans les projets de programmation plus volumineux.  Utilisez le mot clé [namespace](../../../csharp/language-reference/keywords/namespace.md) pour déclarer un espace de noms, comme dans l'exemple suivant :  
  
 [!CODE [csProgGuideNamespaces#6](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#6)]  
  
## Vue d'ensemble des espaces de noms  
 Les espaces de noms possèdent les propriétés suivantes :  
  
-   Ils organisent les grands projets de code.  
  
-   Ils sont délimités avec l'opérateur `.`.  
  
-   La `using directive` signifie que vous n'avez pas besoin de spécifier le nom de l'espace de noms pour chaque classe.  
  
-   L'espace de noms `global` est l'espace de noms « racine » : `global::System` fera toujours référence à l'espace de noms .NET Framework `System`.  
  
## Rubriques connexes  
 Pour plus d'informations sur les espaces de noms, consultez les rubriques suivantes :  
  
-   [Utilisation d'espaces de noms](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Comment : utiliser l'alias d'espace de noms global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [Comment : utiliser l'espace de noms My](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Mots clés d'espaces de noms](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [using, directive](../../../csharp/language-reference/keywords/using-directive.md)   
 [::, opérateur](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [. Opérateur](../../../csharp/language-reference/operators/member-access-operator.md)