---
title: "How to: Receive Strings From Serial Ports in Visual Basic | Microsoft Docs"
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
  - "serial ports, retrieving strings"
  - "strings [Visual Basic], retrieving from serial ports"
  - "My.Resources object"
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Receive Strings From Serial Ports in Visual Basic
Cette rubrique explique comment utiliser `My.Computer.Ports` pour recevoir des chaînes des ports série de l'ordinateur en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### Pour recevoir des chaînes du port série  
  
1.  Initialisez la chaîne de retour.  
  
     [!CODE [VbVbalrMyComputer#38](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#38)]  
  
2.  Déterminez quel port série doit fournir les chaînes.  Cet exemple suppose que c'est le port `COM1`.  
  
3.  Utilisez la méthode `My.Computer.Ports.OpenSerialPort` pour obtenir une référence au port.  Pour plus d'informations, consultez <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Le bloc `Try...Catch...Finally` permet à l'application de fermer le port série même s'il génère une exception.  Tout le code qui manipule le port série doit apparaître dans ce bloc.  
  
     [!CODE [VbVbalrMyComputer#39](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#39)]  
  
4.  Créez une boucle `Do` pour lire les lignes de texte jusqu'à ce qu'il ne reste plus aucune ligne disponible.  
  
     [!CODE [VbVbalrMyComputer#40](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#40)]  
  
5.  Utilisez la méthode <xref:System.IO.Ports.SerialPort.ReadLine%2A> pour lire la ligne de texte disponible suivante à partir du port série.  
  
     [!CODE [VbVbalrMyComputer#41](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#41)]  
  
6.  Utilisez une instruction `If` pour déterminer si la méthode <xref:System.IO.Ports.SerialPort.ReadLine%2A> retourne `Nothing` \(ce qui signifie qu'il n'y a plus de texte disponible\).  Si elle retourne `Nothing`, quittez la boucle `Do`.  
  
     [!CODE [VbVbalrMyComputer#42](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#42)]  
  
7.  Ajoutez un bloc `Else` à l'instruction `If` pour gérer le cas si la chaîne est effectivement lue.  Le bloc ajoute la chaîne du port série à la chaîne de retour.  
  
     [!CODE [VbVbalrMyComputer#43](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#43)]  
  
8.  Retournez la chaîne.  
  
     [!CODE [VbVbalrMyComputer#44](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#44)]  
  
## Exemple  
 [!CODE [VbVbalrMyComputer#37](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#37)]  
  
 Cet exemple de code est également disponible sous forme d'extrait de code IntelliSense.  Dans le sélecteur d'extrait de code, il se trouve dans **Connectivité et réseau**.  Pour plus d'informations, consultez [Extraits de code](/visual-studio/ide/code-snippets).  
  
## Compilation du code  
 Cet exemple suppose que l'ordinateur utilise `COM1`.  
  
## Programmation fiable  
 Cet exemple suppose que l'ordinateur utilise `COM1`.  Pour plus de souplesse, le code doit permettre à l'utilisateur de sélectionner le port série dans une liste de ports disponibles.  Pour plus d'informations, consultez [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 Cet exemple utilise un bloc `Try...Catch...Finally` pour vérifier que l'application ferme le port et pour intercepter les exceptions d'expiration.  Pour plus d'informations, consultez [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)