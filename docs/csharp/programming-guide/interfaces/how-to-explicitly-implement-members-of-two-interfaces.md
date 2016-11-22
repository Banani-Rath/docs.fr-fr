---
title: "Comment&#160;: impl&#233;menter de mani&#232;re explicite des membres de deux interfaces (Guide de programmation C#) | Microsoft Docs"
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
  - "héritage (C#), implémenter explicitement des membres d'interface"
  - "interfaces (C#), implémenter explicitement avec héritage"
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: impl&#233;menter de mani&#232;re explicite des membres de deux interfaces (Guide de programmation C#)
L'implémentation d'[interface](../../../csharp/language-reference/keywords/interface.md) explicite permet également au programmeur d'implémenter deux interfaces qui ont les mêmes noms de membres et donnent à chaque membre d'interface une implémentation distincte.  Cet exemple affiche les dimensions d'une zone à la fois dans les unités de mesure métriques et britanniques.  La [classe](../../../csharp/language-reference/keywords/class.md) Box implémente deux interfaces, IEnglishDimensions et IMetricDimensions, qui représentent les différents systèmes de mesure.  Les deux interfaces ont des noms de membres identiques : Length et Width.  
  
## Exemple  
 [!CODE [csProgGuideInheritance#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#9)]  
  
## Programmation fiable  
 Si vous souhaitez utiliser par défaut les unités de mesure britanniques, implémentez les méthodes Length et Width normalement, puis implémentez explicitement les méthodes Length et Width à partir de l'interface IMetricDimensions :  
  
 [!CODE [csProgGuideInheritance#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#10)]  
  
 Dans ce cas, vous pouvez accéder aux unités de mesure britanniques à partir de l'instance de classe et accéder aux unités métriques à partir de l'instance d'interface :  
  
 [!CODE [csProgGuideInheritance#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#11)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Classes et structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)   
 [Comment : implémenter de manière explicite des membres d'interface](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)