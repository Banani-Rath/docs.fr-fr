---
title: "Nothing and Strings in Visual Basic | Microsoft Docs"
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
  - "strings [Visual Basic], Nothing"
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Nothing and Strings in Visual Basic
Le runtime [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] et [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] évaluent `Nothing` différemment lorsqu'il s'agit de chaînes.  
  
## Runtime Visual Basic et le .NET Framework  
 Prenons l'exemple suivant :  
  
 [!CODE [VbVbalrStrings#47](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#47)]  
  
 Le runtime [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] évalue habituellement `Nothing` comme une chaîne vide \(""\).  Toutefois, ce n'est pas le cas du [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] qui lève une exception à chaque tentative d'exécuter une opération de chaîne sur `Nothing`.  
  
## Voir aussi  
 [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)