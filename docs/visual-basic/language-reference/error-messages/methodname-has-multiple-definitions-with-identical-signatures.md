---
title: "&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures | Microsoft Docs"
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
  - "vbc30269"
  - "bc30269"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30269"
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures
Une déclaration de procédure `Function` ou `Sub` utilise un nom de procédure et une liste d'arguments identiques à ceux d'une déclaration précédente.  Une des causes possibles est une tentative de surcharge de la procédure d'origine.  Les procédures surchargées doivent avoir des listes d'arguments différentes.  
  
 **ID d'erreur :** BC30269  
  
### Pour corriger cette erreur  
  
-   Modifiez le nom de la procédure ou la liste d'arguments ou supprimez la déclaration dupliquée.  
  
## Voir aussi  
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Considerations in Overloading Procedures](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)