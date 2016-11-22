---
title: "How to: Convert an Array of Bytes into a String in Visual Basic | Microsoft Docs"
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
  - "string conversion, arrays"
  - "byte arrays, converting to strings"
  - "examples [Visual Basic], strings"
  - "arrays [Visual Basic], converting to strings"
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Convert an Array of Bytes into a String in Visual Basic
Cette rubrique montre comment convertir les octets d'un tableau d'octets en une chaîne.  
  
## Exemple  
 Cet exemple utilise la méthode <xref:System.Text.Encoding.GetString%2A> de la classe d'encodage <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName> pour convertir tous les octets d'un tableau d'octets en une chaîne.  
  
 [!CODE [VbVbalrStrings#72](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#72)]  
  
 Vous pouvez choisir entre plusieurs options d'encodage pour convertir un tableau d'octets en une chaîne :  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName> : obtient un encodage pour le jeu de caractères ASCII \(7 bits\).  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=fullName> : obtient un encodage pour le format UTF\-16 qui utilise l'ordre d'octet avec primauté des octets de poids fort \(Big\-endian\).  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=fullName> : obtient un encodage pour la page de codes ANSI actuelle du système.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName> : obtient un encodage pour le format UTF\-16 qui utilise l'ordre d'octet avec primauté des octets de poids faible \(Big\-endian\).  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=fullName> : obtient un encodage pour le format UTF\-32 qui utilise l'ordre d'octet avec primauté des octets de poids faible \(Big\-endian\).  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=fullName> : obtient un encodage pour le format UTF\-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=fullName> : obtient un encodage pour le format UTF\-8.  
  
## Voir aussi  
 <xref:System.Text.Encoding?displayProperty=fullName>   
 <xref:System.Text.Encoding.GetString%2A>   
 [How to: Convert Strings into an Array of Bytes in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)