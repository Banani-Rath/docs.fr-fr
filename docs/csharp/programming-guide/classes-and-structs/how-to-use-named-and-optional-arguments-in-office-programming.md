---
title: "Comment&#160;: utiliser des arguments nomm&#233;s et facultatifs dans la programmation Office (Guide de programmation&#160;C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "arguments nommés et facultatifs (C#), programmation Office"
  - "arguments nommés (C#), programmation Office"
  - "arguments facultatifs (C#), programmation Office"
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
caps.handback.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: utiliser des arguments nomm&#233;s et facultatifs dans la programmation Office (Guide de programmation&#160;C#)
Les arguments nommés et facultatifs, qui ont été introduits dans [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)], rendent la programmation en C\# plus pratique, tout en améliorant sa flexibilité et sa lisibilité. En outre, ces fonctionnalités facilitent considérablement l'accès aux interfaces COM telles que les API d'automation de Microsoft Office.  
  
 Dans l'exemple suivant, la méthode [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) comporte seize paramètres qui représentent les caractéristiques d'un tableau, telles que le nombre de colonnes et de lignes, la mise en forme, les bordures, les polices et les couleurs.  Les seize paramètres sont optionnels car, le plus souvent, vous ne souhaitez pas spécifier de valeurs particulières pour chacun d'eux.  Toutefois, sans les arguments nommés et facultatifs, une valeur ou une valeur d'espace réservé doit être fournie pour chaque paramètre.  Avec les arguments nommés et facultatifs, vous pouvez spécifier des valeurs uniquement pour les paramètres requis par votre projet.  
  
 Ces procédures nécessitent que Microsoft Office Word soit installé sur votre ordinateur.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Pour créer une application console  
  
1.  Démarrez Visual Studio.  
  
2.  Dans le menu **Fichier**, pointez sur **Nouveau**, puis cliquez sur **Projet**.  
  
3.  Dans le volet **Catégories de modèles**, développez **Visual C\#**, puis cliquez sur **Windows**.  
  
4.  Vérifiez en haut du volet **Modèles** que **.NET Framework 4** figure dans la zone **Framework cible**.  
  
5.  Dans le volet **Modèles**, cliquez sur **Application console**.  
  
6.  Tapez un nom pour votre projet dans le champ **Nom**.  
  
7.  Cliquez sur **OK**.  
  
     Le nouveau projet s'affiche dans l'**Explorateur de solutions**.  
  
### Pour ajouter une référence  
  
1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le nom du projet, puis cliquez sur **Ajouter une référence**.  La boîte de dialogue **Ajouter une référence** s'affiche.  
  
2.  Dans la page **.NET**, sélectionnez **Microsoft.Office.Interop.Word** dans la liste **Nom du composant**.  
  
3.  Cliquez sur **OK**.  
  
### Pour ajouter les directives using nécessaires  
  
1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le fichier **Program.cs**, puis cliquez sur **Afficher le code**.  
  
2.  Ajoutez les directives `using` suivantes au début du fichier de code.  
  
     [!CODE [csProgGuideNamedAndOptional#4](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#4)]  
  
### Pour afficher du texte dans un document Word  
  
1.  Dans la classe `Program` de Program.cs, ajoutez la méthode suivante pour créer une application Word et un document Word.  La méthode [Add](http://go.microsoft.com/fwlink/?LinkId=145381) comporte quatre paramètres optionnels.  Cet exemple utilise leur valeur par défaut.  Par conséquent, aucun argument n'est nécessaire dans l'instruction appelante.  
  
     [!CODE [csProgGuideNamedAndOptional#6](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#6)]  
  
2.  Ajoutez le code suivant à la fin de la méthode pour définir l'emplacement où le texte doit être affiché dans le document et le texte à afficher.  
  
     [!CODE [csProgGuideNamedAndOptional#7](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#7)]  
  
### Pour exécuter l'application  
  
1.  Ajoutez l'instruction suivante à Main.  
  
     [!CODE [csProgGuideNamedAndOptional#8](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#8)]  
  
2.  Appuyez sur CTRL\+F5 pour exécuter le projet.  Un document Word contenant le texte spécifié s'affiche.  
  
### Pour présenter le texte sous forme de tableau  
  
1.  Utilisez la méthode `ConvertToTable` pour placer le texte dans un tableau.  Cette méthode comporte seize paramètres optionnels.  IntelliSense place les paramètres optionnels entre parenthèses, comme indiqué dans l'illustration suivante.  
  
     ![Liste de paramètres pour la méthode ConvertToTable.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert\_TableParameters")  
Paramètres ConvertToTable  
  
     Les arguments nommés et optionnels vous permettent de spécifier des valeurs pour les seuls paramètres que vous souhaitez modifier.  Ajoutez le code suivant à la fin de la méthode `DisplayInWord` pour créer un tableau simple.  L'argument spécifie que les virgules de la chaîne de texte dans `range` séparent les cellules du tableau.  
  
     [!CODE [csProgGuideNamedAndOptional#9](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#9)]  
  
     Dans les versions antérieures de C\#, l'appel à `ConvertToTable` requiert un argument de référence pour chaque paramètre, comme indiqué dans le code suivant.  
  
     [!CODE [csProgGuideNamedAndOptional#14](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#14)]  
  
2.  Appuyez sur CTRL\+F5 pour exécuter le projet.  
  
### Pour tester d'autres paramètres  
  
1.  Pour modifier le tableau afin qu'il comporte une colonne et trois lignes, remplacez la dernière ligne de `DisplayInWord` par l'instruction suivante, puis appuyez sur CTRL\+F5.  
  
     [!CODE [csProgGuideNamedAndOptional#10](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#10)]  
  
2.  Pour spécifier un format prédéfini pour le tableau, remplacez la dernière ligne de `DisplayInWord` par l'instruction suivante, puis appuyez sur CTRL\+F5.  Le format peut correspondre à n'importe quelle constante [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382).  
  
     [!CODE [csProgGuideNamedAndOptional#11](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#11)]  
  
## Exemple  
 Le code suivant inclut l'exemple complet.  
  
 [!CODE [csProgGuideNamedAndOptional#12](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#12)]  
  
## Voir aussi  
 [Arguments nommés et facultatifs](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)