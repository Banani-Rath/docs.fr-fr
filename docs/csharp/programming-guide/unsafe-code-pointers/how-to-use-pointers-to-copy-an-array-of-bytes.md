---
title: "Comment&#160;: utiliser des pointeurs pour copier un tableau d&#39;octets (Guide de programmation&#160;C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
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
  - "tableaux (C#), byte"
  - "tableaux d'octets (C#)"
  - "pointeurs (C#), pour copier des octets"
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: utiliser des pointeurs pour copier un tableau d&#39;octets (Guide de programmation&#160;C#)
L'exemple suivant utilise des pointeurs pour copier des octets d'un tableau vers un autre.  
  
 Cet exemple utilise le mot clé [unsafe](../../../csharp/language-reference/keywords/unsafe.md), qui vous permet d'utiliser des pointeurs dans la méthode `Copy`.  L'instruction [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) permet de déclarer des pointeurs vers les tableaux source et destination.  Elle *fixe* l'emplacement des tableaux source et de destination en mémoire pour qu'ils ne soient déplacés par le garbage collection.  Les blocs de mémoire pour les tableaux sont désépinglés lorsque le bloc `fixed` est rempli.  Étant donné que la méthode `Copy` de cet exemple utilise le mot clé `unsafe`, il doit être compilé avec l'option de compilateur **\/unsafe**.  Pour définir l'option dans Visual Studio, cliquez avec le bouton droit sur le nom du projet, puis cliquez sur **Propriétés**.  Dans l'onglet **Build**, sélectionnez **Autoriser du code unsafe**.  
  
## Exemple  
 [!CODE [csProgGuidePointers#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#3)]  
  
 [!CODE [csProgGuidePointers#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#18)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Pointeurs et code unsafe](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [\/unsafe \(Enable Unsafe Mode\)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)