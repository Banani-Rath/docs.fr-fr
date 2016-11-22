---
title: "Comment&#160;: d&#233;clarer, instancier et utiliser un d&#233;l&#233;gu&#233; (Guide de programmation C#) | Microsoft Docs"
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
  - "délégués (C#), déclarer et instancier"
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: d&#233;clarer, instancier et utiliser un d&#233;l&#233;gu&#233; (Guide de programmation C#)
Dans C\# 1.0 et dans les versions ultérieures, les délégués peuvent être déclarés comme indiqué dans l'exemple suivant.  
  
 [!CODE [csProgGuideDelegates#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#13)]  
  
 [!CODE [csProgGuideDelegates#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#14)]  
  
 C\# 2.0 offre un moyen plus simple d'écrire la déclaration précédente, comme indiqué dans l'exemple suivant.  
  
 [!CODE [csProgGuideDelegates#32](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#32)]  
  
 Dans C\# 2.0 et les versions ultérieures, il est également possible d'utiliser une méthode anonyme pour déclarer et initialiser un délégué [](../../../csharp/language-reference/keywords/delegate.md "delegate (C# Reference)"), comme indiqué dans l'exemple suivant.  
  
 [!CODE [csProgGuideDelegates#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#15)]  
  
 Dans C\# 3.0 et les versions ultérieures, les délégués peuvent également être déclarés et instanciés à l'aide d'une expression lambda, comme indiqué dans l'exemple suivant.  
  
 [!CODE [csProgGuideDelegates#31](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#31)]  
  
 Pour plus d'informations, consultez [Expressions lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 L'exemple suivant illustre la déclaration, l'instanciation et l'utilisation d'un délégué.  La classe `BookDB` encapsule une base de données de librairie qui gère une base de données de livres.  Elle expose une méthode `ProcessPaperbackBooks`, qui recherche tous les livres de poche dans la base de données et appelle un délégué pour chacun d'entre eux.  Le type `delegate` qui est utilisé est nommé `ProcessBookDelegate`.  La classe `Test` utilise cette classe pour imprimer les titres et le prix moyen des livres de poche.  
  
 L'utilisation de délégués favorise une bonne séparation des fonctionnalités entre la base de données de la librairie et le code client.  Le code client ignore complètement comment les livres sont stockés et comment le code libraire recherche les livres de poche.  Inversement, le code libraire ignore quel traitement est effectué sur les livres de poche lorsqu'il les a trouvés.  
  
## Exemple  
 [!CODE [csProgGuideDelegates#12](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#12)]  
  
## Programmation fiable  
  
-   Déclaration d'un délégué.  
  
     L'instruction suivante déclare un nouveau type délégué.  
  
     [!CODE [csProgGuideDelegates#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#16)]  
  
     Chaque type délégué décrit le nombre et les types des arguments, ainsi que le type de la valeur de retour des méthodes qu'il peut encapsuler.  Chaque fois qu'un nouvel ensemble de types d'argument ou qu'un nouveau type de valeur de retour est requis, un nouveau type délégué doit être déclaré.  
  
-   Instanciation d'un délégué.  
  
     Après qu'un type délégué a été déclaré, un objet délégué doit être créé et associé à une méthode particulière.  Dans l'exemple précédent, pour ce faire, vous passez la méthode `PrintTitle` à la méthode `ProcessPaperbackBooks` comme dans l'exemple suivant :  
  
     [!CODE [csProgGuideDelegates#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#17)]  
  
     Cela crée un objet de délégué associé à la méthode [statique](../../../csharp/language-reference/keywords/static.md) `Test.PrintTitle`.  De la même manière, la méthode non statique `AddBookToTotal` sur l'objet `totaller` est passée comme dans l'exemple suivant :  
  
     [!CODE [csProgGuideDelegates#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#18)]  
  
     Dans les deux cas, un nouvel objet délégué est passé à la méthode `ProcessPaperbackBooks`.  
  
     Après qu'un délégué est créé, la méthode à laquelle il est associé ne change jamais ; les objets délégués sont immuables.  
  
-   Appel d'un délégué.  
  
     Après qu'un objet délégué est créé, il est normalement transmis à un autre code qui appellera le délégué.  Vous pouvez appeler un objet délégué en utilisant son nom, suivi, entre parenthèses, des arguments qui doivent être transmis au délégué.  Un exemple d'appel de délégué est fourni ci\-dessous :  
  
     [!CODE [csProgGuideDelegates#19](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#19)]  
  
     Un délégué peut faire l'objet d'un appel synchrone, comme dans cet exemple, ou d'un appel asynchrone à l'aide des méthodes `BeginInvoke` et `EndInvoke`.  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Événements](../../../csharp/programming-guide/events/index.md)   
 [Délégués](../../../csharp/programming-guide/delegates/index.md)