---
title: "Comment&#160;: utiliser l&#39;alias d&#39;espace de noms global (Guide de programmation C#) | Microsoft Docs"
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
  - "alias (C#)"
  - "espace de noms global (C#)"
  - "espaces de noms (C#), qualificateur d'espace de noms global"
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: utiliser l&#39;alias d&#39;espace de noms global (Guide de programmation C#)
La capacité d'accéder à un membre dans l'[espace de noms](../../../csharp/language-reference/keywords/namespace.md) global est utile lorsque le membre peut être masqué par une autre entité du même nom.  
  
 Par exemple, dans le code suivant, `Console` se résout en `TestApp.Console` au lieu du type `Console` dans l'espace de noms <xref:System>.  
  
 [!CODE [csProgGuide#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#1)]  
  
 [!CODE [csProgGuideNamespaces#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#1)]  
  
 Utiliser `System.Console` produit encore une erreur, car l'espace de noms `System` est masqué par la classe `TestApp.System` :  
  
 [!CODE [csProgGuideNamespaces#2](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#2)]  
  
 Toutefois, vous pouvez contourner cette erreur en utilisant `global::System.Console`, comme ceci :  
  
 [!CODE [csProgGuideNamespaces#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#3)]  
  
 Lorsque l'identificateur gauche est `global`, la recherche de l'identificateur droit commence à l'espace de noms global.  Par exemple, la déclaration suivante référence `TestApp` comme membre de l'espace global.  
  
 [!CODE [csProgGuideNamespaces#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#4)]  
  
 Évidemment, créer vos propres espaces de noms appelés `System` n'est pas recommandé, et il est peu probable que vous rencontriez jamais de code dans lequel cela se soit produit.  Toutefois, dans les projets de plus grande taille, il est tout à fait probable que la duplication d'espaces de noms se produise, sous une forme ou sous une autre.  Dans ces situations, le qualificateur d'espace de noms global vous garantit que vous pouvez spécifier l'espace de noms racine.  
  
## Exemple  
 Dans cet exemple, l'espace de noms `System` est utilisé pour inclure la classe `TestClass`. Par conséquent, `global::System.Console` doit être utilisé pour référencer la classe `System.Console`, qui est masquée par l'espace de noms `System`.  Par ailleurs, l'alias `colAlias` est utilisé pour faire référence à l'espace de noms `System.Collections`. Par conséquent, l'instance d'une <xref:System.Collections.Hashtable?displayProperty=fullName> a été créée à l'aide de cet alias plutôt que de l'espace de noms.  
  
 [!CODE [csProgGuideNamespaces#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#5)]  
  
  **A 1**  
**B 2**  
**C 3**   
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Espaces de noms](../../../csharp/programming-guide/namespaces/index.md)   
 [. Opérateur](../../../csharp/language-reference/operators/member-access-operator.md)   
 [::, opérateur](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)