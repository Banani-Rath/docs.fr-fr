---
title: "using, instruction (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "using (instruction C#)"
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# using, instruction (r&#233;f&#233;rence C#)
Fournit une syntaxe qui garantit l'utilisation correcte d'objets <xref:System.IDisposable>.  
  
## Exemple  
 L'exemple suivant montre comment utiliser l'instruction using.  
  
 [!CODE [csrefKeywordsNamespace#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsNamespace#4)]  
  
## Notes  
 <xref:System.IO.File> et <xref:System.Drawing.Font> sont des exemples des types managés qui accèdent aux ressources non managées \(dans ce cas, des handles de fichiers et des contextes de périphérique\).  Beaucoup d'autres types de ressources non managées et de bibliothèques de classes peuvent les encapsuler.  Tous doivent implémenter l'interface <xref:System.IDisposable>.  
  
 En règle générale, lorsque vous utilisez un objet `IDisposable`, vous devez le déclarer et l'instancier dans une instruction `using`.  L'instruction `using` appelle la méthode <xref:System.IDisposable.Dispose%2A> sur l'objet et, si vous l'utilisez comme indiqué précédemment, met l'objet hors de portée dès que <xref:System.IDisposable.Dispose%2A> est appelé.  Dans le bloc `using`, l'objet est en lecture seule et ne peut être ni modifié ni réassigné.  
  
 L'instruction `using` garantit que <xref:System.IDisposable.Dispose%2A> est appelé même si une exception se produit lors de l'appel de méthodes sur l'objet.  Vous pouvez obtenir le même résultat en plaçant l'objet dans un bloc try puis en appelant <xref:System.IDisposable.Dispose%2A> dans un bloc finally ; c'est d'ailleurs ainsi que l'instruction `using` est traduite par le compilateur.  L'exemple de code précédent se développe vers le code suivant à la compilation \(notez les accolades supplémentaires qui limitent la portée de l'objet\) :  
  
 [!CODE [csrefKeywordsNamespace#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsNamespace#5)]  
  
 Plusieurs instances d'un type peuvent être déclarées dans une instruction `using`, comme indiqué dans l'exemple suivant.  
  
 [!CODE [csrefKeywordsNamespace#6](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsNamespace#6)]  
  
 Il n'est pas conseillé d'instancier l'objet de ressource puis de passer la variable à l'instruction `using`.  En effet, l'objet reste dans la portée une fois que le contrôle a quitté le bloc `using`, même s'il ne peut probablement plus accéder à ses ressources non managées.  En d'autres termes, il ne sera plus complètement initialisé.  Si vous essayez d'utiliser l'objet à l'extérieur du bloc `using`, vous risquez de provoquer la levée d'une exception.  C'est pourquoi il vaut mieux instancier l'objet dans l'instruction `using` et limiter sa portée au bloc `using`.  
  
 [!CODE [csrefKeywordsNamespace#7](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsNamespace#7)]  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Mots clés C\#](../../../csharp/language-reference/keywords/index.md)   
 [using, directive](../../../csharp/language-reference/keywords/using-directive.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)   
 [Implementing a Dispose Method](../Topic/Implementing%20a%20Dispose%20Method.md)