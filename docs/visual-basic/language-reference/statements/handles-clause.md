---
title: "Handles Clause (Visual Basic) | Microsoft Docs"
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
  - "Handles"
  - "vb.Handles"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Handles keyword"
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Handles Clause (Visual Basic)
Déclare qu'une procédure gère un événement spécifié.  
  
## Syntaxe  
  
```  
  
proceduredeclaration Handles eventlist  
```  
  
## Composants  
 `proceduredeclaration`  
 Déclaration de procédure `Sub` pour la procédure qui gérera l'événement.  
  
 `eventlist`  
 Liste des événements pour `proceduredeclaration` à gérer, séparés par des virgules.  Les événements doivent être déclenchés par la classe de base pour la classe en cours ou par un objet déclaré à l'aide du mot clé `WithEvents`.  
  
## Notes  
 Utilisez le mot clé `Handles` à la fin d'une déclaration de procédure pour que celle\-ci gère les événements déclenchés par une variable objet déclarée à l'aide du mot clé `WithEvents`.  Le mot clé `Handles` peut également être utilisé dans une classe dérivée pour gérer des événements à partir d'une classe de base.  
  
 Le mot clé `Handles` et l'instruction `AddHandler` vous permettent de spécifier que des procédures particulières gèrent des événements particuliers, mais il existe des différences.  Utilisez le mot clé `Handles` quand vous définissez une procédure pour indiquer qu'elle gère un événement particulier.  L'instruction `AddHandler` connecte les procédures aux événements au moment de l'exécution.  Pour plus d'informations, consultez [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md).  
  
 Pour les événements personnalisés, l'application appelle l'accesseur `AddHandler` de l'événement quand elle ajoute la procédure comme gestionnaire d'événements.  Pour plus d'informations sur les événements personnalisés, consultez [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Exemple  
 [!CODE [VbVbalrEvents#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#2)]  
  
 L'exemple suivant montre comment une classe dérivée peut utiliser l'instruction `Handles` pour gérer un événement à partir d'une classe de base.  
  
 [!CODE [VbVbalrEvents#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#3)]  
  
## Exemple  
 L'exemple suivant contient deux gestionnaires d'événements de bouton pour un projet **Application WPF**.  
  
 [!CODE [VbVbalrEvents#41](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#41)]  
  
## Exemple  
 L'exemple suivant est équivalent à l'exemple précédent.  La liste `eventlist` dans la clause `Handles` contient les événements pour les deux boutons.  
  
 [!CODE [VbVbalrEvents#42](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#42)]  
  
## Voir aussi  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)   
 [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)