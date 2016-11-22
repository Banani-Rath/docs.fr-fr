---
title: "&lt;example&gt; (Visual Basic) | Microsoft Docs"
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
  - "example XML tag"
  - "<example> XML tag"
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;example&gt; (Visual Basic)
Spécifie un exemple pour le membre.  
  
## Syntaxe  
  
```  
<example>description</example>  
```  
  
#### Paramètres  
 `description`  
 Description de l'exemple de code.  
  
## Notes  
 La balise `<example>` vous permet de spécifier un exemple d'utilisation d'une méthode ou de tout autre membre de bibliothèque.  Cela implique généralement l'utilisation de la balise [\<code\>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Compilez avec [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
 Cet exemple utilise la balise `<example>` pour inclure un exemple afin d'utiliser le champ `ID`.  
  
 [!CODE [VbVbcnXmlDocComments#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#2)]  
  
## Voir aussi  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)