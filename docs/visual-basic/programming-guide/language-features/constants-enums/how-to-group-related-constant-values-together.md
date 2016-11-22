---
title: "How to: Group Related Constant Values Together (Visual Basic) | Microsoft Docs"
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
  - "enumerations [Visual Basic], constants"
  - "constants, grouping together"
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Group Related Constant Values Together (Visual Basic)
Une énumération est le meilleur moyen de regrouper des constantes connexes.  L'ajout d'une instruction `Enum` dans la section des déclarations d'une classe ou d'un module permet de créer une énumération.  Pour plus d'informations, consultez [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).  
  
### Pour regrouper des valeurs de constante connexes  
  
1.  Écrivez une déclaration qui inclut un niveau d'accès de code, le mot clé `Enum` et un nom valide.  Cet exemple crée l'énumération `Private`, `temperatureValues`.  
  
     [!CODE [VbEnumsTask#21](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#21)]  
  
2.  Définissez les constantes dans l'énumération.  Cet exemple crée l'énumération `Public` `temperatureValues` et assigne ses valeurs.  
  
     [!CODE [VbEnumsTask#1](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#1)]  
  
## Voir aussi  
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)