---
title: "How to: Retrieve the Contents of the My Documents Directory in Visual Basic | Microsoft Docs"
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
  - "My Documents directory"
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Retrieve the Contents of the My Documents Directory in Visual Basic
L'objet <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> peut être utilisé pour lire de nombreux répertoires **Tous les utilisateurs**, tels que **Mes documents** ou **Bureau**.  
  
### Pour lire le dossier Mes documents  
  
-   Utilisez la méthode `ReadAllText` pour lire le texte de chaque fichier dans un répertoire spécifique.  Le code suivant spécifie un répertoire et un fichier, puis utilise `ReadAllText` pour les lire dans la chaîne nommée `patients`.  
  
     [!CODE [VbVbcnMyFileSystem#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#15)]  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>