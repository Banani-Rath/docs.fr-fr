---
title: "Visual Basic Coding Conventions | Microsoft Docs"
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
  - "coding conventions, Visual Basic"
  - "examples [Visual Basic], coding conventions"
  - "Visual Basic code, conventions"
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
caps.handback.revision: 48
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Visual Basic Coding Conventions
Microsoft développe les exemples et la documentation qui suivent les instructions de cette rubrique.  Si vous suivez les mêmes conventions de codage, vous pouvez bénéficier des avantages suivants :  
  
-   Votre code aura un aspect homogène afin que les lecteurs puissent mieux se concentrer sur le contenu et non pas sur la disposition.  
  
-   Les lecteurs comprennent votre code plus rapidement, parce qu'ils peuvent faire des hypothèses fondées sur leur expérience précédente.  
  
-   Vous pouvez copier, modifier et gérer le code plus facilement.  
  
-   Vous aidez à garantir que votre code illustre les « meilleures pratiques » pour Visual Basic.  
  
## Conventions d'affectation de noms  
  
-   Pour plus d'informations sur les instructions d'attribution d'un nom, consultez la rubrique [Indications concernant l'attribution d'un nom](../Topic/Naming%20Guidelines.md).  
  
-   N'utilisez pas "My" ou "my" dans un nom de variable,  Cette pratique peut créer une confusion avec les objets `My`.  
  
-   Il n'est pas nécessaire de modifier les noms des objets dans le code généré automatiquement pour les rendre conformes aux indications.  
  
## Conventions de disposition  
  
-   Insérez les tabulations en tant qu'espaces et la mise en retrait intelligente d'utilisation avec des retraits de quatre espaces.  
  
