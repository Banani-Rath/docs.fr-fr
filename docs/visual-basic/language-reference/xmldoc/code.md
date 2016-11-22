---
title: "&lt;code&gt; (Visual Basic) | Microsoft Docs"
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
  - "code XML tag"
  - "<code> XML tag"
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;code&gt; (Visual Basic)
Indique que le texte contient plusieurs lignes de code.  
  
## Syntaxe  
  
```  
<code>content</code>  
```  
  
#### Paramètres  
 `content`  
 Texte à marquer comme étant du code.  
  
## Notes  
 Utilisez les balises `<code>` pour indiquer plusieurs lignes comme étant du code.  Utilisez [\<c\>](../../../visual-basic/language-reference/xmldoc/c.md) pour indiquer que le texte d'une description doit être marqué comme étant du code.  
  
 Compilez avec [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
 Cet exemple utilise la balise \<code\> pour inclure l'exemple de code pour utiliser le champ `ID`.  
  
 [!CODE [VbVbcnXmlDocComments#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#2)]  
  
## Voir aussi  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)