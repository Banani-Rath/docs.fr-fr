---
title: "&lt;c&gt; (Visual Basic) | Microsoft Docs"
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
  - "c XML tag"
  - "<c> XML tag"
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;c&gt; (Visual Basic)
Indique que le texte d'une description constitue du code.  
  
## Syntaxe  
  
```  
<c>text</c>  
```  
  
#### Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`text`|Texte que vous souhaitez indiquer en tant que code.|  
  
## Notes  
 La balise `<c>` permet d'indiquer que le texte d'une description doit être marqué comme étant du code.  Utilisez [\<code\>](../../../visual-basic/language-reference/xmldoc/code.md) pour indiquer que plusieurs lignes constituent du code.  
  
 Compilez avec [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
 Cet exemple utilise la balise `<c>` dans la section sommaire pour indiquer que `Counter` constitue du code.  
  
 [!CODE [VbVbcnXmlDocComments#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#1)]  
  
## Voir aussi  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)