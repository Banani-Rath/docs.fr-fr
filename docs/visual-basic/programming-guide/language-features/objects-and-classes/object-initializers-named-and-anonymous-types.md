---
title: "Object Initializers: Named and Anonymous Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ObjectInitializer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "object initializers [Visual Basic]"
  - "anonymous types [Visual Basic], object initializers"
  - "initializing properties [Visual Basic]"
  - "initializers [Visual Basic]"
  - "named types [Visual Basic]"
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Object Initializers: Named and Anonymous Types (Visual Basic)
Les initialiseurs d'objets vous permettent de spécifier des propriétés pour un objet complexe, en utilisant une expression unique.  Ils peuvent être utilisés pour créer des instances de types nommés et de types anonymes.  
  
## Déclarations  
 Les déclarations d'instances de types nommés et anonymes peuvent sembler presque identiques, mais leurs effets ne sont pas les mêmes.  Chaque catégorie a ses propres capacités et restrictions.  L'exemple suivant montre une manière pratique de déclarer et d'initialiser une instance de classe nommée, `Customer`, en utilisant une liste d'initialiseurs d'objets.  Remarquez que le nom de la classe est spécifié après le mot clé `New`.  
  
 [!CODE [VbVbalrObjectInit#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#1)]  
  
 Un type anonyme n'a aucun nom utilisable.  Par conséquent, une instanciation de type anonyme ne peut pas inclure de nom de classe.  
  
 [!CODE [VbVbalrObjectInit#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#2)]  
  
 Les spécifications et résultats des deux déclarations ne sont pas les mêmes.  Pour `namedCust`, une classe `Customer` ayant une propriété `Name` doit déjà exister, et la déclaration crée une instance de cette classe.  Pour `anonymousCust`, le compilateur définit une nouvelle classe possédant une propriété, une chaîne appelée `Name`, et crée une nouvelle instance de cette classe.  
  
## Types nommés  
 Les initialiseurs d'objets sont un moyen simple d'appeler le constructeur d'un type et de définir ensuite les valeurs de tout ou partie des propriétés, en une instruction unique.  Le compilateur appelle le constructeur approprié pour l'instruction : le constructeur par défaut, si aucun argument n'est présenté, ou un constructeur paramétrable, si un ou plusieurs arguments sont envoyés.  Après cela, les propriétés spécifiées sont initialisées dans l'ordre dans lequel elles sont présentées dans la liste d'initialiseurs.  
  
 Chaque initialisation de la liste d'initialiseurs se compose de l'assignation d'une valeur initiale à un membre de la classe.  Les noms et types de données des membres sont déterminés quand la classe est définie.  Dans les exemples qui suivent, la classe `Customer` doit exister et doit comporter des membres nommés `Name` et `City`, capables d'accepter des valeurs de chaînes.  
  
 [!CODE [VbVbalrObjectInit#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#3)]  
  
 Vous pouvez également obtenir le même résultat en utilisant le code suivant :  
  
 [!CODE [VbVbalrObjectInit#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#4)]  
  
 Chacune de ces déclarations équivaut à l'exemple suivant, qui crée un objet `Customer` en utilisant le constructeur par défaut, puis spécifie des valeurs initiales pour les propriétés `Name` et `City`, en utilisant une instruction `With`.  
  
 [!CODE [VbVbalrObjectInit#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#5)]  
  
 Si la classe `Customer` contient un constructeur paramétrable qui vous permet d'envoyer une valeur pour `Name`, par exemple, vous pouvez également déclarer et initialiser un objet `Customer` par les méthodes suivantes :  
  
 [!CODE [VbVbalrObjectInit#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#6)]  
  
 Vous n'avez pas à initialiser toutes les propriétés, comme le montre code suivant.  
  
 [!CODE [VbVbalrObjectInit#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#7)]  
  
 Toutefois, la liste d'initialisation ne peut pas être vide.  Les propriétés non initialisées conservent leurs valeurs par défaut.  
  
### Inférence de type avec les types nommés  
 Vous pouvez raccourcir le code pour la déclaration de `cust1` en combinant des initialiseurs d'objets et l'inférence de type local.  Cela vous permet d'omettre la clause `As` dans la déclaration de variable.  Le type de données de la variable est déduit du type de l'objet créé par l'assignation.  Dans l'exemple suivant, le type de `cust6` est `Customer`.  
  
 [!CODE [VbVbalrObjectInit#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#8)]  
  
### Remarques sur les types nommés  
  
-   Un membre de classe ne peut pas être initialisé plus d'une fois dans la liste d'initialiseurs d'objets.  La déclaration de `cust7` provoque une erreur.  
  
     [!CODE [VbVbalrObjectInit#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#9)]  
  
-   Un membre peut être utilisé pour s'initialiser lui\-même ou initialiser un autre champ.  Si un membre fait l'objet d'un accès avant qu'il n'ait été initialisé, comme dans la déclaration suivante pour `cust8`, la valeur par défaut est utilisée.  Souvenez\-vous que lorsqu'une déclaration qui utilise un initialiseur d'objet est traitée, la première chose qui se passe est que le constructeur approprié est appelé.  Après cela, les champs individuels de la liste d'initialiseurs sont initialisés.  Dans les exemples qui suivent, la valeur par défaut de `Name` est assignée à `cust8`, et une valeur initialisée est assignée en `cust9`.  
  
     [!CODE [VbVbalrObjectInit#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#10)]  
  
     L'exemple suivant utilise le constructeur paramétrable de `cust3` et `cust4` pour déclarer et initialiser `cust10` et `cust11`.  
  
     [!CODE [VbVbalrObjectInit#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#11)]  
  
-   Les initialiseurs d'objets peuvent être imbriqués.  Dans l'exemple qui suit, `AddressClass` est une classe qui a deux propriétés, `City` et `State`, et la classe `Customer` a une propriété `Address` qui est une instance d' `AddressClass`.  
  
     [!CODE [VbVbalrObjectInit#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#12)]  
  
-   La liste d'initialisation ne peut pas être vide.  
  
-   L'instance initialisée ne peut pas être de type Objet.  
  
-   Les membres d'une classe en cours d'initialisation ne peuvent pas être des membres partagés, des membres en lecture seule, des constantes ni des appels de méthode.  
  
-   Les membres de classes en cours d'initialisation ne peuvent être ni indexés ni qualifiés.  Les exemples suivants déclenchent des erreurs du compilateur :  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## Types anonymes  
 Les types anonymes utilisent les initialiseurs d'objets pour créer des instances de types nouveaux que vous ne définissez ni ne nommez explicitement.  Au contraire, le compilateur génère un type d'après les propriétés que vous désignez, dans la liste d'initialiseurs d'objets.  Le nom du type de données n'étant pas spécifié, ce dernier est considéré comme un *type anonyme*.  Comparez, par exemple, la déclaration suivante à la déclaration préalable correspondant à `cust6`.  
  
 [!CODE [VbVbalrObjectInit#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#13)]  
  
 La seule différence est syntaxique : aucun nom n'est spécifié après `New` pour le type de données.  Toutefois, ce qui se passe est assez différent.  Le compilateur définit un nouveau type anonyme qui a deux propriétés, `Name` et `City`et crée une instance de ce type avec les valeurs spécifiées.  L'inférence de type détermine les types `Name` et `City` de l'exemple comme étant des chaînes.  
  
> [!CAUTION]
>  Le nom du type anonyme, généré par le compilateur, et peut varier de compilation en compilation.  Votre code ne doit pas utiliser ni compter sur le nom d'un type anonyme.  
  
 Le nom du type n'étant pas disponible, vous ne pouvez pas utiliser de clause `As` pour déclarer `cust13`.  Son type doit être déduit.  Sans utiliser la liaison tardive, cela limite l'utilisation de types anonymes aux variables locales.  
  
 Les types anonymes fournissent un support essentiel aux requêtes [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  Pour plus d'informations sur l'utilisation des types anonymes dans les requêtes, consultez [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) et [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### Remarques sur les types anonymes  
  
-   En général, la plupart ou la totalité des propriétés d'une déclaration de type anonyme est constituée de propriétés de clé, indiquées en tapant le mot clé `Key` devant le nom de la propriété.  
  
     [!CODE [VbVbalrObjectInit#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#14)]  
  
     Pour plus d'informations sur les propriétés de clé, consultez [Key](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   À l'instar des types nommés, les listes d'initialiseurs pour les définitions de types anonymes doivent déclarer au moins une propriété.  
  
     [!CODE [VbVbalrObjectInit#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#2)]  
  
-   Lorsqu'une instance de type anonyme est déclarée, le compilateur génère une définition de type anonyme correspondante.  Les noms et types de données des propriétés sont pris à la déclaration d'instance et sont inclus par le compilateur dans la définition.  Les propriétés ne sont pas nommées ni définies en avance, comme elles seraient dans le cas d'un type nommé.  Leurs types sont déduits.  Vous ne pouvez pas spécifier les types de données des propriétés en utilisant une clause `As`.  
  
-   Les types anonymes peuvent également établir les noms et valeurs de leurs propriétés de nombreuses manières différentes.  Par exemple, une propriété de type anonyme peut prendre à la fois le nom et la valeur d'une variable, ou le nom et la valeur de la propriété d'un autre objet.  
  
     [!CODE [VbVbalrObjectInit#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrObjectInit#15)]  
  
     Pour plus d'informations sur les options de définition des propriétés dans les types anonymes, consultez [Comment : déduire les types et les noms de propriétés dans des déclarations de types anonymes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## Voir aussi  
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Comment : déduire les types et les noms de propriétés dans des déclarations de types anonymes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)   
 [How to: Declare an Object by Using an Object Initializer](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)