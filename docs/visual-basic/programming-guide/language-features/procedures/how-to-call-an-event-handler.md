---
title: "How to: Call an Event Handler in Visual Basic | Microsoft Docs"
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
helpviewer_keywords: 
  - "Visual Basic code, procedures"
  - "event handlers, calling"
  - "event handlers"
  - "procedures, event handlers"
  - "procedures, calling"
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Call an Event Handler in Visual Basic
Un *événement* est une action ou une occurrence \(par exemple un clic de souris ou le dépassement d'un seuil de crédit\) reconnue par un composant de programme pour laquelle vous pouvez écrire du code en réponse.  Un *gestionnaire d'événements* est le code que vous écrivez pour répondre à un événement.  
  
 Un gestionnaire d'événements en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] est une procédure `Sub`.  Toutefois, vous ne l'appelez normalement pas de la même manière que d'autres procédures `Sub`.  À la place, vous identifiez la procédure comme un gestionnaire pour l'événement.  Pour cela, vous pouvez utiliser soit une clause [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) et une variable[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md), soit une [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).  L'utilisation d'une clause `Handles` est la manière par défaut de déclarer un gestionnaire d'événements en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Les gestionnaires d'événements sont écrits de cette manière par les concepteurs lorsque vous programmez dans l'environnement de développement intégré \(IDE\).  L'instruction `AddHandler` convient pour déclencher dynamiquement des événements au moment de l'exécution.  
  
 Lorsque l'événement se produit, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] appelle automatiquement la procédure de gestionnaire d'événements.  Tout code qui a accès à l'événement peut déclencher celui\-ci en exécutant une [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Vous pouvez associer plusieurs gestionnaires d'événements au même événement.  Dans quelques cas, vous pouvez dissocier un gestionnaire pour un événement.  Pour plus d'informations, consultez [Events](../../../../visual-basic/programming-guide/language-features/events/events.md).  
  
### Pour appeler un gestionnaire d'événements à l'aide de Handles et de WithEvents  
  
1.  Assurez\-vous que l'événement est déclaré avec une [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Déclarez une variable objet au niveau du module ou de la classe, à l'aide du mot clé [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).  La clause `As` pour cette variable doit spécifier la classe qui déclenche l'événement.  
  
3.  Dans la déclaration de la procédure `Sub` de gestion des événements, ajoutez une clause [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) qui spécifie la variable `WithEvents` et le nom d'événement.  
  
4.  Lorsque l'événement se produit, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] appelle automatiquement la procédure `Sub`.  Votre code peut utiliser une instruction `RaiseEvent` pour faire en sorte que l'événement se produise.  
  
     L'exemple suivant définit un événement et une variable `WithEvents` qui font référence à la classe qui déclenche l'événement.  La procédure `Sub` de gestion des événements utilise une clause `Handles` pour spécifier la classe et l'événement qu'elle gère.  
  
     [!CODE [VbVbcnProcedures#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#4)]  
  
### Pour appeler un gestionnaire d'événements à l'aide d'AddHandler  
  
1.  Assurez\-vous que l'événement est déclaré avec une instruction `Event`.  
  
2.  Exécutez une [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) pour connecter dynamiquement la procédure `Sub` de gestion des événements avec l'événement.  
  
3.  Lorsque l'événement se produit, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] appelle automatiquement la procédure `Sub`.  Votre code peut utiliser une instruction `RaiseEvent` pour faire en sorte que l'événement se produise.  
  
     L'exemple suivant définit une procédure `Sub` pour gérer l'événement <xref:System.Windows.Forms.Form.Closing> d'un formulaire.  Il utilise ensuite l'[AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) pour associer la procédure `catchClose` en tant que gestionnaire d'événements pour <xref:System.Windows.Forms.Form.Closing>.  
  
     [!CODE [VbVbcnProcedures#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#5)]  
  
     Vous pouvez dissocier un gestionnaire d'événements d'un événement en exécutant l'[RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## Voir aussi  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [How to: Create a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [How to: Call a Procedure that Does Not Return a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)