---
title: "*, op&#233;rateur (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "*_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "* (opérateur C#)"
  - "opérateur de multiplication (*) (C#)"
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# *, op&#233;rateur (r&#233;f&#233;rence C#)
L'opérateur de multiplication \(`*`\) calcule le produit de ses opérandes.  De même, l'opérateur de déréférencement permet de lire et d'écrire sur un pointeur.  
  
## Notes  
 Tous les types numériques disposent d'opérateurs de multiplication prédéfinis.  
  
 L'opérateur `*` est aussi utilisé pour déclarer des types pointeur et supprimer la référence à des pointeurs.  Cet opérateur ne peut être utilisé que dans des contextes unsafe, signalés par l'utilisation du mot clé [unsafe](../../../csharp/language-reference/keywords/unsafe.md), et requiert l'option [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) du compilateur.  L'opérateur de déréférencement est également connu comme opérateur d'indirection.  
  
 Les types définis par l'utilisateur peuvent surcharger l'opérateur `*` binaire \(consultez [operator](../../../csharp/language-reference/keywords/operator.md)\).  Lorsqu'un opérateur binaire est surchargé, l'opérateur d'assignation correspondant \(s'il y en a un\) est, lui aussi, implicitement surchargé.  
  
## Exemple  
 [!CODE [csRefOperators#50](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#50)]  
  
## Exemple  
 [!CODE [csRefOperators#51](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#51)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Pointeurs et code unsafe](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Opérateurs C\#](../../../csharp/language-reference/operators/index.md)