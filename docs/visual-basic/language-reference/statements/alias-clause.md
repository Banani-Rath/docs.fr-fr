---
title: "Alias Clause (Visual Basic) | Microsoft Docs"
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
  - "vb.Alias"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Alias keyword"
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Alias Clause (Visual Basic)
Indique qu'une procédure externe possède un autre nom dans sa DLL.  
  
## Notes  
 Le mot clé `Alias` peut être utilisé dans le contexte suivant :  
  
 [Declare, instruction](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 Dans l'exemple suivant, le mot clé `Alias` est utilisé pour fournir le nom de la fonction dans advapi32.dll, `GetUserNameA`, ce `getUserName` est utilisé à sa place dans cet exemple.  La fonction `getUserName` est appelée dans la sous\-fonction `getUser`, qui affiche le nom de l'utilisateur actuel.  
  
 [!CODE [VbVbalrStatements#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#15)]  
  
## Voir aussi  
 [Mots clés](../../../visual-basic/language-reference/keywords/index.md)