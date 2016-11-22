---
title: "Enumerations and Name Qualification (Visual Basic) | Microsoft Docs"
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
  - "declarations, enumerations"
  - "Imports statement, namespace declarations"
  - "declaring namespaces, enumerations"
  - "name collisions"
  - "ambiguous names, enumerations"
  - "enumerations [Visual Basic], name qualification"
  - "names, avoiding conflicts"
  - "namespaces, declaring"
  - "naming conflicts, enumerations"
  - "naming conflicts, qualifying names"
  - "declaring enumerations"
  - "references, enumeration members"
  - "naming conventions, naming conflicts"
  - "declarations, namespaces"
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Enumerations and Name Qualification (Visual Basic)
Lorsque vous faites référence à un membre d'une énumération, vous devez généralement le désigner par le nom de votre énumération.  Par exemple, pour faire référence au membre `Sunday` de votre énumération `Days`, vous devez utiliser la syntaxe suivante :  
  
 [!CODE [VbEnumsTask#18](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#18)]  
  
## Utilisation de l'instruction Imports  
 Vous pouvez éviter d'employer le nom complet en ajoutant une instruction `Imports` dans la section des déclarations d'espace de noms de votre code, comme dans l'exemple suivant :  
  
 [!CODE [VbEnumsTask#22](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#22)]  
  
 Une instruction `Imports` importe des noms d'espaces de noms à partir de projets et d'assemblys référencés et à partir de noms définis dans le même projet que le module dans lequel figure l'instruction.  Dès que cette instruction est ajoutée, vous pouvez faire référence aux membres de l'énumération sans qualification, comme dans l'exemple suivant :  
  
 [!CODE [VbEnumsTask#24](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#24)]  
  
 Si vous organisez des ensembles de constantes connexes dans des énumérations, vous pouvez utiliser les mêmes noms de constantes dans des contextes distincts.  Par exemple, vous pouvez utiliser des noms identiques pour les constantes des jours de la semaine dans les énumérations `Days` et `WorkDays`.  Si vous utilisez l'instruction `Imports` avec vos énumérations, vous devez éviter d'utiliser des références ambiguës.  Prenons l'exemple suivant :  
  
 [!CODE [VbEnumsTask#22](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#22)]  
  
 [!CODE [VbEnumsTask#25](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#25)]  
  
 Si `Monday` est un membre des énumérations `Days` et `Workdays`, ce code génère une erreur de compilation.  Pour éviter les références ambiguës lorsque vous faites référence à une constante individuelle, vous devez désigner le nom de la constante par son énumération.  Le code suivant fait référence aux constantes `Saturday` dans les énumérations `Days` et `WorkDays`.  
  
 [!CODE [VbEnumsTask#32](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#32)]  
  
## Voir aussi  
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)