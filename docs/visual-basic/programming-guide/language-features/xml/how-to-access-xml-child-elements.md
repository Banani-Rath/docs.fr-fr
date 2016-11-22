---
title: "How to: Access XML Child Elements (Visual Basic) | Microsoft Docs"
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
  - "XML axis [Visual Basic], child"
  - "child axis property [Visual Basic]"
  - "XML child axis property [Visual Basic]"
  - "XML [Visual Basic], accessing"
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Access XML Child Elements (Visual Basic)
Cet exemple indique comment utiliser une propriété d'axe enfant pour accéder à tous les éléments enfants XML qui ont un nom spécifié dans un élément XML.  Il utilise, en particulier, la propriété <xref:System.Xml.Linq.XElement.Value%2A> pour obtenir la valeur du premier élément de la collection que la propriété d'axe enfant `name` retourne.  La propriété d'axe enfant `name` obtient tous les éléments enfants nommés `phone` dans l'objet `contact`.  Cet exemple utilise également la propriété d'axe enfant `phone` pour accéder à tous les éléments enfants nommés `phone` contenu dans l'objet `contact`.  
  
## Exemple  
 [!CODE [VbXMLSamples#10](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#10)]  
  
## Compilation du code  
 Cet exemple nécessite :  
  
-   Référence à l'espace de noms <xref:System.Xml.Linq>.  
  
## Voir aussi  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>   
 [XML Child Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)   
 [XML Value Property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)   
 [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)