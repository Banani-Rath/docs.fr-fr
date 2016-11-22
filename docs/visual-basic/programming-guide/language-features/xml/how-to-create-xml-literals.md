---
title: "How to: Create XML Literals (Visual Basic) | Microsoft Docs"
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
  - "XML literals [Visual Basic], creating"
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Create XML Literals (Visual Basic)
Vous pouvez créer directement un document, fragment ou élément XML dans le code en utilisant un littéral XML.  Les exemples dans cette rubrique montrent comment créer un document XML et un élément XML possédant trois éléments enfants.  
  
 Vous pouvez également utiliser les API [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] pour créer des objets [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  Pour plus d'informations, consultez <xref:System.Xml.Linq.XElement>.  
  
### Pour créer un élément XML  
  
-   Créez l'élément XML inline en utilisant la syntaxe de littéral XML qui est identique à la syntaxe XML réelle.  
  
     [!CODE [VbXMLSamples#5](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#5)]  
  
     Exécutez le code.  Le résultat généré par ce code est le suivant :  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### Pour créer un document XML  
  
-   Créez le document XML inline.  Le code suivant crée un document XML qui possède une syntaxe de littéral, une déclaration XML, une instruction de traitement, un commentaire et un élément contenant un autre élément.  
  
     [!CODE [VbXMLSamples#30](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#30)]  
  
     Exécutez le code.  Le résultat généré par ce code est le suivant :  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works.  -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## Voir aussi  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)