---
title: "&lt;typeparam&gt; (Visual Basic) | Microsoft Docs"
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
  - "typeparam XML tag"
  - "<typeparam> XML tag"
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;typeparam&gt; (Visual Basic)
Définit un nom de paramètre de type et une description.  
  
## Syntaxe  
  
```  
<typeparam name="name">description</typeparam>  
```  
  
#### Paramètres  
 `name`  
 Nom du paramètre de type.  Mettez le nom entre guillemets doubles \(" "\).  
  
 `description`  
 Description du paramètre de type.  
  
## Notes  
 Utilisez la balise `<typeparam>` dans le commentaire d'un type générique ou une déclaration de membre générique pour décrire l'un des paramètres de type.  
  
 Compilez avec [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
 Cet exemple utilise la balise `<typeparam>` pour décrire le paramètre `id`.  
  
 [!CODE [VbVbcnXmlDocComments#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#8)]  
  
## Voir aussi  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)