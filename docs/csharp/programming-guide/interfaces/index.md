---
title: "Interfaces (Guide de programmation&#160;C#) | Microsoft Docs"
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
  - "langage C#, interfaces"
  - "interfaces (C#)"
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
caps.latest.revision: 45
caps.handback.revision: 45
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Interfaces (Guide de programmation&#160;C#)
Une interface contient des définitions pour un groupe de fonctionnalités connexes qu'une [classe](../../../csharp/language-reference/keywords/class.md) ou un [struct](../../../csharp/language-reference/keywords/struct.md) peuvent implémenter.  
  
 En utilisant des interfaces, vous pouvez, par exemple, inclure le comportement de plusieurs sources dans une classe.  Cette fonctionnalité est importante en C\#, car le langage ne prend pas en charge l'héritage multiple de classes.  De plus, vous devez utiliser une interface si vous voulez simuler l'héritage pour des structs, car ils ne peuvent en fait pas hériter d'un autre struct ou d'une autre classe.  
  
 Vous définissez une interface à l'aide du mot clé [interface](../../../csharp/language-reference/keywords/interface.md), comme le montre l'exemple suivant.  
  
 [!CODE [csProgGuideInheritance#47](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#47)]  
  
 Toute classe ou tout struct qui implémentent l'interface <xref:System.IEquatable%601> doivent contenir une définition pour une méthode <xref:System.IEquatable%601.Equals%2A> qui correspond à la signature spécifiée par l'interface.  Ainsi, vous pouvez compter sur une classe qui implémente `IEquatable<T>` pour contenir une méthode `Equals` avec laquelle une instance de la classe peut déterminer si elle est égale à une autre instance de la même classe.  
  
 La définition de `IEquatable<T>` ne fournit pas d'implémentation pour `Equals`.  L'interface définit uniquement la signature.  De cette façon, une interface en C\# est semblable à une classe abstraite dans laquelle toutes les méthodes sont abstraites.  En revanche, une classe ou un struct peuvent implémenter plusieurs interfaces, mais une classe peut uniquement hériter d'une seule classe, abstraite ou non.  Ainsi, en utilisant des interfaces, vous pouvez inclure le comportement de plusieurs sources dans une classe.  
  
 Pour plus d'informations sur les classes abstraites, consultez [Classes abstract et sealed et membres de classe](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Les interfaces peuvent contenir des méthodes, propriétés, événements, indexeurs ou toute combinaison de ces quatre types de membres.  Pour obtenir des liens vers des exemples, consultez [Rubriques connexes](../../../csharp/programming-guide/interfaces/index.md#BKMK_RelatedSections).  Une interface ne peut pas contenir de constantes, champs, opérateurs, constructeurs d'instance, destructeurs ou types.  Les membres d'interface sont automatiquement publics et ils ne peuvent pas inclure de modificateurs d'accès.  Les membres ne peut également pas être [statiques](../../../csharp/language-reference/keywords/static.md).  
  
 Pour implémenter un membre d'interface, le membre correspondant de la classe d'implémentation doit être public, non statique et porter le même nom et la même signature que le membre d'interface.  
  
 Quand une classe ou un struct implémentent une interface, la classe ou le struct doivent fournir une implémentation pour tous les membres que l'interface définit.  L'interface elle\-même n'offre aucune fonctionnalité dont une classe ou un struct peuvent hériter de la manière qu'ils peuvent hériter d'une fonctionnalité de classe de base.  Toutefois, si une classe de base implémente une interface, toute classe dérivée de la classe de base hérite de cette implémentation.  
  
 L'exemple suivant illustre une implémentation de l'interface IEquatable\<T\>.  La classe d'implémentation, `Car`, doit fournir une implémentation de la méthode <xref:System.IEquatable%601.Equals%2A>.  
  
 [!CODE [csProgGuideInheritance#48](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#48)]  
  
 Les propriétés et indexeurs d'une classe peuvent définir des accesseurs supplémentaires pour une propriété ou un indexeur qui est défini dans une interface.  Par exemple, une interface peut déclarer une propriété qui a un accesseur [get](../../../csharp/language-reference/keywords/get.md).  La classe qui implémente l'interface peut déclarer la même propriété avec à la fois un accesseur `get` et un accesseur [set](../../../csharp/language-reference/keywords/set.md).  Toutefois, si la propriété ou l'indexeur utilisent une implémentation explicite, les accesseurs doivent correspondre.  Pour plus d'informations sur l'implémentation explicite, consultez [Implémentation d’interface explicite](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) et [Propriétés d'interface](../../../csharp/programming-guide/classes-and-structs/interface-properties.md).  
  
 Les interfaces peuvent implémenter d'autres interfaces.  Une classe peut inclure une interface plusieurs fois par le biais de classes de base qu'elle hérite ou d'interfaces que d'autres interfaces implémentent.  Toutefois, la classe peut fournir une implémentation d'une interface une seule fois et uniquement si la classe déclare l'interface dans le cadre de la définition de la classe \(`class ClassName : InterfaceName`\).  Si l'interface est héritée car vous avez hérité d'une classe de base qui implémente l'interface, la classe de base fournit l'implémentation des membres de l'interface.  Toutefois, la classe dérivée peut implémenter de nouveau les membres d'interface au lieu d'utiliser l'implémentation héritée.  
  
 Une classe de base peut également implémenter des membres d'interface à l'aide de membres virtuels.  Dans ce cas, une classe dérivée peut modifier le comportement de l'interface en substituant les membres virtuels.  Pour plus d'informations sur les membres virtuels, consultez [Polymorphisme](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).  
  
## Résumé des interfaces  
 Une interface possède les propriétés suivantes :  
  
-   Une interface est comme une classe de base abstraite.  Toute classe ou tout struct qui implémentent l'interface doivent implémenter tous ses membres.  
  
-   Une interface ne peut pas être instanciée directement.  Ses membres sont implémentées par une classe ou un struct qui implémentent l'interface.  
  
-   Les interfaces peuvent contenir des événements, des indexeurs, des méthodes et des propriétés.  
  
-   Les interfaces ne contiennent aucune implémentation de méthodes.  
  
-   Une classe ou un struct peuvent implémenter plusieurs interfaces.  Une classe peut hériter d'une classe de base et également implémenter une ou plusieurs interfaces.  
  
## Dans cette section  
 [Implémentation d’interface explicite](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
 Explique comment créer un membre de classe spécifique à une interface.  
  
 [Comment : implémenter de manière explicite des membres d'interface](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)  
 Fournit un exemple montrant comment implémenter explicitement des membres d'interface.  
  
 [Comment : implémenter de manière explicite des membres de deux interfaces](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)  
 Fournit un exemple montrant comment implémenter explicitement des membres d'interface avec héritage.  
  
##  <a name="BKMK_RelatedSections"></a> Rubriques connexes  
  
-   [Propriétés d'interface](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [Indexeurs dans les interfaces](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [Comment : implémenter des événements d'interface](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [Classes et structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
  
-   [Héritage](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
  
-   [Méthodes](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Polymorphisme](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
  
-   [Classes abstract et sealed et membres de classe](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
  
-   [Propriétés](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [Événements](../../../csharp/programming-guide/events/index.md)  
  
-   [Indexeurs](../../../csharp/programming-guide/indexers/index.md)  
  
## Chapitre proposé  
 [Interfaces](http://msdn.microsoft.com/library/orm-9780596521066-01-13.aspx) dans [Formation C\# 3.0 : maîtriser les principes fondamentaux de C\# 3.0](http://msdn.microsoft.com/library/orm-9780596521066-01.aspx)  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Héritage](../../../csharp/programming-guide/classes-and-structs/inheritance.md)