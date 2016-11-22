---
title: "Comment&#160;: enregistrer des messages lorsque l&#39;application d&#233;marre ou s&#39;arr&#234;te (Visual Basic) | Microsoft Docs"
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
  - "journaux des événements, arrêt"
  - "My.Application.Log (objet), journalisation"
  - "Startup (événement)"
  - "journaux des événements, démarrage"
  - "Shutdown (événement)"
  - "My.Log (objet), journalisation"
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: enregistrer des messages lorsque l&#39;application d&#233;marre ou s&#39;arr&#234;te (Visual Basic)
Vous pouvez utiliser les objets `My.Application.Log` et `My.Log` pour enregistrer des informations sur les événements qui se produisent dans votre application. Cet exemple montre comment utiliser la méthode `My.Application.Log.WriteEntry` avec les événements `Startup` et `Shutdown` pour enregistrer des informations de traçage.  
  
### Pour accéder au code du gestionnaire d’événements de l’application  
  
1.  Sélectionnez un projet dans l'**Explorateur de solutions**. Dans le menu **Projet**, choisissez **Propriétés**.  
  
2.  Cliquez sur l’onglet **Application**.  
  
3.  Cliquez sur le bouton **Afficher les événements de l’application** pour ouvrir l’éditeur de code.  
  
     Le fichier ApplicationEvents.vb s’ouvre.  
  
### Pour enregistrer des messages quand l’application démarre  
  
1.  Ouvrez le fichier ApplicationEvents.vb dans l’éditeur de code. Dans le menu **Général**, choisissez **Événements MyApplication**.  
  
2.  Dans le menu **Déclarations**, choisissez **Démarrage**.  
  
     L’application déclenche l’événement <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> avant l’exécution de l’application principale.  
  
3.  Ajoutez la méthode `My.Application.Log.WriteEntry` au gestionnaire d’événements `Startup`.  
  
     [!CODE [VbVbalrMyApplicationLog#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#1)]  
  
### Pour enregistrer des messages quand l’application s’arrête  
  
1.  Ouvrez le fichier ApplicationEvents.vb dans l’éditeur de code. Dans le menu **Général**, choisissez **Événements MyApplication**.  
  
2.  Dans le menu **Déclarations**, choisissez **Arrêt**.  
  
     L’application déclenche l’événement <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> après l’exécution de l’application principale, mais avant qu’elle s’arrête.  
  
3.  Ajoutez la méthode `My.Application.Log.WriteEntry` au gestionnaire d’événements `Shutdown`.  
  
     [!CODE [VbVbalrMyApplicationLog#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#2)]  
  
## Exemple  
 Vous pouvez utiliser le **Concepteur de projets** pour accéder aux événements de l’application dans l’éditeur de code. Pour plus d'informations, consultez [Page Application, Concepteur de projets \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
 [!CODE [VbVbalrMyApplicationLog#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#3)]  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Page Application, Concepteur de projets \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Utilisation des journaux des applications](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)