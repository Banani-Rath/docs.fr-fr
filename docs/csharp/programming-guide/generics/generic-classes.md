---
title: "Classes g&#233;n&#233;riques (guide de programmation C#) | Microsoft Docs"
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
  - "langage C#, classes génériques"
  - "génériques (C#), classes"
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Classes g&#233;n&#233;riques (guide de programmation C#)
Les classes génériques encapsulent des opérations qui ne sont pas spécifiques à un type de données particulier.  L'utilisation la courante des classes génériques concerne les collections telles que les listes liées, les tables de hachage, les pile, les files d'attente, les arborescences, etc.  Les opérations telles que l'ajout et la suppression d'éléments de la collection sont exécutées fondamentalement de la même manière quel que soit le type de données stockées.  
  
 Pour la plupart des scénarios qui requièrent des classes de collection, l'approche recommandée est d'utiliser ceux fournis dans la bibliothèque de classes .NET Framework.  Pour plus d'informations sur l'utilisation de ces classes, consultez [Génériques dans la bibliothèque de classes .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).  
  
 En général, vous créez des classes génériques en démarrant avec une classe concrète existante, puis en modifiant des types en paramètres de type jusqu'à ce que vous atteigniez l'équilibre optimal au niveau de la généralisation et de la facilité d'utilisation.  Lors de la création de vos propres classes génériques, les aspects importants à prendre en considération sont notamment les suivants :  
  
-   Quels types généraliser en paramètres de type.  
  
     En règle générale, plus le nombre de types que vous pouvez paramétrer est important, plus votre code est souple et réutilisable.  Toutefois, une généralisation excessive peut produire un code qui est difficile à lire ou à comprendre par d'autres développeurs.  
  
-   Quelles contraintes, le cas échéant, appliquer aux paramètres de type \(consultez [Contraintes sur les paramètres de type](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)\).  
  
     Une bonne règle est d'appliquer le maximum de contraintes possible vous permettant néanmoins de gérer les types que vous avez besoin de gérer.  Par exemple, si vous savez que votre classe générique est destinée uniquement à être utilisée avec les types référence, appliquez la contrainte de classe.  Cela empêchera l'utilisation involontaire de votre classe avec les types valeur et vous permettra d'utiliser l'opérateur `as` sur `T` et de rechercher les valeurs nulles.  
  
-   S'il faut prendre en compte le comportement générique dans les sous\-classes et les classes de base.  
  
     Les classes génériques pouvant servir de classes de base, les considérations de conception qui s'appliquent ici sont les mêmes que pour les classes non génériques.  Consultez les règles relatives à l'héritage à partir des classes de base génériques plus loin dans cette rubrique.  
  
-   S'il faut implémenter une ou plusieurs interfaces génériques.  
  
     Par exemple, si vous concevez une classe qui sera utilisée pour créer des éléments dans une collection basée sur les génériques, vous pouvez avoir besoin d'implémenter une interface telle que <xref:System.IComparable%601>, où `T` est le type de votre classe.  
  
 Pour obtenir un exemple d'une classe générique simple, consultez [Introduction aux génériques](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 Les règles pour les paramètres de type et les contraintes ont plusieurs conséquences sur le comportement de classe générique, surtout en ce qui concerne l'héritage et l'accessibilité des membres.  Avant de continuer, vous devez comprendre quelques termes.  Pour une classe générique `Node<T>,` le code client peut référencer la classe soit en spécifiant un argument de type, pour créer un type construit fermé \(`Node<int>`\),  soit, en laissant le paramètre type non spécifié, par exemple lorsque vous spécifiez une classe de base générique, pour créer un type construit ouvert \(`Node<T>`\).  Les classes génériques peuvent hériter de classes concrètes, de classes construites fermées ou de classes de base construites ouvertes :  
  
 [!CODE [csProgGuideGenerics#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#16)]  
  
 Les classes non génériques, également appelées concrètes, peuvent hériter des classes de base construites fermées, mais pas des classes construites ouvertes ou des paramètres de type parce que le code client ne peut en aucune façon fournir au moment de l'exécution l'argument de type requis pour instancier la classe de base.  
  
 [!CODE [csProgGuideGenerics#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#17)]  
  
 Les classes génériques qui héritent de types construits ouverts doivent fournir des arguments de type pour tout paramètre de type de classe de base qui n'est pas partagé par la classe qui hérite, comme cela est indiqué dans le code suivant :  
  
 [!CODE [csProgGuideGenerics#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#18)]  
  
 Les classes génériques qui héritent des types construits ouverts doivent spécifier des contraintes qui sont un sur\-ensemble, ou qui impliquent, des contraintes sur le type de base :  
  
 [!CODE [csProgGuideGenerics#19](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#19)]  
  
 Les types génériques peuvent utiliser plusieurs paramètres de type et contraintes, comme suit :  
  
 [!CODE [csProgGuideGenerics#20](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#20)]  
  
 Les types construits ouverts et les types construits fermés peuvent être utilisés comme paramètres de méthode :  
  
 [!CODE [csProgGuideGenerics#21](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#21)]  
  
 Si une classe générique implémente une interface, toutes les instances de cette classe peuvent être castées à cette interface.  
  
 Les classes génériques sont indifférentes.  En d'autres termes, si un paramètre d'entrée spécifie un `List<BaseClass>`, vous obtiendrez une erreur de compilation si vous tentez de fournir un `List<DerivedClass>`.  
  
## Voir aussi  
 <xref:System.Collections.Generic>   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Génériques](../../../csharp/programming-guide/generics/index.md)   
 [Enregistrement de l'état des énumérateurs](http://go.microsoft.com/fwlink/?LinkId=112390)   
 [Un puzzle d'héritage, partie un](http://go.microsoft.com/fwlink/?LinkId=112380)