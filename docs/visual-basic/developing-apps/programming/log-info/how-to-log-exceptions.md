---
title: "How to: Log Exceptions in Visual Basic | Microsoft Docs"
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
  - "exceptions, logging"
  - "exceptions, tracking"
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Log Exceptions in Visual Basic
Vous pouvez utiliser les objets `My.Application.Log` et `My.Log` pour enregistrer des informations sur les exceptions qui se produisent dans votre application.  Ces exemples indiquent comment utiliser la méthode `My.Application.Log.WriteException` pour enregistrer des exceptions que vous interceptez explicitement et des exceptions qui ne sont pas gérées.  
  
 Pour enregistrer des informations de traçage, utilisez la méthode `My.Application.Log.WriteEntry`.  Pour plus d'informations, consultez <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>.  
  
### Pour enregistrer une exception gérée  
  
1.  Créez la méthode qui générera les informations sur les exceptions.  
  
     [!CODE [VbVbalrMyApplicationLog#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#9)]  
  
2.  Utilisez un bloc `Try...Catch` pour intercepter l'exception.  
  
     [!CODE [VbVbalrMyApplicationLog#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#6)]  
  
3.  Placez le code susceptible de générer une exception dans le bloc `Try`.  
  
     Supprimez les marques de commentaire des lignes `Dim` et `MsgBox` pour provoquer une exception <xref:System.NullReferenceException>.  
  
     [!CODE [VbVbalrMyApplicationLog#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#7)]  
  
4.  Dans le bloc `Catch`, utilisez la méthode `My.Application.Log.WriteException` pour écrire les informations sur les exceptions.  
  
     [!CODE [VbVbalrMyApplicationLog#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#8)]  
  
     L'exemple suivant affiche le code complet pour enregistrer une exception gérée.  
  
     [!CODE [VbVbalrMyApplicationLog#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#10)]  
  
### Pour enregistrer une exception non gérée  
  
1.  Sélectionnez un projet dans l'**Explorateur de solutions**.  Dans le menu **Projet**, choisissez **Propriétés**.  
  
2.  Cliquez sur l'onglet **Application**.  
  
3.  Cliquez sur le bouton **Afficher les événements de l'application** pour ouvrir l'éditeur de code.  
  
     Le fichier ApplicationEvents.vb s'ouvre.  
  
4.  Ouvrez le fichier ApplicationEvents.vb dans l'éditeur de code.  Dans le menu **Général**, choisissez **Événements MyApplication**.  
  
5.  Dans le menu **Déclarations**, choisissez **UnhandledException**.  
  
     L'application déclenche l'événement <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> avant l'exécution de l'application principale.  
  
6.  Ajoutez la méthode `My.Application.Log.WriteException` au gestionnaire d'événements `UnhandledException`.  
  
     [!CODE [VbVbalrMyApplicationLog#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#4)]  
  
     L'exemple suivant affiche le code complet pour enregistrer une exception non gérée.  
  
     [!CODE [VbVbalrMyApplicationLog#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#5)]  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Utilisation des journaux des applications](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Comment : écrire des messages de journal](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Procédure pas à pas : détermination de l'emplacement des informations My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [Procédure pas à pas : modification de l'emplacement des informations My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)