---
title: "File already open | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID55"
dev_langs: 
  - "VB"
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# File already open
Un fichier doit parfois être fermé avant qu'une opération `FileOpen` ou qu'une autre opération ne se produise.  Cette erreur peut se produire pour de nombreuses raisons.  
  
-   Une opération `FileOpen` de mode séquentiel Output a été exécutée pour un fichier déjà ouvert.  
  
-   Une instruction fait référence à un fichier ouvert.  
  
### Pour corriger cette erreur  
  
1.  Fermez le fichier avant d'exécuter l'instruction.  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>