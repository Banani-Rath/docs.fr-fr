---
title: "&lt;summary&gt; (Visual Basic) | Microsoft Docs"
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
  - "<summary> XML tag"
  - "summary XML tag"
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;summary&gt; (Visual Basic)
Spécifie le résumé du membre.  
  
## Syntaxe  
  
```  
<summary>description</summary>  
```  
  
#### Paramètres  
 `description`  
 Résumé de l'objet.  
  
## Notes  
 Utilisez les balises `<summary>` pour décrire un type ou un membre de type.  Utilisez [\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md) pour ajouter des informations complémentaires à une description de type.  
  
 Le texte de la balise d' `<summary>` est la seule source d'informations sur le type dans Intellisense, et est également affiché dans l'Explorateur d'objets.  Pour plus d'informations sur l'Explorateur d'objets, consultez [Affichage de la structure du code](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Compilez avec [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
 Cet exemple utilise la balise `<summary>` pour décrire la méthode `ResetCounter` et la propriété `Counter`.  
  
 [!CODE [VbVbcnXmlDocComments#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#1)]  
  
## Voir aussi  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)