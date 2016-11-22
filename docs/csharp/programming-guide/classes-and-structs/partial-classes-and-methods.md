---
title: "Classes et m&#233;thodes partielles (Guide de programmation&#160;C#) | Microsoft Docs"
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
  - "langage C#, classes et méthodes partielles"
  - "classes partielles (C#)"
  - "méthodes partielles (C#)"
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
caps.latest.revision: 35
caps.handback.revision: 35
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Classes et m&#233;thodes partielles (Guide de programmation&#160;C#)
Il est possible de fractionner la définition d'une [classe](../../../csharp/language-reference/keywords/class.md) ou d'un [struct](../../../csharp/language-reference/keywords/struct.md), ou d'une [interface](../../../csharp/language-reference/keywords/interface.md) ou d'une méthode sur deux fichiers sources ou plus.  Chaque fichier source contient une section de la définition de type ou de méthode, et toutes les parties sont combinées lorsque l'application est compilée.  
  
## Classes partielles  
 Il est souhaitable de fractionner une définition de classe dans plusieurs situations :  
  
-   Dans le cadre de projets volumineux, la répartition d'une classe en plusieurs fichiers distincts permet à plusieurs programmeurs d'y travailler simultanément.  
  
-   Lorsque vous travaillez avec une source générée automatiquement, le code peut être ajouté à la classe sans qu'il soit nécessaire de recréer le fichier source.  Visual Studio utilise cette approche lors de la création de formulaires Windows Forms, de code wrapper de service Web, etc.  Vous pouvez créer un code qui utilise ces classes sans avoir à modifier le fichier créé par Visual Studio.  
  
