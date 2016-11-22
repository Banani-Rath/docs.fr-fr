---
title: "remove (R&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "remove_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "remove (accesseur d'événement C#)"
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# remove (R&#233;f&#233;rence C#)
Le mot clé contextuel `remove` sert à définir un accesseur d'événement personnalisé appelé lorsque le code client annule son abonnement à votre [événement](../../../csharp/language-reference/keywords/event.md).  Si vous fournissez un accesseur `remove` personnalisé, vous devez également fournir un accesseur [add](../../../csharp/language-reference/keywords/add.md).  
  
## Exemple  
 L'exemple suivant illustre un événement avec des accesseurs [add](../../../csharp/language-reference/keywords/add.md) et `remove` personnalisés.  Pour obtenir l'exemple complet, consultez [Comment : implémenter des événements d'interface](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!CODE [csrefKeywordsContextual#15](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsContextual#15)]  
  
 En général, vous n'avez pas besoin de fournir vos propres accesseurs d'événements personnalisés.  Les accesseurs générés automatiquement par le compilateur lorsque vous déclarez un événement sont suffisants pour la plupart des scénarios.  
  
## Voir aussi  
 [Événements](../../../csharp/programming-guide/events/index.md)