-   Utilisez **Mise en forme automatique avec tabulation du code** pour mettre en forme votre code dans l'éditeur de code.  Pour plus d'informations, consultez [Options, Éditeur de texte, De base \(Visual Basic\)](/visual-studio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Mettez une seule instruction par ligne.  N'utilisez pas le caractère de séparation de ligne Visual Basic \(:\).  
  
-   Préférez au caractère de continuation de ligne explicite « \_ » la continuation de ligne implicite partout où le langage le permet.  
  
-   Mettez une seule déclaration par ligne.  
  
-   Si la **mise en forme automatique du code \(reformatage\)** ne met pas les lignes de continuation en forme automatiquement, mettez manuellement les lignes de continuation en retrait d'un taquet de tabulation.  Toutefois, alignez toujours les éléments à gauche dans une liste.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Laissez au moins une ligne vide entre les définitions de méthode et de propriété.  
  
## Conventions de commentaires  
  
-   Placez les commentaires sur une ligne séparée, et non à la fin d'une ligne de code.  
  
-   Démarrez le texte de commentaire par une majuscule et terminez le texte de commentaire par un point.  
  
-   Insérez un espace entre le délimiteur de commentaire \('\) et le texte de commentaire.  
  
     [!CODE [VbVbalrGuidelines#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#2)]  
  
-   N'entourez pas les commentaires avec des blocs d'astérisques mis en forme.  
  
## Structure du programme  
  
-   Avec la méthode `Main`, utilisez la construction par défaut pour les nouvelles applications console et utilisez `My` pour les arguments de ligne de commande.  
  
     [!CODE [VbVbalrGuidelines#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#3)]  
  
## Indications concernant le langage  
  
### Type de données String  
  
-   Pour concaténer des chaînes, utilisez une perluète \(&\).  
  
     [!CODE [VbVbalrGuidelines#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#4)]  
  
-   Pour ajouter des chaînes dans des boucles, utilisez l'objet <xref:System.Text.StringBuilder>.  
  
     [!CODE [VbVbalrGuidelines#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#5)]  
  
### Délégués souples dans les gestionnaires d'événements  
 N'appliquez pas explicitement les arguments \(Objet et EventArgs\) aux gestionnaires d'événements.  Si vous n'utilisez pas les arguments d'événement passés à un événement \(par exemple, expéditeur pour Objet, e pour EventArgs\), utilisez les délégués simplifiés et omettez les arguments d'événement dans votre code :  
  
 [!CODE [VbVbalrGuidelines#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#7)]  
  
### Type de données non signé  
  
-   Utilisez `Integer` au lieu des types non signés, sauf s'ils sont nécessaires.  
  
### Tableaux  
  
-   Utilisez la syntaxe concise lorsque vous initialisez des tableaux sur la ligne de déclaration.  Par exemple, utilisez la syntaxe suivante.  
  
     [!CODE [VbVbalrGuidelines#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#8)]  
  
     N'utilisez pas la syntaxe suivante.  
  
     [!CODE [VbVbalrGuidelines#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#9)]  
  
-   Mettez l'indicateur de tableau sur le type, pas sur la variable.  Par exemple, utilisez la syntaxe suivante :  
  
     [!CODE [VbVbalrGuidelines#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#11)]  
  
     N'utilisez pas la syntaxe suivante :  
  
     [!CODE [VbVbalrGuidelines#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#10)]  
  
-   Utilisez la syntaxe { } lorsque vous déclarez et initialisez des tableaux comportant des types de données de base.  Par exemple, utilisez la syntaxe suivante :  
  
     [!CODE [VbVbalrGuidelines#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#12)]  
  
     N'utilisez pas la syntaxe suivante :  
  
     [!CODE [VbVbalrGuidelines#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#13)]  
  
### Utilisation du mot clé "With"  
 Lorsque vous créez une série d'appels à un objet, envisagez l'utilisation du mot clé `With` :  
  
 [!CODE [VbVbalrGuidelines#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#15)]  
  
### Utilisez les instructions Try...Catch et Using pour la gestion des exceptions  
 N'utilisez pas `On Error Goto`.  
  
### Utilisation du mot clé IsNot  
 Utilisez le mot clé `IsNot` au lieu de `Not...Is Nothing`.  
  
### Mot clé New  
  
-   Utilisez l'instanciation courte.  Par exemple, utilisez la syntaxe suivante :  
  
     [!CODE [VbVbalrGuidelines#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#21)]  
  
     La ligne précédente est équivalente à ce qui suit :  
  
     [!CODE [VbVbalrGuidelines#22](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#22)]  
  
-   Utilisez des initialiseurs d'objets pour les nouveaux objets au lieu du constructeur sans paramètre :  
  
     [!CODE [VbVbalrGuidelines#23](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#23)]  
  
### Gestion des événements  
  
-   Utilisez `Handles` plutôt que `AddHandler` :  
  
     [!CODE [VbVbalrGuidelines#24](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#24)]  
  
-   Utilisez `AddressOf` et n'instanciez pas le délégué explicitement :  
  
     [!CODE [VbVbalrGuidelines#25](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#25)]  
  
-   Lorsque vous définissez un événement, utilisez la syntaxe concise et laissez le compilateur définir le délégué :  
  
     [!CODE [VbVbalrGuidelines#26](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#26)]  
  
-   Ne vérifiez pas si un événement est `Nothing` \(null\) avant d'appeler la méthode `RaiseEvent`.  `RaiseEvent` recherche la valeur `Nothing` avant de déclencher l'événement.  
  
### Utilisation des membres partagés  
 Appelez des membres `Shared` à l'aide du nom de la classe et non à partir d'une variable d'instance.  
  
### Utilisation des littéraux XML  
 Les littéraux XML simplifient les tâches les plus courantes que vous rencontrez lorsque vous utilisez XML \(par exemple, chargement, interrogation et transformation\).  Lorsque vous utilisez XML pour un développement, suivez ces consignes :  
  
-   Utilisez des littéraux XML pour créer des fragments et des documents XML au lieu d'appeler directement des API XML.  
  
-   Importez des espaces de noms XML au niveau du fichier ou du projet pour tirer parti des optimisations des performances des littéraux XML.  
  
-   Utilisez les propriétés d'axe XML pour accéder aux éléments et aux attributs dans un document XML.  
  
-   Utilisez des expressions incorporées pour inclure des valeurs et créer du code XML à partir de valeurs existantes au lieu d'utiliser des appels d'API tels que la méthode `Add` :  
  
     [!CODE [VbVbalrGuidelines#27](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#27)]  
  
### Requêtes LINQ  
  
-   Utilisez des noms explicites pour les variables de requête :  
  
     [!CODE [VbVbalrGuidelines#28](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#28)]  
  
-   Fournit des noms pour les éléments d'une requête qui permettent de s'assurer que les noms de propriété des types anonymes sont correctement capitalisés à l'aide de la casse Pascal :  
  
     [!CODE [VbVbalrGuidelines#29](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#29)]  
  
-   Renommez les propriétés lorsque les noms de propriété dans le résultat sont ambigus.  Par exemple, si votre requête retourne un nom de client et un ID de commande, renommez\-les au lieu de les laisser au format `Name` et `ID` dans le résultat :  
  
     [!CODE [VbVbalrGuidelines#30](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#30)]  
  
-   Utilisez l'inférence de type dans la déclaration des variables de requête et de portée :  
  
     [!CODE [VbVbalrGuidelines#31](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#31)]  
  
-   Alignez les clauses de requête sous l'instruction `From` :  
  
     [!CODE [VbVbalrGuidelines#32](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#32)]  
  
-   Utilisez les clauses `Where` avant les autres clauses de requête afin de vous assurer que les clauses de requête ultérieures s'appliqueront au groupe de données réduit et filtré :  
  
     [!CODE [VbVbalrGuidelines#33](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#33)]  
  
-   Utilisez la clause `Join` pour définir explicitement une jointure au lieu de la définir implicitement à l'aide de la clause `Where`:  
  
     [!CODE [VbVbalrGuidelines#34](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#34)]  
  
## Voir aussi  
 [Instructions de codage sécurisé](../Topic/Secure%20Coding%20Guidelines.md)