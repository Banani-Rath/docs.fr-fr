---
title: "Stop Statement (Visual Basic) | Microsoft Docs"
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
  - "vb.Stop"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "breakpoints, Stop statements"
  - "Stop statements, syntax"
  - "Stop statements"
  - "execution, suspending"
  - "processing, interrupting"
  - "processes, interrupting"
  - "execution, stopping"
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Stop Statement (Visual Basic)
Interrompt l'exécution.  
  
## Syntaxe  
  
```  
Stop  
```  
  
## Notes  
 Vous pouvez placer des instructions `Stop` n'importe où dans les procédures afin d'en interrompre l'exécution.  Utiliser l'instruction `Stop` revient à placer un point d'arrêt dans le code.  
  
 L'instruction `Stop` interrompt l'exécution, mais contrairement à `End`, elle ne ferme pas les fichiers et n'efface pas les variables, sauf si elle est placée dans un fichier exécutable \(.exe\) compilé.  
  
> [!NOTE]
>  Si l'instruction `Stop` figure dans le code qui s'exécute en dehors de l'environnement de développement intégré \(IDE, Integrated Development Environment\), le débogueur est appelé.  C'est le cas quel que soit le mode de compilation du code \(mode débogage ou mode commercial\).  
  
## Exemple  
 Cet exemple utilise l'instruction `Stop` pour suspendre l'exécution à chaque itération de la boucle `For...Next`.  
  
 [!CODE [VbVbalrStatements#56](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#56)]  
  
## Voir aussi  
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)