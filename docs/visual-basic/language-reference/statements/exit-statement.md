---
title: "Exit Statement (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Exit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "execution, ending"
  - "files, closing"
  - "programs, quitting"
  - "code, exiting"
  - "Exit statement"
  - "program termination"
  - "execution, stopping"
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Exit Statement (Visual Basic)
Quitte une procédure ou un bloc et passe immédiatement le contrôle à l'instruction qui suit l'appel de procédure ou la définition de bloc.  
  
## Syntaxe  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## Instructions  
 `Exit Do`  
 Quitte immédiatement la boucle `Do` dans laquelle il apparaît.  L'exécution continue l'instruction qui suit l'instruction `Loop`.  `Exit Do` peut être utilisé uniquement à l'intérieur d'une boucle `Do`.  Utilisée dans des boucles `Do` imbriquées, l'instruction `Exit Do` quitte la boucle la plus profonde et transfère le contrôle au niveau d'imbrication supérieur suivant.  
  
 `Exit For`  
 Quitte immédiatement la boucle `For` dans laquelle il apparaît.  L'exécution continue l'instruction qui suit l'instruction `Next`.  `Exit For` peut être utilisé uniquement à l'intérieur d'une boucle `For`...`Next` ou `For Each`...`Next`.  Utilisée dans des boucles `For` imbriquées, l'instruction `Exit For` quitte la boucle la plus profonde et transfère le contrôle au niveau d'imbrication supérieur suivant.  
  
 `Exit Function`  
 Quitte immédiatement la procédure `Function` dans laquelle il apparaît.  L'exécution se poursuit avec l'instruction qui suit l'instruction qui a appelé la procédure `Function`.  `Exit Function` peut être utilisé uniquement à l'intérieur d'une procédure `Function`.  
  
 Pour spécifier une valeur de retour, vous pouvez assigner la valeur au nom de la fonction sur une ligne avant l'instruction `Exit Function`.  Pour assigner la valeur de retour et quitter la fonction en une instruction, vous pouvez à la place utiliser [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) \(page éventuellement en anglais\).  
  
 `Exit Property`  
 Quitte immédiatement la procédure `Property` dans laquelle il apparaît.  L'exécution continue l'instruction qui a appelé la procédure `Property`, autrement dit, l'instruction qui demande ou définit la valeur de la propriété.  `Exit Property` peut être utilisé à l'intérieur uniquement d'une procédure `Get` ou `Set` d'une propriété.  
  
 Pour spécifier une valeur de retour dans une procédure `Get`, vous pouvez assigner la valeur au nom de la fonction sur une ligne avant l'instruction `Exit Property`.  Pour assigner la valeur de retour et quitter la procédure `Get` en une instruction, vous pouvez utiliser à la place l'instruction `Return`.  
  
 Dans une procédure `Set`, l'instruction `Exit Property` est équivalente à l'instruction `Return`.  
  
 `Exit Select`  
 Quitte immédiatement le bloc `Select Case` dans lequel il apparaît.  L'exécution continue l'instruction qui suit l'instruction `End Select`.  `Exit Select` peut être utilisé uniquement à l'intérieur d'une instruction `Select Case`  
  
 `Exit Sub`  
 Quitte immédiatement la procédure `Sub` dans laquelle il apparaît.  L'exécution se poursuit avec l'instruction qui suit l'instruction qui a appelé la procédure `Sub`.  `Exit Sub` peut être utilisé uniquement à l'intérieur d'une procédure `Sub`.  
  
 Dans une procédure `Sub`, l'instruction `Exit Sub` est équivalente à l'instruction `Return`.  
  
 `Exit Try`  
 Quitte immédiatement le bloc `Try` ou `Catch` dans lequel il apparaît.  L'exécution continue avec le bloc `Finally` s'il y en a un, ou avec l'instruction qui suit l'instruction `End Try` `Exit Try` peut être utilisé uniquement à l'intérieur d'un bloc `Try` ou `Catch`, et pas à l'intérieur d'un bloc `Finally`.  
  
 `Exit While`  
 Quitte immédiatement la boucle `While` dans laquelle il apparaît.  L'exécution continue l'instruction qui suit l'instruction `End While`.  `Exit While` peut être utilisé uniquement à l'intérieur d'une boucle `While`.  Utilisée à l'intérieur de boucles `While` imbriquées, l'instruction `Exit While` transfère le contrôle à la boucle située à un niveau au\-dessus de la boucle dans laquelle `Exit While` apparaît.  
  
## Notes  
 Ne confondez pas les instructions `Exit` avec les instructions `End`.  `Exit` ne définit pas la fin d'une instruction.  
  
## Exemple  
 Dans l'exemple suivant, la condition de boucle arrête la boucle lorsque la variable `index` est supérieure à 100.  Cependant, avec l'instruction `If` dans la boucle, l'instruction `Exit Do` arrête la boucle lorsque la variable d'index est supérieure à 10.  
  
 [!CODE [VbVbalrStatements#133](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#133)]  
  
## Exemple  
 L'exemple suivant assigne la valeur de retour au nom de la fonction `myFunction`, puis utilise l'instruction `Exit Function` pour retourner de la fonction  
  
 [!CODE [VbVbalrStatements#23](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#23)]  
  
## Exemple  
 L'exemple suivant utilise [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) pour assigner la valeur de retour et pour quitter la fonction.  
  
 [!CODE [VbVbalrStatements#24](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#24)]  
  
## Voir aussi  
 [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md)   
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)   
 [For Each...Next, instruction](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next, instruction](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)   
 [Stop Statement](../../../visual-basic/language-reference/statements/stop-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)