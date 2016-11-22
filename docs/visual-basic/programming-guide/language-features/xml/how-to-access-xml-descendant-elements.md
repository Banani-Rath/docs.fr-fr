---
title: "How to: Access XML Descendant Elements (Visual Basic) | Microsoft Docs"
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
  - "XML descendent axis property [Visual Basic]"
  - "XML axis [Visual Basic], descendent"
  - "descendent axis property [Visual Basic]"
  - "XML [Visual Basic], accessing"
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Access XML Descendant Elements (Visual Basic)
Cet exemple indique comment utiliser une propriété d'axe descendant pour accéder à tous les éléments XML portant un nom spécifié et contenus sous un élément XML.  Il utilise, en particulier, la propriété `Value` pour obtenir la valeur du premier élément de la collection que la propriété d'axe descendant `name` retourne.  La propriété d'axe descendant `name` obtient tous les éléments nommés `name` et contenus dans l'objet `contacts`.  Cet exemple utilise également la propriété d'axe descendant `phone` pour accéder à tous les descendants nommés `phone` et contenus dans l'objet `contacts`.  
  
## Exemple  
 [!CODE [VbXMLSamples#31](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#31)]  
  
## Compilation du code  
 Cet exemple nécessite :  
  
-   Référence à l'espace de noms <xref:System.Xml.Linq>.  
  
## Voir aussi  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>   
 [XML Descendant Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [XML Value Property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)   
 [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)