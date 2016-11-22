---
title: "RemoveHandler Statement | Microsoft Docs"
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
  - "vb.RemoveHandlerMethod"
  - "vb.RemoveHandler"
  - "RemoveHandler"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "RemoveHandler keyword"
  - "RemoveHandler statement"
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# RemoveHandler Statement
Supprime l'association qui lie un événement et un gestionnaire d'événements.  
  
## Syntaxe  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## Composants  
  
|||  
|-|-|  
|Terme|Définition|  
|`event`|Nom de l'événement géré.|  
|`eventhandler`|Nom de la procédure qui gère actuellement l'événement.|  
  
## Notes  
 Les instructions `AddHandler` et `RemoveHandler` vous permettent de débuter et d'arrêter la gestion d'un événement particulier à tout moment au cours de l'exécution du programme.  
  
> [!NOTE]
>  Pour les événements personnalisés, l'instruction `RemoveHandler` appelle l'accesseur `RemoveHandler` de l'événement.  Pour plus d'informations sur les événements personnalisés, consultez [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Exemple  
 [!CODE [VbVbalrEvents#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#17)]  
  
## Voir aussi  
 [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)