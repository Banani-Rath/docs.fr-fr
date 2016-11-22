---
title: "How to: Refer to an Enumeration Member (Visual Basic) | Microsoft Docs"
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
  - "enumerations [Visual Basic], referring to"
  - "values, associating constant values with names"
  - "enumeration members"
  - "constants, enumerated"
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Refer to an Enumeration Member (Visual Basic)
Les énumérations offrent un moyen pratique d'utiliser des ensembles de constantes connexes et d'associer des valeurs de constantes à des noms.  Par exemple, vous pouvez déclarer une énumération pour un ensemble de constantes entières associées aux jours de la semaine, et utiliser ensuite les noms des jours dans le code plutôt que leurs valeurs entières.  
  
 Vous pouvez éviter d'utiliser des noms qualifiés complets avec l'instruction `Imports`.  Pour plus d'informations, consultez [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### Pour faire référence à un membre d'énumération  
  
-   Qualifiez le nom de membre avec l'énumération.  Par exemple, l'exemple suivant assigne le membre `Saturday` de l'énumération `FirstDayOfWeek` à la variable `DayValue`.  
  
     [!CODE [VbEnumsTask#19](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#19)]  
  
## Voir aussi  
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)