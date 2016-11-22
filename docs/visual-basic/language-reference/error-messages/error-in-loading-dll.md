---
title: "Error in loading DLL (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID48"
dev_langs: 
  - "VB"
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Error in loading DLL (Visual Basic)
Une bibliothèque de liens dynamiques \(DLL, Dynamic\-Link Library\) est une bibliothèque spécifiée dans la clause `Lib` d'une instruction `Declare`.  Cette erreur peut avoir plusieurs causes :  
  
-   Le fichier n'est pas un exécutable DLL.  
  
-   Le fichier n'est pas une DLL Microsoft Windows.  
  
-   La DLL fait référence à une autre DLL qui n'est pas présente.  
  
-   La DLL ou la DLL référencée n'est pas un répertoire spécifié par le chemin d'accès.  
  
### Pour corriger cette erreur  
  
-   Si le fichier est un fichier texte source et non un exécutable DLL, il doit être compilé et lié à un formulaire exécutable DLL.  
  
-   Si le fichier n'est pas une DLL Microsoft Windows, vous devez obtenir l'équivalent Microsoft Windows.  
  
-   Si la DLL fait référence à une autre DLL qui n'est pas présente, vous devez obtenir la DLL référencée et la rendre disponible.  
  
-   Si la DLL ou la DLL référencée n'est pas un répertoire spécifié par le chemin d'accès, déplacez la DLL vers un répertoire référencé.  
  
## Voir aussi  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)