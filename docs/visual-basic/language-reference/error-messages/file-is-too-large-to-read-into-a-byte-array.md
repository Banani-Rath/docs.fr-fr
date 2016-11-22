---
title: "File is too large to read into a byte array | Microsoft Docs"
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
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# File is too large to read into a byte array
La taille du fichier que vous essayez de lire dans un tableau d'octets est supérieure à 4 Go.  La méthode `My.Computer.FileSystem.ReadAllBytes` ne peut pas lire un fichier qui dépasse cette taille.  
  
### Pour corriger cette erreur  
  
-   Utilisez <xref:System.IO.StreamReader> pour lire le fichier.  Pour plus d'informations, consultez [Concepts de base du système de fichiers et des E\/S de fichier du .NET Framework \(Visual Basic\)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>   
 <xref:System.IO.StreamReader>   
 [File Access with Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)   
 [How to: Read Text from Files with a StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)