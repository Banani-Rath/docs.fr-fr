---
title: "XML comment exception must have a &#39;cref&#39; attribute | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc42319"
  - "vbc42319"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42319"
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# XML comment exception must have a &#39;cref&#39; attribute
La balise \<exception\> permet de documenter les exceptions qui peuvent être levées par une méthode.  L'attribut `cref` requis désigne le nom d'un membre qui est vérifié par le générateur de documentation.  Si le membre existe, il est traduit en nom d'élément canonique dans le fichier documentation.  
  
 **ID d'erreur :** BC42319  
  
### Pour corriger cette erreur  
  
-   Ajoutez l'attribut `cref` à l'exception comme suit :  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## Voir aussi  
 [\<exception\>](../../../visual-basic/language-reference/xmldoc/exception.md)   
 [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)   
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)