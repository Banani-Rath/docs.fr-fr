---
title: "How to: Start an Application and Send it Keystrokes (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
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
  - "keystrokes, sending"
  - "Shell command example [Visual Basic]"
  - "processes, starting and sending keystrokes"
  - "SendKeys.SendWait examples"
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Start an Application and Send it Keystrokes (Visual Basic)
Cet exemple utilise la fonction `Shell` pour démarrer l'application de calculatrice, puis multiplie deux nombres en envoyant des séquences de touches à l'aide de la méthode `My.Computer.Keyboard.SendKeys`.  
  
## Exemple  
 [!CODE [VbVbalrMyComputer#25](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#25)]  
  
## Programmation fiable  
 Une exception <xref:System.ArgumentException> est levée si une application avec l'identificateur de processus demandé ne peut pas être trouvée.  
  
## Sécurité .NET Framework  
 L'appel à la fonction `Shell` nécessite une confiance totale \(classe <xref:System.Security.SecurityException>\).  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>