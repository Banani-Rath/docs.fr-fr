---
title: "Conventions de codage C# (Guide de programmation C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
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
  - "langage C#, conventions de codage"
  - "conventions de codage, C#"
  - "Visual C#, conventions de codage"
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
caps.handback.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Conventions de codage C# (Guide de programmation C#)
La [spécification du langage C\#](http://go.microsoft.com/fwlink/?LinkId=199552) ne définit pas une norme de codage.  Toutefois, les instructions de cette rubrique sont utilisées par Microsoft pour développer les exemples et la documentation.  
  
 Les conventions de codage répondent aux objectifs suivants :  
  
-   Elles confèrent une apparence cohérente au code, afin que les lecteurs puissent se concentrer sur le contenu, pas sur la disposition.  
  
-   Elles permettent aux lecteurs de comprendre le code plus rapidement en formulant des hypothèses selon leur expérience antérieure.  
  
-   Elles facilitent la copie, la modification et la gestion du code.  
  
-   Elles illustrent les meilleures pratiques en C\#.  
  
## Conventions d'affectation de noms  
  
-   Dans les exemples courts qui ne comprennent pas de [directives](../../../csharp/language-reference/keywords/using-directive.md), utilisez les qualifications d'espace de noms.  Si vous savez qu'un espace de noms est importé par défaut dans un projet, vous n'êtes pas obligé de qualifier entièrement les noms à partir de cet espace de noms.  Les noms qualifiés peuvent être interrompus après un point \(.\) s'ils sont trop longs pour contenir sur une ligne unique, comme indiqué dans l'exemple suivant.  
  
     [!CODE [csProgGuideCodingConventions#1](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#1)]  
  
-   Vous n'avez pas à modifier les noms des objets qui ont été créés à l'aide des outils du concepteur Visual Studio pour les rendre conformes aux autres directives.  
  
## Conventions de disposition  
 Une bonne disposition utilise la mise en forme pour souligner la structure de votre code et en faciliter la lecture.  Les exemples Microsoft et autres se conforment aux conventions suivantes :  
  
-   Utilisez les paramètres par défaut de l'éditeur de code \(retrait intelligent, retrait de quatre caractères, tabulations enregistrées en tant qu'espaces\).  Pour plus d'informations, consultez [Options, Éditeur de texte, C\#, Mise en forme](/visual-studio/ide/reference/options-text-editor-csharp-formatting).  
  
-   Écrivez une seule instruction par ligne.  
  
-   Écrivez une seule déclaration par ligne.  
  
-   Si les lignes de continuation ne sont pas mises en retrait automatiquement, indentez\-les à l'aide d'un taquet de tabulation \(quatre espaces\).  
  
-   Ajoutez au moins une ligne blanche entre les définitions des méthodes et les définitions des propriétés.  
  
-   Utilisez des parenthèses pour rendre apparentes les clauses d'une expression, comme illustré dans le code suivant.  
  
     [!CODE [csProgGuideCodingConventions#2](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#2)]  
  
## Conventions de commentaires  
  
-   Placez le commentaire sur une ligne séparée, pas à la fin d'une ligne de code.  
  
-   Commencez le commentaire par une lettre majuscule.  
  
-   Terminez le texte de commentaire par un point.  
  
-   Insérez un espace entre le délimiteur de commentaire \(\/\/\) et le texte du commentaire, comme illustré dans l'exemple suivant.  
  
     [!CODE [csProgGuideCodingConventions#3](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#3)]  
  
-   Ne créez pas de blocs d'astérisques mis en forme autour des commentaires.  
  
## Directives du langage  
 Les sections suivantes décrivent les pratiques que l'équipe C\# suit pour préparer les exemples de code et autres.  
  
### String, type de données  
  
-   Utilisez l'opérateur `+` pour concaténer les chaînes courtes, comme illustré dans le code suivant.  
  
     [!CODE [csProgGuideCodingConventions#6](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#6)]  
  
-   Pour ajouter des chaînes dans des boucles, en particulier lorsque vous travaillez avec une quantité de texte importante, utilisez un objet <xref:System.Text.StringBuilder>.  
  
     [!CODE [csProgGuideCodingConventions#7](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#7)]  
  
### Variables locales implicitement typées  
  
-   Utilisez le [typage implicite](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) pour les variables locales lorsque le type de la variable est évident à droite de l'affectation ou lorsque le type précis n'importe pas.  
  
     [!CODE [csProgGuideCodingConventions#8](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#8)]  
  
-   N'utilisez pas [var](../../../csharp/language-reference/keywords/var.md) lorsque le type n'est pas apparent à droite de l'affectation.  
  
     [!CODE [csProgGuideCodingConventions#9](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#9)]  
  
-   Ne vous basez pas sur le nom de la variable pour spécifier son type.  Il peut ne pas être correct.  
  
     [!CODE [csProgGuideCodingConventions#10](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#10)]  
  
-   Évitez d'utiliser `var` à la place de [dynamic](../../../csharp/language-reference/keywords/dynamic.md).  
  
-   Utilisez le typage implicite pour déterminer le type de la variable de boucle dans les boucles [for](../../../csharp/language-reference/keywords/for.md) et [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
     L'exemple suivant utilise un typage implicite dans une instruction `for`.  
  
     [!CODE [csProgGuideCodingConventions#11](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#11)]  
  
     L'exemple suivant utilise un typage implicite dans une instruction `foreach`.  
  
     [!CODE [csProgGuideCodingConventions#12](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#12)]  
  
### Type de données non signé  
  
-   En règle générale, utilisez `int` plutôt que les types non signés.  L'utilisation de `int` est commun en C\# et il est plus facile d'interagir avec d'autres bibliothèques lorsque vous utilisez `int`.  
  
### Tableaux  
  
-   Utilisez la syntaxe concise lorsque vous initialisez des tableaux sur la ligne de déclaration.  
  
     [!CODE [csProgGuideCodingConventions#13](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#13)]  
  
### Délégués  
  
-   Utilisez la syntaxe concise pour créer des instances d'un type délégué.  
  
     [!CODE [csProgGuideCodingConventions#14](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#14)]  
  
     [!CODE [csProgGuideCodingConventions#15](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#15)]  
  
### Instructions try\-catch et using dans la gestion des exceptions  
  
-   Utilisez une instruction [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) pour la plus grande part de la gestion des exceptions.  
  
     [!CODE [csProgGuideCodingConventions#16](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#16)]  
  
-   Simplifiez votre code à l'aide de l'instruction C\# [using](../../../csharp/language-reference/keywords/using-statement.md).  Si vous avez une instruction [try\-finally](../../../csharp/language-reference/keywords/try-finally.md) dans laquelle le seul code du bloc `finally` est un appel à la méthode <xref:System.IDisposable.Dispose%2A>, utilisez à la place une instruction `using`.  
  
     [!CODE [csProgGuideCodingConventions#17](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#17)]  
  
### Opérateurs && et &#124;&#124;  
  
-   Pour éviter les exceptions et accroître les performances en ignorant les comparaisons superflues, utilisez [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) au lieu de [&](../../../csharp/language-reference/operators/and-operator.md) et [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) au lieu de                                       [&#124;](../../../csharp/language-reference/operators/or-operator.md) lorsque vous effectuez des comparaisons, comme illustré dans l'exemple suivant.  
  
     [!CODE [csProgGuideCodingConventions#18](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#18)]  
  
### New, opérateur  
  
-   Utilisez la forme concise de l'instanciation d'objets, avec typage implicite, comme indiqué dans la déclaration suivante.  
  
     [!CODE [csProgGuideCodingConventions#19](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#19)]  
  
     La ligne précédente est équivalente à la déclaration suivante.  
  
     [!CODE [csProgGuideCodingConventions#20](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#20)]  
  
-   Utilisez les initialiseurs d'objets pour simplifier la création d'objet.  
  
     [!CODE [csProgGuideCodingConventions#21](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#21)]  
  
### Gestion des événements  
  
-   Si vous définissez un gestionnaire d'événements que vous n'avez pas besoin de supprimer ultérieurement, utilisez une expression lambda.  
  
     [!CODE [csProgGuideCodingConventions#22](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#22)]  
  
     [!CODE [csProgGuideCodingConventions#23](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#23)]  
  
### Membres static  
  
-   Appelez les membres [static](../../../csharp/language-reference/keywords/static.md) en utilisant le nom de classe : *ClassName.StaticMember*.  Cette pratique rend le code plus lisible en clarifiant l'accès aux membres static.  Ne qualifiez pas un membre static défini dans une classe de base avec le nom d'une classe dérivée.  Lorsque ce code est compilé, la lisibilité du code est trompeuse et le code peut s'interrompre à l'avenir si vous ajoutez à la classe dérivée un membre static de même nom.  
  
### Requêtes LINQ  
  
-   Utilisez des noms explicites pour les variables de requête.  L'exemple suivant utilise `seattleCustomers` pour les clients qui se trouvent à Seattle.  
  
     [!CODE [csProgGuideCodingConventions#25](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#25)]  
  
-   Utilisez des alias pour vous assurer que les noms de propriétés des types anonymes sont correctement écrits en majuscules à l'aide de la casse Pascal.  
  
     [!CODE [csProgGuideCodingConventions#26](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#26)]  
  
-   Renommez les propriétés lorsque les noms de propriétés dans le résultat sont ambigus.  Par exemple, si votre requête retourne un nom de client et un ID de distributeur, au lieu de les laisser sous la forme `Name` et `ID` dans le résultat, renommez\-les pour montrer clairement que `Name` est le nom d'un client et `ID` l'ID d'un distributeur.  
  
     [!CODE [csProgGuideCodingConventions#27](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#27)]  
  
-   Utilisez le typage implicite dans la déclaration des variables de requête et des variables de portée.  
  
     [!CODE [csProgGuideCodingConventions#25](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#25)]  
  
-   Alignez les clauses de requête sous la clause [from](../../../csharp/language-reference/keywords/from-clause.md), comme illustré dans les exemples précédents.  
  
-   Utilisez les clauses [where](../../../csharp/language-reference/keywords/where-clause.md) avant les autres clauses de requête pour garantir que les clauses de requête ultérieures opèrent sur l'ensemble de données réduit et filtré.  
  
     [!CODE [csProgGuideCodingConventions#29](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#29)]  
  
-   Utilisez plusieurs clauses `from` au lieu d'une clause [join](../../../csharp/language-reference/keywords/join-clause.md) pour accéder aux collections internes.  Par exemple, une collection d'objets `Student` peut contenir chacune une collection de scores de test.  Lorsque la requête suivante est exécutée, elle retourne chaque score supérieur à 90, avec le nom de l'étudiant correspondant.  
  
     [!CODE [csProgGuideCodingConventions#30](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#30)]  
  
## Sécurité  
 Suivez les instructions indiquées dans [Instructions de codage sécurisé](../Topic/Secure%20Coding%20Guidelines.md).  
  
## Voir aussi  
 [Visual Basic Coding Conventions](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)   
 [Instructions de codage sécurisé](../Topic/Secure%20Coding%20Guidelines.md)