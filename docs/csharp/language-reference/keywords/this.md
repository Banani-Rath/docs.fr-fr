---
title: "this (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "this"
  - "this_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "this (mot clé C#)"
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# this (r&#233;f&#233;rence C#)
Le mot clé `this` fait référence à l'instance actuelle de la classe et est également utilisé comme un modificateur du premier paramètre d'une méthode d'extension.  
  
> [!NOTE]
>  Cet article traite de l'utilisation de `this` avec des instances de classe.  Pour plus d'informations sur son utilisation dans les méthodes d'extension, consultez [Méthodes d'extension](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
 Voici quelques emplois courants de `this` :  
  
-   Qualification de membres masqués par des noms similaires, par exemple :  
  
 [!CODE [csrefKeywordsAccess#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsAccess#4)]  
  
-   Passage d'un objet comme paramètre à d'autres méthodes, par exemple :  
  
    ```  
    CalcTax(this);  
    ```  
  
-   Déclaration d'indexeurs, par exemple :  
  
 [!CODE [csrefKeywordsAccess#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsAccess#5)]  
  
 Les fonctions membre static, parce qu'elles existent au niveau de la classe et pas dans le cadre d'un objet, n'ont pas de pointeur `this`.  Faire référence à `this` dans une méthode statique est une erreur.  
  
## Exemple  
 Dans cet exemple, `this` est utilisé pour qualifier les membres de la classe `Employee`, `name` et `alias`, qui sont masqués par des noms similaires.  Il est également utilisé pour passer un objet à la méthode `CalcTax`, qui appartient à une autre classe.  
  
 [!CODE [csrefKeywordsAccess#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsAccess#3)]  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Mots clés C\#](../../../csharp/language-reference/keywords/index.md)   
 [de base](../../../csharp/language-reference/keywords/base.md)   
 [Méthodes](../../../csharp/programming-guide/classes-and-structs/methods.md)