-   Pour fractionner une définition de classe, utilisez le modificateur de mot clé [partial](../../../csharp/language-reference/keywords/partial-type.md), comme indiqué ici :  
  
 [!CODE [csProgGuideObjects#26](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#26)]  
  
 Le mot clé `partial` indique que d'autres parties de la classe, du struct ou de l'interface peuvent être définies dans l'espace de noms.  Toutes les parties doivent utiliser le mot clé `partial`.  Toutes les parties doivent être disponibles lors de la compilation pour former le type final.  Toutes les parties doivent avoir la même accessibilité : `public`, `private`, etc.  
  
 Si une partie est déclarée comme abstract, l'ensemble du type est considéré comme abstract.  Si une partie est déclarée comme sealed, l'ensemble du type est considéré comme sealed.  Si une partie déclare un type de base, l'ensemble du type hérite de cette classe.  
  
 Toutes les parties qui spécifient une classe de base doivent se mettre d'accord, mais les parties qui omettent une classe de base héritent tout de même du type de base.  Les parties peuvent spécifier différentes interfaces de base, et le type final implémente toutes les interfaces répertoriées par toutes les déclarations partielles.  Tous les membres de classe, de struct ou d'interface déclarés dans une définition partielle sont disponibles pour toutes les autres parties.  Le type final est la combinaison de toutes les parties lors de la compilation.  
  
> [!NOTE]
>  Le modificateur `partial` n'est pas disponible sur les déclarations de délégué ou d'énumération.  
  
 L'exemple suivant montre que les types imbriqués peuvent être partiels, même si le type dans lequel ils sont imbriqués n'est pas partiel lui\-même.  
  
 [!CODE [csProgGuideObjects#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#25)]  
  
 À la compilation, les attributs de définitions de type partiel sont fusionnés.  Observez par exemple les déclarations suivantes :  
  
 [!CODE [csProgGuideObjects#23](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#23)]  
  
 Elles sont équivalentes aux déclarations suivantes :  
  
 [!CODE [csProgGuideObjects#24](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#24)]  
  
 Les éléments suivants sont fusionnés à partir de toutes les définitions de type partiel :  
  
-   Commentaires XML  
  
-   interfaces  
  
-   attributs de paramètre de type générique  
  
-   attributs de classe  
  
-   membres  
  
 Observez par exemple les déclarations suivantes :  
  
 [!CODE [csProgGuideObjects#21](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#21)]  
  
 Elles sont équivalentes aux déclarations suivantes :  
  
 [!CODE [csProgGuideObjects#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#22)]  
  
### Restrictions  
 Il y a plusieurs règles à suivre lorsque vous utilisez des définitions de classe partielles :  
  
-   Toutes les définitions de type partiel conçues comme des parties du même type doivent être modifiées avec `partial`.  Par exemple, les déclarations de classe suivantes génèrent une erreur :  
  
     [!CODE [csProgGuideObjects#20](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#20)]  
  
-   Le modificateur `partial` peut uniquement apparaître juste avant les mots clés `class`, `struct` ou `interface`.  
  
-   Les types partiels imbriqués sont autorisés dans les définitions de type partiel, comme illustré dans l'exemple suivant :  
  
     [!CODE [csProgGuideObjects#19](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#19)]  
  
-   Toutes les définitions de type partiel conçues comme des parties du même type doivent être définies dans le même assembly et dans le même module \(fichier .exe ou .dll\).  Les définitions partielles ne peuvent pas couvrir plusieurs modules.  
  
-   Le nom de la classe et les paramètres de type de générique doivent correspondre sur toutes les définitions de type partiel.  Les types génériques peuvent être partiels.  Chaque déclaration partielle doit utiliser les mêmes noms de paramètres dans le même ordre.  
  
-   Les mots clés suivants sur une définition de type partiel sont facultatifs, mais s'ils sont présents sur une définition de type partiel, ils ne peuvent pas être en conflit avec les mots clés spécifiés sur une autre définition partielle pour le même type :  
  
    -   [public](../../../csharp/language-reference/keywords/public.md)  
  
    -   [private](../../../csharp/language-reference/keywords/private.md)  
  
    -   [protected](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [internal](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [abstract](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [sealed](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   classe de base  
  
    -   Modificateur [new](../../../csharp/language-reference/keywords/new.md) \(parties imbriquées\)  
  
    -   contraintes génériques  
  
         Pour plus d'informations, consultez [Contraintes sur les paramètres de type](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## Exemple 1  
  
### Description  
 Dans l'exemple suivant, les champs et le constructeur de la classe, `CoOrds`, sont déclarés dans une définition de classe partielle, et le membre, `PrintCoOrds`, est déclaré dans une autre définition de classe partielle.  
  
### Code  
 [!CODE [csProgGuideObjects#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#17)]  
  
## Exemple 2  
  
### Description  
 L'exemple suivant montre que vous pouvez également développer des interfaces et des structs partiels.  
  
### Code  
 [!CODE [csProgGuideObjects#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#18)]  
  
## Méthodes partielles  
 Une classe partielle ou un struct partiel peut contenir une méthode partielle.  Une partie de la classe contient la signature de la méthode.  Une implémentation facultative peut être définie dans la même partie ou dans une autre partie.  Si l'implémentation n'est pas fournie, les méthodes et tous les appels à la méthode sont supprimés à la compilation.  
  
 Les méthodes partielles permettent à l'implémenteur d'une partie d'une classe de définir une méthode, semblable à un événement.  L'implémenteur de l'autre partie de la classe peut décider s'il faut implémenter la méthode ou pas.  Si la méthode n'est pas implémentée, le compilateur supprime la signature de méthode et tous les appels à la méthode.  Les appels à la méthode, y compris tous les résultats qui se produiraient depuis l'évaluation des arguments dans les appels, n'ont aucun effet au moment de l'exécution.  Par conséquent, tout code dans la classe partielle peut utiliser librement une méthode partielle, même si l'implémentation n'est pas fournie.  Aucune erreur de compilation ou d'exécution ne sera générée si la méthode est appelée mais non implémentée.  
  
 Les méthodes partielles sont particulièrement utiles comme moyen de personnaliser le code généré.  Elles permettent de réserver un nom et une signature de méthode, de sorte que le code généré peut appeler la méthode, mais le développeur peut décider s'il faut implémenter la méthode.  En grande partie comme les classes partielles, les méthodes partielles permettent au code créé par un générateur de code et au code créé par un développeur humain de fonctionner ensemble sans coûts en temps d'exécution.  
  
 Une déclaration de méthode partielle se compose de deux parties : la définition et l'implémentation.  Celles\-ci peuvent être situées dans des parties distinctes d'une classe partielle, ou dans la même partie.  En l'absence de déclaration d'implémentation, le compilateur optimise la fois la déclaration de définition et tous les appels à la méthode.  
  
```  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   Les déclarations de méthodes partielles doivent commencer par le mot clé contextuel [partial](../../../csharp/language-reference/keywords/partial-type.md) et la méthode doit retourner [void](../../../csharp/language-reference/keywords/void.md).  
  
-   Les méthodes partielles peuvent avoir les paramètres [ref](../../../csharp/language-reference/keywords/ref.md) mais pas [out](../../../csharp/language-reference/keywords/out.md).  
  
-   Les méthodes partielles sont implicitement [privées](../../../csharp/language-reference/keywords/private.md), et par conséquent, elles ne peuvent pas être [virtuelles](../../../csharp/language-reference/keywords/virtual.md).  
  
-   Les méthodes partielles ne peuvent pas être [externes](../../../csharp/language-reference/keywords/extern.md), car la présence du corps détermine si elles définissent ou implémentent.  
  
-   Les méthodes partielles avoir des modificateurs [static](../../../csharp/language-reference/keywords/static.md) et [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
-   Les méthodes partielles peuvent être génériques.  Les contraintes sont placées sur la déclaration de méthode partielle de définition et peuvent être répétées facultativement sur celle d'implémentation.  Les noms de paramètre et de paramètre de type ne doivent pas obligatoirement être identiques dans la déclaration d'implémentation et dans celle de définition.  
  
-   Vous pouvez créer un [délégué](../../../csharp/language-reference/keywords/delegate.md) pour une méthode partielle qui a été définie et implémentée, mais pas pour une méthode partielle qui a été uniquement définie.  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Classes](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Structures](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)   
 [partiel, Type](../../../csharp/language-reference/keywords/partial-type.md)