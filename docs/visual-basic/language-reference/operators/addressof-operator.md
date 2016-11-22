---
title: "AddressOf Operator (Visual Basic) | Microsoft Docs"
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
  - "AddressOf"
  - "vb.AddressOf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddressOf operator"
  - "addresses, passing to API procedures"
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# AddressOf Operator (Visual Basic)
Crée une instance déléguée de procédure qui fait référence à la procédure spécifique.  
  
## Syntaxe  
  
```  
  
AddressOf procedurename  
```  
  
## Composants  
 `procedurename`  
 Obligatoire.  Spécifie la procédure à référencer par le délégué de procédure créé récemment.  
  
## Notes  
 L'opérateur `AddressOf` crée un délégué de fonction qui pointe vers la fonction spécifiée par `procedurename`.  Lorsque la procédure spécifiée est une méthode d'instance, le délégué de fonction fait référence à l'instance et à la méthode.  Ensuite, lorsque le délégué de fonction est appelé, la méthode spécifiée de l'instance spécifiée est appelée.  
  
 L'opérateur `AddressOf` peut être utilisé comme opérande d'un constructeur délégué ou bien dans un contexte où le type du délégué peut être déterminé par le compilateur.  
  
## Exemple  
 Cet exemple utilise l'opérateur `AddressOf` pour désigner un délégué qui va gérer l'événement `Click` d'un bouton.  
  
 [!CODE [VbVbalrDelegates#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDelegates#8)]  
  
## Exemple  
 L'exemple suivant utilise l'opérateur `AddressOf` pour désigner la fonction de démarrage d'un thread.  
  
 [!CODE [VbVbalrDelegates#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDelegates#9)]  
  
## Voir aussi  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)