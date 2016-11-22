---
title: "How to: Validate Strings That Represent Dates or Times (Visual Basic) | Microsoft Docs"
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
  - "strings [Visual Basic], validating"
  - "String data type, validation"
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Validate Strings That Represent Dates or Times (Visual Basic)
L'exemple de code suivant définit une valeur `Boolean` qui indique si une chaîne représente une date ou une heure valide.  
  
## Exemple  
 [!CODE [VbVbcnRegEx#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnRegEx#2)]  
  
## Compilation du code  
 Remplacez `("01/01/03")` et `"9:30 PM"` par la date et l'heure que vous souhaitez valider.  Vous pouvez remplacer la chaîne par une autre chaîne codée de manière irréversible, à l'aide d'une variable `String` ou d'une méthode qui retourne une chaîne, telle que `InputBox`.  
  
## Programmation fiable  
 Utilisez cette méthode pour valider la chaîne avant d'essayer de convertir `String` en une variable `DateTime`.  Vérifiez d'abord la date ou l'heure pour éviter de générer une exception au moment de l'exécution.  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>   
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>   
 [Validating Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)