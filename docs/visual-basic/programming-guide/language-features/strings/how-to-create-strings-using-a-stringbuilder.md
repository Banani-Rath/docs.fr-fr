---
title: "How to: Create Strings Using a StringBuilder in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "StringBuilder class"
  - "strings [Visual Basic], using StringBuilder"
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Create Strings Using a StringBuilder in Visual Basic
Cet exemple construit une longue chaîne à partir de plusieurs chaînes plus petites à l'aide de la classe <xref:System.Text.StringBuilder>.  La classe <xref:System.Text.StringBuilder> est plus efficace que l'opérateur `&=` pour concaténer plusieurs chaînes.  
  
## Exemple  
 L'exemple suivant crée une instance de la classe <xref:System.Text.StringBuilder>, ajoute 1 000 chaînes à cette instance, puis retourne sa représentation sous forme de chaîne.  
  
 [!CODE [VbVbalrStrings#70](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#70)]  
  
## Voir aussi  
 [Utilisation de la classe StringBuilder](../Topic/Using%20the%20StringBuilder%20Class%20in%20the%20.NET%20Framework.md)   
 [&\= Operator](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Strings](../../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Création de nouvelles chaînes](../Topic/Creating%20New%20Strings%20in%20the%20.NET%20Framework.md)   
 [Manipulation des chaînes](../Topic/Manipulating%20Strings%20in%20the%20.NET%20Framework.md)   
 [Strings Sample](http://msdn.microsoft.com/fr-fr/be9e82a3-dc95-4aaa-9396-61b66e467e02)