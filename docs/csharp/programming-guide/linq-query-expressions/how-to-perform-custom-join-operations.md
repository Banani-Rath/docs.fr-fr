---
title: "Comment&#160;: effectuer des op&#233;rations de jointure personnalis&#233;es (Guide de programmation&#160;C#) | Microsoft Docs"
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
  - "jointures personnalisées (C#)"
  - "jointures (C#), personnalisé"
  - "requêtes (LINQ en C#), jointures"
  - "expressions de requête (LINQ en C#), jointures"
ms.assetid: a05e2ab1-410d-4a1d-8ada-af93539682c9
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: effectuer des op&#233;rations de jointure personnalis&#233;es (Guide de programmation&#160;C#)
Cet exemple indique comment effectuer des opérations de jointure qui ne sont pas possibles avec la clause `join`.  Dans une expression de requête, la clause `join` est limitée à et optimisée pour les équijointures, qui sont de loin le type le plus courant d'opération de jointure.  Lorsque vous effectuez une équijointure, vous obtiendrez probablement toujours les meilleures performances en utilisant la clause `join`.  
  
 Toutefois, la clause `join` ne peut pas être utilisée dans les cas suivants :  
  
-   Lorsque la jointure est prédiquée sur une expression d'inégalité \(une non\-équijointure\).  
  
-   Lorsque la jointure est prédiquée sur plusieurs expressions d'égalité ou inégalité.  
  
-   Lorsque vous devez introduire une variable de portée temporaire pour la séquence de côté droit \(interne\) avant l'opération de jointure.  
  
 Pour effectuer des jointures qui ne sont pas des équijointures, vous pouvez utiliser plusieurs clauses `from` pour introduire chaque source de données indépendamment.  Vous appliquez ensuite une expression de prédicat dans une clause `where` à la variable de portée pour chaque source.  L'expression peut également se présenter sous la forme d'un appel de méthode.  
  
> [!NOTE]
>  Ne confondez pas ce type d'opération de jointure personnalisée avec l'utilisation de plusieurs clauses `from` pour accéder aux collections internes.  Pour plus d'informations, consultez [join, clause](../../../csharp/language-reference/keywords/join-clause.md).  
  
## Exemple  
 La première méthode de l'exemple suivant affiche une jointure croisée simple.  Les jointures croisées doivent être utilisées avec prudence, car elles peuvent produire des ensembles de résultats très grands.  Toutefois, elles peuvent être utiles dans certains scénarios pour la création de séquences source par rapport auxquelles les requêtes supplémentaires sont exécutées.  
  
 La deuxième méthode produit une séquence de tous les produits dont l'ID de catégorie est répertorié dans la liste de catégories sur le côté gauche.  Notez l'utilisation de la clause `let` et de la méthode `Contains` pour créer un tableau temporaire.  Il est également possible de créer le tableau avant la requête et d'éliminer la première clause `from`.  
  
 [!CODE [csProgGuideLINQ#64](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#64)]  
  
## Exemple  
 Dans l'exemple suivant, la requête doit joindre deux séquences en fonction des clés correspondantes qui, dans le cas de la séquence interne \(côté droit\), ne peuvent pas être obtenues avant la clause de jointure elle\-même.  Si cette jointure a été effectuée avec une clause `join`, la méthode `Split` devra être appelée pour chaque élément.  L'utilisation de plusieurs clauses `from` permet à la requête d'éviter la charge mémoire inhérente à la répétition de l'appel de méthode.  Toutefois, puisque `join` est optimisée, cela peut se révéler plus rapide que l'utilisation de plusieurs clauses `from` dans ce cas particulier.  Les résultats varieront principalement en fonction du coût de l'appel.  
  
 [!CODE [csProgGuideLINQ#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#13)]  
  
## Compilation du code  
  
-   Créez un projet d'application console [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)] qui cible [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 3.5 ou version ultérieure.  Par défaut, le projet possède une référence à System.Core.dll et une directive `using` pour l'espace de noms System.Linq.  
  
-   Remplacez la classe `Program` par le code dans l'exemple précédent.  
  
-   Suivez les instructions dans [How to: Join Content from Dissimilar Files \(LINQ\)](../Topic/How%20to:%20Join%20Content%20from%20Dissimilar%20Files%20\(LINQ\).md) pour installer les fichiers de données, scores.csv et names.csv.  
  
-   Appuyez sur F5 pour compiler et exécuter le programme.  
  
-   Appuyez sur une touche pour quitter la fenêtre de console.  
  
## Voir aussi  
 [Expressions de requête \(LINQ\)](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [join, clause](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Comment : classer les résultats d'une clause Join](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)