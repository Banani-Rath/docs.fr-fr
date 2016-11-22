---
title: "Comment&#160;: analyser des chemins d&#39;acc&#232;s dans Visual Basic | Microsoft Docs"
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
  - "noms de fichier, analyse (Visual Basic)"
  - "analyse des chemins de fichier (Visual Basic)"
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: analyser des chemins d&#39;acc&#232;s dans Visual Basic
L’objet <xref:Microsoft.VisualBasic.FileIO.FileSystem> fournit plusieurs méthodes qui facilitent l’analyse des chemins de fichier.  
  
-   La méthode <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> combine deux chemins et affiche un chemin combiné au format correct.  
  
-   La méthode <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> retourne le chemin absolu du parent du chemin fourni.  
  
-   La méthode <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> retourne un objet <xref:System.IO.FileInfo> qui peut être interrogé pour déterminer les propriétés du fichier, telles que son nom et son chemin.  
  
 Ne vous basez pas sur l’extension de nom de fichier pour déterminer le contenu d’un fichier. Par exemple, le fichier Form1.vb peut ne pas être un fichier source Visual Basic.  
  
### Pour déterminer le nom et le chemin d’un fichier  
  
-   Utilisez les propriétés <xref:System.IO.FileInfo.DirectoryName%2A> et <xref:System.IO.FileInfo.Name%2A> de l’objet <xref:System.IO.FileInfo> pour déterminer le nom et le chemin d’un fichier. Cet exemple détermine le nom et le chemin d’un fichier, puis les affiche.  
  
     [!CODE [VbVbcnMyFileSystem#54](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#54)]  
  
### Pour combiner le nom et le répertoire d’un fichier en un chemin complet  
  
-   Utilisez la méthode `CombinePath`, en spécifiant le répertoire et le nom du fichier. Cet exemple combine les chaînes `folderPath` et `fileName` créées dans l’exemple précédent, puis affiche le résultat.  
  
     [!CODE [VbVbcnMyFileSystem#55](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#55)]  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>   
 <xref:System.IO.FileInfo>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>   
 [How to: Get the Collection of Files in a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)