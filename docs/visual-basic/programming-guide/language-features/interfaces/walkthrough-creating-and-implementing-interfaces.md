---
title: "Walkthrough: Creating and Implementing Interfaces (Visual Basic) | Microsoft Docs"
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
  - "interfaces, walkthroughs"
  - "interfaces, testing"
  - "interface implementation, walkthrough"
  - "interfaces, creating"
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Walkthrough: Creating and Implementing Interfaces (Visual Basic)
Les interfaces décrivent les caractéristiques des propriétés, des méthodes et des événements, mais laissent les détails d'implémentation aux structures ou aux classes.  
  
 Cette procédure pas à pas explique comment déclarer et implémenter une interface.  
  
> [!NOTE]
>  Cette procédure pas \- à \- pas ne fournit pas d'informations sur la création d'une interface utilisateur.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Pour définir une interface  
  
1.  Ouvrez un nouveau projet d'application Windows [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
2.  Ajoutez un nouveau module au projet en cliquant sur **Ajouter un module** dans le menu **Projet**.  
  
3.  Nommez le nouveau module `Module1.vb` et cliquez sur **Ajouter**.  Le code du nouveau module s'affiche.  
  
4.  Définissez une interface nommée `TestInterface` dans `Module1` en tapant `Interface TestInterface` entre les instructions `Module` et `End Module`, puis en appuyant sur ENTRÉE.  L'**éditeur de code** met en retrait le mot clé `Interface` et ajoute une instruction `End Interface` pour constituer un bloc de code.  
  
5.  Définissez une propriété, une méthode et un événement pour l'interface en insérant le code suivant entre les instructions `Interface` et `End Interface` :  
  
     [!CODE [VbVbalrOOP#98](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#98)]  
  
## Implémentation  
 Vous remarquez peut\-être que la syntaxe utilisée pour déclarer des membres d'interface est différente de celle utilisée pour déclarer des membres de classe.  Cette différence reflète le fait que les interfaces ne peuvent pas contenir le code d'implémentation.  
  
#### Pour implémenter l'interface  
  
1.  Ajoutez une classe nommée `ImplementationClass` en ajoutant l'instruction ci\-après à `Module1` entre les instructions `End Interface` et `End Module`, puis appuyez sur ENTRÉE :  
  
     [!CODE [VbVbalrOOP#99](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#99)]  
  
     Si vous travaillez dans l'environnement de développement intégré, l'**éditeur de code** fournit une instruction `End Class` concordante lorsque vous appuyez sur ENTRÉE.  
  
2.  Ajoutez l'instruction `Implements` suivante à `ImplementationClass`, qui nomme l'interface que la classe implémente :  
  
     [!CODE [VbVbalrOOP#100](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#100)]  
  
     Lorsqu'elle est séparée d'autres éléments en haut d'une classe ou d'une structure, l'instruction `Implements` indique que la classe ou structure implémente une interface.  
  
     Si vous travaillez dans l'environnement de développement intégré, l'**éditeur de code** implémente les membres de classe requis par `TestInterface` lorsque vous appuyez sur ENTRÉE et vous pouvez ignorer l'étape suivante.  
  
3.  Si vous ne travaillez pas dans l'environnement de développement intégré, vous devez implémenter tous les membres de l'interface `MyInterface`.  Ajoutez le code suivant à `ImplementationClass` pour implémenter `Event1`, `Method1` et `Prop1` :  
  
     [!CODE [VbVbalrOOP#101](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#101)]  
  
     L'instruction `Implements` nomme l'interface et le membre d'interface en cours d'implémentation.  
  
4.  Complétez la définition de `Prop1` en ajoutant un champ privé à la classe qui a stocké la valeur de propriété :  
  
     [!CODE [VbVbalrOOP#102](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#102)]  
  
     Retournez la valeur du `pval` de l'accesseur get de propriété.  
  
     [!CODE [VbVbalrOOP#103](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#103)]  
  
     Définissez la valeur de `pval` dans l'accesseur set de propriété.  
  
     [!CODE [VbVbalrOOP#104](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#104)]  
  
5.  Complétez la définition de `Method1` en ajoutant le code suivant.  
  
     [!CODE [VbVbalrOOP#105](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#105)]  
  
#### Pour tester l'implémentation de l'interface  
  
1.  Cliquez avec le bouton droit sur le formulaire de démarrage de votre projet dans l'**Explorateur de solutions** et cliquez sur **Afficher le code**.  L'éditeur affiche la classe de votre formulaire de départ.  Par défaut, le formulaire de démarrage s'appelle `Form1`.  
  
2.  Ajoutez le champ suivant `testInstance` à la classe `Form1` :  
  
     [!CODE [VbVbalrOOP#120](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#120)]  
  
     En déclarant `testInstance` comme `WithEvents`, la classe `Form1` peut gérer ses événements.  
  
3.  Ajoutez le gestionnaire d'événements suivant à la classe `Form1` pour gérer les événements déclenchés par `testInstance` :  
  
     [!CODE [VbVbalrOOP#106](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#106)]  
  
4.  Ajoutez une sous\-routine nommée `Test` à la classe `Form1` pour tester la classe d'implémentation :  
  
     [!CODE [VbVbalrOOP#107](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#107)]  
  
     La procédure `Test` crée une instance de la classe qui implémente `MyInterface`, assigne cette instance au champ `testInstance`, définit une propriété et exécute une méthode par le biais de l'interface.  
  
5.  Ajoutez du code pour appeler la procédure `Test` à partir de la procédure `Form1 Load` de votre formulaire de départ :  
  
     [!CODE [VbVbalrOOP#108](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#108)]  
  
6.  Exécutez la procédure `Test` en appuyant sur F5.  Le message "Prop1 was set to 9" s'affiche.  Après avoir cliqué sur OK, le message "The X parameter for Method1 is 5" s'affiche.  Cliquez sur OK et le message "The event handler caught the event" s'affiche.  
  
## Voir aussi  
 [Implements Statement](../../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Interface Statement](../../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md)