---
title: "Interfaces g&#233;n&#233;riques (guide de programmation C#) | Microsoft Docs"
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
  - "langage C#, interfaces génériques"
  - "génériques (C#), interfaces"
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Interfaces g&#233;n&#233;riques (guide de programmation C#)
Il est souvent utile de définir des interfaces pour les classes de collection génériques, ou pour les classes génériques qui représentent des éléments dans la collection.  Pour les classes génériques, il est préférable d'utiliser des interfaces génériques, telles que <xref:System.IComparable%601> à la place de <xref:System.IComparable>, pour éviter les opérations de boxing et d'unboxing sur les types valeur.  La bibliothèque de classes .NET Framework définit plusieurs nouvelles interfaces génériques à utiliser avec les classes de collection dans l'espace de noms <xref:System.Collections.Generic>.  
  
 Lorsqu'une interface est spécifiée comme une contrainte sur un paramètre de type, seuls les types qui implémentent l'interface peuvent être utilisés.  L'exemple de code suivant illustre une classe `SortedList<T>` qui dérive de la classe `GenericList<T>`.  Pour plus d'informations, consultez [Introduction aux génériques](../../../csharp/programming-guide/generics/introduction-to-generics.md).  `SortedList<T>` ajoute la contrainte `where T : IComparable<T>`.  Ceci permet à la méthode `BubbleSort` dans `SortedList<T>` d'utiliser la méthode générique <xref:System.IComparable%601.CompareTo%2A> sur les éléments de liste.  Dans cet exemple, les éléments de liste sont une classe simple, `Person` qui implémente `IComparable<Person>`.  
  
 [!CODE [csProgGuideGenerics#29](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#29)]  
  
 Les interfaces multiples peuvent être spécifiées en tant que contraintes sur un seul type, comme suit :  
  
 [!CODE [csProgGuideGenerics#30](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#30)]  
  
 Une interface peut définir plusieurs paramètres de type, comme suit :  
  
 [!CODE [csProgGuideGenerics#31](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#31)]  
  
 Les règles d'héritage qui s'appliquent aux classes s'appliquent également aux interfaces :  
  
 [!CODE [csProgGuideGenerics#32](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#32)]  
  
 Les interfaces génériques peuvent hériter d'interfaces non génériques si l'interface générique est de type contravariant, ce qui signifie qu'elle utilise uniquement son paramètre de type comme valeur de retour.  Dans la bibliothèque de classes .NET Framework, <xref:System.Collections.Generic.IEnumerable%601> hérite de <xref:System.Collections.IEnumerable>, car <xref:System.Collections.Generic.IEnumerable%601> utilise uniquement `T` dans la valeur de retour de <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> et dans l'accesseur Get de propriété <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.  
  
 Les classes concrètes peuvent implémenter des interfaces construites fermées, comme suit :  
  
 [!CODE [csProgGuideGenerics#33](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#33)]  
  
 Les classes génériques peuvent implémenter des interfaces génériques ou des interfaces construites fermées tant que la liste de paramètres de classe fournit tous les arguments requis par l'interface, comme suit :  
  
 [!CODE [csProgGuideGenerics#34](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#34)]  
  
 Les règles qui déterminent la surcharge des méthodes sont les mêmes pour les méthodes dans les classes génériques, les structs génériques ou les interfaces génériques.  Pour plus d'informations, consultez [Méthodes génériques](../../../csharp/programming-guide/generics/generic-methods.md).  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Introduction aux génériques](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [interface](../../../csharp/language-reference/keywords/interface.md)   
 [Génériques](../Topic/Generics%20in%20the%20.NET%20Framework.md)