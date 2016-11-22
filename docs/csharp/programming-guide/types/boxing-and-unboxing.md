---
title: "Boxing et unboxing (Guide de programmation C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.boxing"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Langage C#, conversion boxing"
  - "Langage C#, conversion unboxing"
  - "unboxing [C#]"
  - "boxing [C#]"
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
caps.latest.revision: 34
caps.handback.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Boxing et unboxing (Guide de programmation C#)
Le boxing consiste à convertir un [type valeur](../../../csharp/language-reference/keywords/value-types.md) en type `object` ou bien en n'importe quel type interface implémenté par ce type valeur.  Lorsque le CLR exécute un boxing d'un type valeur, il inclut la valeur dans un wrapper, à l'intérieur d'un System.Object, et la stocke sur le tas managé.  L'unboxing extrait le type valeur de l'objet.  La conversion boxing est implicite ; la conversion unboxing est explicite.  Le concept de boxing et de unboxing repose sur la vue unifiée par C\# du système de type, dans lequel une valeur de n'importe quel type peut être traitée en tant qu'objet.  
  
 Dans l'exemple suivant, la variable de type entier `i` est convertie \(*boxed*\) et assignée à l'objet `o`.  
  
 [!CODE [csProgGuideTypes#14](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#14)]  
  
 L'objet `o` peut être ensuite unboxed et assigné à la variable entier `i` :  
  
 [!CODE [csProgGuideTypes#15](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#15)]  
  
 Les exemples suivants montrent comment le boxing est utilisé dans C\#.  
  
 [!CODE [csProgGuideTypes#47](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#47)]  
  
## Performances  
 Par rapport aux assignations simples, le boxing et l'unboxing sont des processus qui coûtent cher en calcul.  Lorsqu'un type valeur est boxed, un nouvel objet doit être alloué et construit.  À un degré moindre, le cast requis pour l'unboxing coûte également cher en calcul.  Pour plus d'informations, consultez [Performances](../Topic/.NET%20Performance%20Tips.md).  
  
## Boxing  
 Le boxing est utilisé pour stocker des types valeur dans le tas rassemblé par garbage collection.  Le boxing est une conversion implicite d'un [type valeur](../../../csharp/language-reference/keywords/value-types.md) en type `object` ou bien en n'importe quel type interface implémenté par ce type valeur.  Le boxing d'un type valeur alloue une instance d'objet sur le tas et copie la valeur dans le nouvel objet.  
  
 Dans l'exemple suivant, une variable de type valeur est déclarée :  
  
 [!CODE [csProgGuideTypes#17](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#17)]  
  
 L'instruction ci\-dessous réalise implicitement une opération de boxing sur la variable `i` :  
  
 [!CODE [csProgGuideTypes#18](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#18)]  
  
 Le résultat de cette instruction crée, sur la pile, un objet `o` qui fait référence à une valeur de type `int` sur le tas.  Cette valeur est une copie de la valeur de type valeur qui a été assignée à la variable `i`.  La différence entre les deux variables, `i` et `o`, est illustrée dans la figure ci\-dessous.  
  
 ![Graphique BoxingConversion](../../../csharp/programming-guide/types/media/vcboxingconversion.png "vcBoxingConversion")  
Conversion boxing  
  
 Il est également possible, mais jamais obligatoire, d'effectuer un boxing explicite comme dans l'exemple suivant :  
  
 [!CODE [csProgGuideTypes#19](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#19)]  
  
## Description  
 Cet exemple utilise le boxing pour convertir une variable `i` \(entier\) en un objet `o`.  Ensuite, la valeur `123` stockée dans la variable `i` est remplacée par la valeur `456`.  L'exemple montre que le type valeur d'origine et que l'objet boxed utilisent des emplacements de mémoire distincts et peuvent, par conséquent, stocker des valeurs différentes.  
  
## Exemple  
 [!CODE [csProgGuideTypes#16](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#16)]  
  
## Unboxing  
 L'unboxing est une conversion explicite du type `object` en un [type valeur](../../../csharp/language-reference/keywords/value-types.md) ou bien d'un type interface en un type valeur qui implémente l'interface.  Une opération d'unboxing comprend les étapes suivantes :  
  
-   Vérification de l'instance de l'objet pour s'assurer qu'il s'agit bien d'une valeur boxed du type valeur spécifié.  
  
-   Copie de la valeur de l'instance dans la variable de type valeur.  
  
 Les instructions suivantes expliquent les opérations de boxing et d'unboxing :  
  
 [!CODE [csProgGuideTypes#21](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#21)]  
  
 Le résultat de ces instructions est illustré dans la figure ci\-dessous.  
  
 ![Graphique de conversion UnBoxing](../../../csharp/programming-guide/types/media/vcunboxingconversion.png "vcUnBoxingConversion")  
Conversion unboxing  
  
 Pour que l'unboxing de types valeur réussisse au moment de l'exécution, l'élément qui est unboxed doit être une référence à un objet précédemment créé par boxing d'une instance de ce type valeur.  La tentative d'extraction de `null` provoque un <xref:System.NullReferenceException>.  La tentative d'extraction d'une référence vers un type de valeur incompatible provoque un <xref:System.InvalidCastException>.  
  
## Exemple  
 L'exemple suivant montre un cas d'unboxing non valide et l'`InvalidCastException` qui en résulte.  Avec `try` et `catch`, un message d'erreur est affiché lorsque l'erreur se produit.  
  
 [!CODE [csProgGuideTypes#20](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#20)]  
  
 Sortie de ce programme :  
  
 `Specified cast is not valid.  Error: Incorrect unboxing.`  
  
 Si vous modifiez l'instruction :  
  
```  
int j = (short) o;  
```  
  
 en :  
  
```  
int j = (int) o;  
```  
  
 la conversion sera réalisée, avec le résultat suivant :  
  
 `Unboxing OK.`  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Rubriques connexes  
 Pour plus d'informations :  
  
-   [Types référence](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [Types valeur](../../../csharp/language-reference/keywords/value-types.md)  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)