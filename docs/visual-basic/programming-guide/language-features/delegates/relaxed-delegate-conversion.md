---
title: "Relaxed Delegate Conversion (Visual Basic) | Microsoft Docs"
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
  - "relaxed delegate conversion [Visual Basic]"
  - "delegates [Visual Basic], relaxed conversion"
  - "conversions, relaxed delegate"
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Relaxed Delegate Conversion (Visual Basic)
La conversion simplifiée des délégués vous permet d'assigner des subs et des fonctions aux délégués ou aux gestionnaires même lorsque leurs signatures ne sont pas identiques. Par conséquent, la liaison aux délégués devient cohérente avec la liaison déjà autorisée pour les appels de méthodes.  
  
## Paramètres et type de retour  
 À la place d'une correspondance de signature exacte, la conversion simplifiée requiert que les conditions suivantes soient réunies lorsque `Option Strict` a la valeur `On` :  
  
-   Une conversion étendue doit avoir lieu, du type de données de chaque paramètre de délégué en type de données du paramètre correspondant de la fonction ou du `Sub` assigné.  Dans l'exemple suivant, le délégué `Del1` possède un seul paramètre, un `Integer`.  Le paramètre `m` dans les expressions lambda assignées doit présenter un type de données pour lequel il existe une conversion étendue de `Integer`, tel que `Long` ou `Double`.  
  
     [!CODE [VbVbalrRelaxedDelegates#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#1)]  
  
     [!CODE [VbVbalrRelaxedDelegates#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#2)]  
  
     Les conversions restrictives sont autorisées uniquement lorsque `Option Strict` a la valeur `Off`.  
  
     [!CODE [VbVbalrRelaxedDelegates#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#8)]  
  
-   Une conversion étendue doit avoir lieu dans le sens opposé, du type de retour de la fonction ou du `Sub` assigné en type de retour du délégué.  Dans les exemples suivants, le corps de chaque expression lambda assignée doit avoir la valeur d'un type de données qui s'étend à `Integer` étant donné que le type de retour de `del1` est `Integer`.  
  
     [!CODE [VbVbalrRelaxedDelegates#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#3)]  
  
 Si `Option Strict` a la valeur `Off`, la restriction étendue est supprimée dans les deux directions.  
  
 [!CODE [VbVbalrRelaxedDelegates#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#4)]  
  
## Omission des spécifications de paramètres  
 Les délégués simplifiés vous permettent également d'omettre complètement les spécifications de paramètres dans la méthode assignée :  
  
 [!CODE [VbVbalrRelaxedDelegates#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#5)]  
  
 [!CODE [VbVbalrRelaxedDelegates#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#6)]  
  
 Notez que vous ne pouvez pas spécifier certains paramètres et en omettre d'autres.  
  
 [!CODE [VbVbalrRelaxedDelegates#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#15)]  
  
 L'omission des paramètres est utile par exemple lors de la définition d'un gestionnaire d'événements, où plusieurs paramètres complexes sont impliqués.  Les arguments de certains gestionnaires d'événements ne sont pas utilisés.  À la place, le gestionnaire accède directement à l'état du contrôle dans lequel l'événement est enregistré et ignore les arguments.  Les délégués simplifiés vous permettent d'omettre les arguments dans les déclarations qui ne comprennent aucune ambiguïté.  Dans l'exemple suivant, la méthode `OnClick` intégralement spécifiée peut être réécrite en tant que `RelaxedOnClick`.  
  
```vb#  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## Exemples d'AddressOf  
 Les expressions lambda sont utilisées dans les exemples précédents de manière à simplifier l'affichage des relations des types.  Toutefois, les mêmes simplifications sont autorisées pour les assignations de délégués qui utilisent `AddressOf`, `Handles` ou `AddHandler`.  
  
 Dans l'exemple suivant, les fonctions `f1`, `f2`, `f3` et `f4` peuvent toutes être assignées à `Del1`.  
  
 [!CODE [VbVbalrRelaxedDelegates#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#1)]  
  
 [!CODE [VbVbalrRelaxedDelegates#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#7)]  
  
 [!CODE [VbVbalrRelaxedDelegates#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#9)]  
  
 L'exemple suivant est valide uniquement lorsque `Option Strict` a la valeur `Off`.  
  
 [!CODE [VbVbalrRelaxedDelegates#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#14)]  
  
## Déplacement des retours de la fonction  
 La conversion simplifiée des délégués vous permet d'assigner une fonction à un délégué `Sub`, en ignorant la valeur de retour de la fonction.  Toutefois, vous ne pouvez pas assigner un `Sub` à un délégué de fonction.  Dans l'exemple suivant, l'adresse de la fonction `doubler` est assignée au délégué `Sub` `Del3`.  
  
 [!CODE [VbVbalrRelaxedDelegates#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#10)]  
  
 [!CODE [VbVbalrRelaxedDelegates#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates#11)]  
  
## Voir aussi  
 [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)