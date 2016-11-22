---
title: "Iterator (Visual Basic) | Microsoft Docs"
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
  - "vb.Iterator"
helpviewer_keywords: 
  - "Iterator keyword [Visual Basic]"
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Iterator (Visual Basic)
Spécifie qu'une fonction ou un accesseur d' `Get` est un itérateur.  
  
## Notes  
 *Un itérateur* effectue une itération personnalisée sur une collection.  Un itérateur utilise l'instruction de [rendement](../../../visual-basic/language-reference/statements/yield-statement.md) pour retourner chaque élément dans la collection un par un.  Lorsqu'une instruction d' `Yield` est atteinte, la position actuelle dans le code est conservée.  l'exécution est redémarrée de cet emplacement la prochaine fois que la fonction d'itérateur est appelé.  
  
 Un itérateur peut être implémenté en tant que fonction ou comme accesseurs d' `Get` d'une définition de propriété.  Le modificateur d' `Iterator` apparaît dans la déclaration de la fonction d'itérateur ou de l'accesseur d' `Get` .  
  
 Vous appelez un itérateur de code client à l'aide de [For Each...Next, instruction](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Le type de retour d'une fonction d'itérateur ou d'un accesseur d' `Get` peut être <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, ou <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Un itérateur ne peut contenir que des paramètres d' `ByRef` .  
  
 Un itérateur ne peut pas apparaître dans un événement, un constructeur d'instance, un constructeur statique, ou un destructeur statique.  
  
 Un itérateur peut être une fonction anonyme.  Pour plus d'informations, consultez [Itérateurs](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Pour plus d'informations sur les itérateurs, consultez [Itérateurs](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Utilisation  
 Le modificateur `Iterator` peut être utilisé dans les contextes suivants :  
  
-   [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## Exemple  
 L'exemple suivant illustre une fonction d'itérateur.  La fonction d'itérateur a une instruction d' `Yield` qui est à l'intérieur d'une boucle de [Pour… next](../../../visual-basic/language-reference/statements/for-next-statement.md) .  Chaque itération du corps du didacticiel de [Pour chaque](../../../visual-basic/language-reference/statements/for-each-next-statement.md) dans `Main` crée un appel à la fonction d'itérateur d' `Power` .  Chaque appel à la fonction d'itérateur continue à l'exécution suivante de l'instruction d' `Yield` , qui se produit pendant l'itération suivante de la boucle d' `For…Next` .  
  
 [!CODE [VbVbalrStatements#98](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#98)]  
  
## Exemple  
 l'exemple suivant montre un accesseur d' `Get` qui est un itérateur.  Le modificateur d' `Iterator` est dans la déclaration de propriété.  
  
 [!CODE [VbVbalrStatements#99](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#99)]  
  
 Pour obtenir d'autres exemples, consultez [Itérateurs](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Voir aussi  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>   
 [Itérateurs](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [yield, instruction](../../../visual-basic/language-reference/statements/yield-statement.md)