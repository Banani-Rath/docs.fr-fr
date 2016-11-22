---
title: "How to: Convert Hexadecimal Strings to Numbers (Visual Basic) | Microsoft Docs"
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
  - "numbers, hexadecimals"
  - "hexadecimals, decimals"
  - "examples [Visual Basic], string conversion"
  - "decimals, hexadecimals"
  - "string conversion, hexadecimal to numbers"
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Convert Hexadecimal Strings to Numbers (Visual Basic)
Cet exemple convertit une chaîne hexadécimale en un entier à l'aide de la méthode <xref:System.Convert.ToInt32%2A>.  
  
### Pour convertir une chaîne hexadécimale en un nombre  
  
-   Utilisez la méthode <xref:System.Convert.ToInt32%2A> pour convertir le nombre exprimé en base\-16 en un entier.  
  
     Le premier argument de la méthode <xref:System.Convert.ToInt32%2A> est la chaîne à convertir.  Le deuxième argument décrit la base dans laquelle le nombre est exprimé ; hexadécimal est de base 16.  
  
     [!CODE [VbVbalrStrings#62](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#62)]  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>   
 <xref:System.Convert.ToInt32%2A>