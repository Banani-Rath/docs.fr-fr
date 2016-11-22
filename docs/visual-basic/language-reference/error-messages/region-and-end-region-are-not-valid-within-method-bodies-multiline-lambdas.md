---
title: "&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas | Microsoft Docs"
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
  - "bc32025"
  - "vbc32025"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32025"
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas
Le bloc `#Region` doit être déclaré au niveau d'une classe, d'un module ou d'un espace de noms.  Une région que vous pouvez réduire peut inclure une ou plusieurs procédures, mais elle ne peut pas commencer ou se terminer à l'intérieur d'une procédure.  
  
 **ID d'erreur :** BC32025  
  
### Pour corriger cette erreur  
  
1.  Assurez\-vous qu'une instruction `End Function` ou `End Sub` termine bien la procédure précédente.  
  
2.  Assurez\-vous que les directives `#Region` et `#End Region` se trouvent dans le même bloc de code.  
  
## Voir aussi  
 [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md)