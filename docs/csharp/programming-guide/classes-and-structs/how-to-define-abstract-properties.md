---
title: "Comment&#160;: d&#233;finir des propri&#233;t&#233;s abstraites (Guide de programmation C#) | Microsoft Docs"
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
  - "propriétés abstraites (C#)"
  - "propriétés (C#), abstract"
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: d&#233;finir des propri&#233;t&#233;s abstraites (Guide de programmation C#)
L'exemple suivant explique comment définir des propriétés [abstraites](../../../csharp/language-reference/keywords/abstract.md).  Une déclaration de propriété abstraite ne fournit pas une implémentation des accesseurs de propriété ; elle déclare que la classe prend en charge des propriétés, mais laisse l'implémentation de l'accesseur aux classes dérivées.  L'exemple suivant montre comment implémenter les propriétés abstraites héritées d'une classe de base.  
  
 Cet exemple se compose de trois fichiers, dont chacun est compilé individuellement et dont l'assembly produit est référencé par la compilation suivante :  
  
-   abstractshape.cs: la classe `Shape` qui contient une propriété `Area` abstraite.  
  
-   shapes.cs : Les sous\-classes de la classe `Shape`.  
  
-   shapetest.cs : Un programme de test pour afficher des zones de certains objets dérivés de `Shape`.  
  
 Pour compiler l'exemple, utilisez la commande suivante :  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 Cette commande crée le fichier exécutable shapetest.exe.  
  
## Exemple  
 Ce fichier déclare la classe `Shape` qui contient la propriété `Area` du type `double`.  
  
 [!CODE [csProgGuideInheritance#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#1)]  
  
-   Les modificateurs sur la propriété sont placés sur la déclaration de propriété proprement dite.  Par exemple :  
  
    ```  
    public abstract double Area  
    ```  
  
-   Lorsque vous déclarez une propriété abstraite \(telle `Area` dans cet exemple\), vous indiquez simplement quels sont les accesseurs de propriété disponibles, mais vous ne les implémentez pas.  Dans cet exemple, seul un accesseur [get](../../../csharp/language-reference/keywords/get.md) est disponible, donc la propriété est en lecture seule.  
  
## Exemple  
 Le code suivant présente trois sous\-classes de `Shape` qui substituent la propriété `Area` pour fournir leur propre implémentation.  
  
 [!CODE [csProgGuideInheritance#2](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#2)]  
  
## Exemple  
 Le code suivant présente un programme test qui crée un certain nombre d'objets dérivés de `Shape` et imprime les zones correspondantes.  
  
 [!CODE [csProgGuideInheritance#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#3)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Classes et structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Classes abstract et sealed et membres de classe](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [Propriétés](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Comment : créer et utiliser des assemblys à l’aide de la ligne de commande](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)