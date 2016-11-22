---
title: "&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31122"
  - "bc31122"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31122"
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &#39;Custom&#39; modifier is not valid on events declared without explicit delegate types
Contrairement à un événement qui n'est pas personnalisé, une déclaration `Custom Event` requiert une clause `As` après le nom de l'évènement qui spécifie explicitement le type délégué de l'événement.  
  
 Les événements non personnalisés peuvent être définis avec une clause `As` et un type délégué explicite, ou avec une liste de paramètres qui suit immédiatement le nom de l'évènement.  
  
 **ID d'erreur :** BC31122  
  
### Pour corriger cette erreur  
  
1.  Définissez un délégué avec la même liste de paramètres que l'événement personnalisé.  
  
     Par exemple, si `Custom Event` a été défini par `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, le délégué correspondant est le suivant :  
  
     [!CODE [VbVbalrEventError#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#18)]  
  
2.  Remplacez la liste des paramètres de l'événement personnalisé par une clause `As` qui spécifie le type délégué.  
  
     Pour reprendre l'exemple précédent, la déclaration `Custom Event` est réécrite comme suit :  
  
     [!CODE [VbVbalrEventError#19](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#19)]  
  
## Exemple  
 Cet exemple déclare `Custom Event` et spécifie la clause `As` requise avec un type délégué.  
  
 [!CODE [VbVbalrEventError#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#2)]  
  
## Voir aussi  
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)