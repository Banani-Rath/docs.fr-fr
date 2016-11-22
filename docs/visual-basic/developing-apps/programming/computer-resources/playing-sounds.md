---
title: "Playing Sounds (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
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
  - "system sounds, playing"
  - "system sounds"
  - "playing sounds, Visual Basic"
  - "sound loops"
  - "My.Computer.Audio object, tasks"
  - "sounds, playing"
  - "sounds, background"
  - "playing sounds"
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Playing Sounds (Visual Basic)
L'objet `My.Computer.Audio` comporte des méthodes permettant de lire les sons.  
  
## Lire des sons  
 L'arrière\-plan permet à l'application d'exécuter du code pendant la lecture des sons.  La méthode `My.Computer.Audio.Play` permet à l'application de ne lire qu'un seul fond sonore à la fois. Lorsqu'elle lit un nouveau fond sonore, l'application arrête la lecture du fond sonore précédent.  Vous pouvez également lire un son et attendre qu'il s'arrête.  
  
 Dans l'exemple suivant, la méthode d' `My.Computer.Audio.Play` lit un son.  Lorsque `AudioPlayMode.WaitToComplete` est spécifié, `My.Computer.Audio.Play` attend que le son s'arrête pour que l'exécution du code appelant continue.  En utilisant cet exemple, vous devez vous assurer que le nom de fichier fait référence à un fichier son .wav présent sur votre ordinateur  
  
 [!CODE [VbVbalrMyComputer#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#15)]  
  
 Dans l'exemple suivant, la méthode d' `My.Computer.Audio.Play` lit un son.  En utilisant cet exemple, vous devez vous assurer que les ressources de l'application incluent un fichier son .wav nommé Waterfall.  
  
 [!CODE [VbVbalrMyComputer#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#16)]  
  
## Lire les sons de bouclage  
 Dans l'exemple suivant, la méthode d' `My.Computer.Audio.Play` lit le son spécifié en arrière\-plan lorsque `PlayMode.BackgroundLoop` est spécifié.  En utilisant cet exemple, vous devez vous assurer que le nom de fichier fait référence à un fichier son .wav présent sur votre ordinateur.  
  
 [!CODE [VbVbalrMyComputer#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#11)]  
  
 Dans l'exemple suivant, la méthode d' `My.Computer.Audio.Play` lit le son spécifié en arrière\-plan lorsque `PlayMode.BackgroundLoop` est spécifié.  En utilisant cet exemple, vous devez vous assurer que les ressources de l'application incluent un fichier son .wav nommé Waterfall.  
  
 [!CODE [VbVbalrMyComputer#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#12)]  
  
 L'exemple de code précédent est également disponible sous forme de extrait de code IntelliSense.  Dans le sélecteur d'extrait de code, il se trouve dans **Applications Windows Forms \> Son**.  Pour plus d'informations, consultez [Extraits de code](/visual-studio/ide/code-snippets).  
  
 En général, lorsqu'une application lit un son en boucle, elle doit finir par l'arrêter.  
  
## Arrêtant lire des sons en arrière\-plan  
 Utilisez la méthode `My.Computer.Audio.Stop` pour arrêter la lecture en cours du fonds sonore ou du son en boucle de l'application.  
  
 En général, lorsqu'une application lit un son en boucle, elle doit l'arrêter à un certain point.  
  
 L'exemple suivant arrête un son en en arrière\-plan.  
  
 [!CODE [VbVbalrMyComputer#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#18)]  
  
 L'exemple de code précédent est également disponible sous forme de extrait de code IntelliSense.  Dans le sélecteur d'extrait de code, il se trouve dans **Applications Windows Forms \> Son**.  Pour plus d'informations, consultez [Extraits de code](/visual-studio/ide/code-snippets).  
  
## Lire des sons système  
 Utilisez la méthode `My.Computer.Audio.PlaySystemSound` pour lire le son système spécifié.  
  
 La méthode `My.Computer.Audio.PlaySystemSound` prend comme paramètre l'un des membres partagés de la classe <xref:System.Media.SystemSound>.  Le son système <xref:System.Media.SystemSounds.Asterisk%2A> indique généralement des erreurs.  
  
 L'exemple suivant utilise la méthode d' `My.Computer.Audio.PlaySystemSound` pour lire un son système.  
  
 [!CODE [VbVbalrMyComputer#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#17)]  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>