---
title: "How to: Declare and Call a Default Property in Visual Basic | Microsoft Docs"
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
  - "defaults, properties"
  - "properties [Visual Basic], default"
  - "procedures, defining"
  - "default properties, in Visual Basic"
  - "Visual Basic code, procedures"
  - "Visual Basic code, properties"
  - "default properties"
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Declare and Call a Default Property in Visual Basic
Une *propriété par défaut* est une classe ou une propriété de structure à laquelle votre code peut accéder sans la spécifier.  Lorsque le code appelant nomme une classe ou une structure, mais pas une propriété et lorsque le contexte autorise l'accès à une propriété, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] résout l'accès à cette classe ou à la propriété par défaut de la structure s'il en existe une.  
  
 Une classe ou une structure peut avoir au plus une propriété par défaut.  Toutefois, vous pouvez surcharger une propriété par défaut et avoir plusieurs versions de celle\-ci.  
  
 Pour plus d'informations, consultez [Default](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### Pour déclarer une propriété par défaut  
  
1.  Déclarez normalement la propriété.  Ne spécifiez pas le mot clé `Shared` ou `Private`.  
  
2.  Incluez le mot clé `Default` dans la déclaration de propriété.  
  
3.  Spécifiez au moins un paramètre pour la propriété.  Vous ne pouvez pas définir une propriété par défaut qui ne prend pas au moins un argument.  
  
     [!CODE [VbVbcnProcedures#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#17)]  
  
### Pour appeler une propriété par défaut  
  
1.  Déclarez une variable de la classe conteneur ou du type structure.  
  
     [!CODE [VbVbcnProcedures#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#16)]  
  
2.  Utilisez le nom de variable seul dans une expression où vous incluriez normalement le nom de propriété.  
  
     [!CODE [VbVbcnProcedures#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#21)]  
  
3.  Faites suivre le nom de variable d'une liste d'arguments entre parenthèses.  Une propriété par défaut doit prendre au moins un argument.  
  
     [!CODE [VbVbcnProcedures#20](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#20)]  
  
4.  Pour récupérer la valeur de propriété par défaut, utilisez le nom de variable, avec une liste d'arguments, dans une expression ou à la suite du signe égal \(`=`\) dans une instruction d'assignation.  
  
     [!CODE [VbVbcnProcedures#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#15)]  
  
5.  Pour définir la valeur de propriété par défaut, utilisez le nom de variable, avec une liste d'arguments, à gauche d'une instruction d'assignation.  
  
     [!CODE [VbVbcnProcedures#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#14)]  
  
6.  Vous pouvez toujours spécifier le nom de propriété par défaut avec le nom de variable, comme vous le feriez pour accéder à une autre propriété.  
  
     [!CODE [VbVbcnProcedures#19](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#19)]  
  
## Exemple  
 L'exemple suivant déclare une propriété par défaut dans une classe.  
  
 [!CODE [VbVbcnProcedures#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#12)]  
  
## Exemple  
 L'exemple suivant montre comment appeler la propriété par défaut `myProperty` sur la classe `class1`.  Les trois instructions d'assignation stockent des valeurs dans `myProperty`, et l'appel <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> lit les valeurs.  
  
 [!CODE [VbVbcnProcedures#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#13)]  
  
 La propriété <xref:Microsoft.VisualBasic.Collection.Item%2A> de diverses classes de collection représente l'utilisation la plus courante d'une propriété par défaut.  
  
## Programmation fiable  
 Les propriétés par défaut peuvent entraîner une légère réduction des caractères de code source, mais elles peuvent rendre votre code plus difficile à lire.  Si le code appelant ne connaît pas votre classe ou votre structure, lorsqu'il fait référence au nom de la classe ou de la structure, il ne peut pas déterminer avec certitude si cette référence accède à la classe ou à la structure elle\-même ou à une propriété par défaut.  Cela peut engendrer des erreurs du compilateur ou des erreurs de logique d'exécution subtiles.  
  
 Vous pouvez légèrement réduire la probabilité que se produisent des erreurs de propriété par défaut en utilisant toujours l'[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) pour affecter la valeur `On` au contrôle de type de compilateur.  
  
 Si vous envisagez d'utiliser une classe ou une structure prédéfinie dans votre code, vous devez déterminer si elle a une propriété par défaut, et, le cas échéant, indiquer son nom.  
  
 À cause de ces inconvénients, vous devez envisager de ne pas définir de propriétés par défaut.  Afin de garantir la lisibilité du code, vous devez également envisager de toujours faire référence explicitement à toutes les propriétés, y compris aux propriétés par défaut.  
  
## Voir aussi  
 [Procédures de propriété](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Default](../../../../visual-basic/language-reference/modifiers/default.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)