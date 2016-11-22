---
title: "Introduction to LINQ in Visual Basic | Microsoft Docs"
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
  - "queries [LINQ in Visual Basic], about LINQ in Visual Basic queries"
  - "query execution [LINQ in Visual Basic]"
  - "range variables"
  - "LINQ [Visual Basic]"
  - "LINQ [Visual Basic], about LINQ in Visual Basic"
  - "query expressions [LINQ in Visual Basic]"
  - "LINQ"
  - "deferred execution"
  - "iteration variables"
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Introduction to LINQ in Visual Basic
LINQ \(Language\-Integrated Query\) ajoute des fonctions de requête à [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] et fournit des fonctions simples et puissantes permettant de travailler avec tous les types de données.  Au lieu d'envoyer une requête à une base de données à des fins de traitement ou d'utiliser une syntaxe de requête différente pour chaque type de données que vous recherchez, LINQ introduit des requêtes dans le cadre du langage [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Il utilise une syntaxe unifiée indépendamment du type de données.  
  
 LINQ vous permet d'interroger les données d'une base de données SQL Server, données XML, collections et tableaux en mémoire, groupe de données [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] ou toute autre source de données distante ou locale qui prend en charge LINQ.  Vous pouvez faire toutes ces choses avec les éléments de langage [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] communs.  Comme vos requêtes sont écrites en langage [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], vos résultats de requête sont retournés en tant qu'objets fortement typés.  Ces objets prennent en charge IntelliSense, qui vous permet d'écrire du code plus rapidement et d'intercepter les erreurs dans vos requêtes au moment de la compilation plutôt qu'au moment de l'exécution.  Les requêtes LINQ peuvent être utilisées comme source de requêtes supplémentaires pour affiner les résultats.  Elles peuvent également être liées à des contrôles pour que les utilisateurs puissent afficher et modifier facilement vos résultats de requête.  
  
 Par exemple, l'exemple de code suivant affiche une requête LINQ qui retourne une liste de clients à partir d'une collection et les regroupe en fonction de leur emplacement.  
  
 [!CODE [VbVbalrIntroToLINQ#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#1)]  
  
 Cette rubrique comprend des informations sur les sujets suivants :  
  
-   [Exécution des exemples](#RunningtheExamples)  
  
-   [Fournisseurs LINQ](#LINQProviders)  
  
-   [Structure d'une requête LINQ](#StructureOfALINQQuery)  
  
-   [Opérateurs de requête LINQ Visual Basic](#VisualBasicLINQQueryOperators)  
  
-   [Connexion à une base de données à l'aide de LINQ to SQL](#ConnectingToADatabase)  
  
-   [Fonctionnalités Visual Basic prenant en charge LINQ](#VisualBasicFeaturesThatSupportLINQ)  
  
-   [Exécution de requête différée et immédiate](#QueryExecution)  
  
-   [XML en Visual Basic](#XMLInVisualBasic)  
  
-   [Ressources connexes](#RelatedResources)  
  
-   [Rubriques « Comment » et « Procédure pas à pas »](#HowToAndWalkthroughTopics)  
  
##  <a name="RunningtheExamples"></a> Exécution des exemples  
 Pour exécuter les exemples de l'introduction et de la section « Structure d'une requête LINQ », incluez le code suivant qui retourne les listes de clients et de commandes.  
  
 [!CODE [VbVbalrIntroToLINQ#31](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#31)]  
  
##  <a name="LINQProviders"></a> Fournisseurs LINQ  
 Un *fournisseur LINQ* mappe vos requêtes LINQ [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] à la source de données interrogée.  Quand vous écrivez une requête LINQ, le fournisseur prend cette requête et la traduit en commandes que la source de données sera en mesure d'exécuter.  Le fournisseur convertit également des données de la source en objets qui composent votre résultat de la requête.  Enfin, il convertit des objets en données quand vous envoyez des mises à jour à la source de données.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] inclut les fournisseurs LINQ suivants.  
  
|||  
|-|-|  
|Fournisseur|Description|  
|LINQ to Objects|Le fournisseur LINQ to Objects vous permet d'interroger des collections et des tableaux en mémoire.  Si un objet prend en charge l'interface <xref:System.Collections.IEnumerable> ou <xref:System.Collections.Generic.IEnumerable%601>, le fournisseur LINQ to Objects vous permet de l'interroger.<br /><br /> Vous pouvez activer le fournisseur LINQ to Objects en important l'espace de noms <xref:System.Linq>, importé par défaut pour tous les projets [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].<br /><br /> Pour plus d'informations sur le fournisseur LINQ to Objects, consultez [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Le fournisseur LINQ to SQL vous permet d'interroger et de modifier des données dans une base de données SQL Server.  Cela facilite le mappage du modèle objet d'une application aux tables et objets d'une base de données.<br /><br /> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] facilite l'utilisation de LINQ to SQL en incluant le Concepteur Objet Relationnel \(Concepteur O\/R\).  Ce concepteur est utilisé pour créer un modèle objet dans une application qui effectue un mappage aux objets d'une base de données. Le Concepteur O\/R fournit également des fonctionnalités pour mapper les procédures stockées et les fonctions à l'objet <xref:System.Data.Linq.DataContext>, qui gère la communication avec la base de données et stocke l'état des contrôles d'accès concurrentiel optimiste.<br /><br /> Pour plus d'informations sur le fournisseur LINQ to SQL, consultez [LINQ à SQL](../Topic/LINQ%20to%20SQL.md).  Pour plus d'informations sur le Concepteur Objet Relationnel, consultez [Concepteur Objet\/Relationnel \(Concepteur O\/R\)](/visual-studio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Le fournisseur LINQ to XML vous permet d'interroger et de modifier du code XML.  Vous pouvez modifier du code XML en mémoire ou le charger à partir d'un fichier, mais également l'enregistrer dans un fichier.<br /><br /> En outre, le fournisseur LINQ to XML active des littéraux XML et des propriétés d'axe XML qui vous permettent d'écrire directement du code XML dans votre code [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Pour plus d'informations, consultez [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Le fournisseur LINQ to DataSet vous permet d'interroger et de mettre à jour des données dans un dataset [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)].  Vous pouvez ajouter la puissance de LINQ aux applications qui utilisent des groupes de données afin de simplifier et d'étendre vos capacités de requête, d'agrégation et de mise à jour des données dans votre dataset.<br /><br /> Pour plus d'informations, consultez [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md).|  
  
##  <a name="StructureOfALINQQuery"></a> Structure d'une requête LINQ  
 Une requête LINQ, souvent appelée *expression de requête*, se compose d'une combinaison de clauses de requête qui identifient les sources de données et les variables d'itération pour la requête.  Une expression de requête peut également inclure des instructions de tri, de filtrage, de regroupement et de jonction ou des calculs applicables aux données sources.  La syntaxe de l'expression de requête ressemble à la syntaxe de SQL ; par conséquent, une grande partie de cette syntaxe vous semblera familière.  
  
 Une expression de requête commence par une clause `From`.  Cette clause identifie les données sources d'une requête et les variables utilisées pour faire individuellement référence à chaque élément des données sources.  Ces variables sont appelées *variables de portée* ou *variables d'itération*.  La clause `From` est nécessaire pour une requête, à l'exception des requêtes `Aggregate`, où la clause `From` est facultative.  Après avoir identifié la portée et la source de la requête dans les clauses `From` ou `Aggregate`, vous pouvez inclure toute combinaison de clauses de requête pour affiner la requête.  Pour plus d'informations sur les clauses de requête, consultez la section Opérateurs de requête LINQ [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] plus loin dans cette rubrique.  Par exemple, la requête suivante identifie une collection de sources de données client comme variable `customers` et une variable d'itération appelée `cust`.  
  
 [!CODE [VbVbalrIntroToLINQ#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#2)]  
  
 Cet exemple représente une requête valide en elle\-même ; toutefois, la requête gagne en puissance quand vous ajoutez davantage de clauses de requête pour affiner le résultat.  Par exemple, vous pouvez ajouter une clause `Where` pour filtrer le résultat en fonction d'une ou plusieurs valeurs.  Les expressions de requête forment une ligne unique de code ; il vous suffit d'ajouter des clauses de requête supplémentaires à la fin de la requête.  Vous pouvez décomposer une requête en plusieurs lignes de texte pour améliorer la lisibilité à l'aide du trait de soulignement \(\_\), un caractère de continuation de ligne.  L'exemple de code suivant illustre une requête qui inclut une clause `Where`.  
  
 [!CODE [VbVbalrIntroToLINQ#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#3)]  
  
 Autre clause de requête performante, la clause `Select` vous permet de retourner uniquement des champs sélectionnés de la source de données.  Les requêtes LINQ retournent des collections énumérables d'objets fortement typés.  Une requête peut retourner une collection de types anonymes ou nommés.  Vous pouvez utiliser la clause `Select` pour retourner uniquement un champ de la source de données.  Dans ce cas, le type de la collection retournée est le type de ce champ unique.  Vous pouvez également utiliser la clause `Select` pour retourner plusieurs champs de la source de données.  Dans ce cas, le type de la collection retournée est un nouveau type anonyme.  Vous pouvez également faire correspondre les champs retournés par la requête aux champs d'un type nommé spécifié.  L'exemple de code suivant affiche une expression de requête qui retourne une collection de types anonymes dont les membres sont remplis des données des champs sélectionnés de la source de données.  
  
 [!CODE [VbVbalrIntroToLINQ#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#4)]  
  
 Les requêtes LINQ peuvent également être utilisées pour combiner plusieurs sources de données et retourner un résultat unique.  Cette opération peut être effectuée à l'aide d'une ou plusieurs clauses `From` ou en utilisant les clauses de requête `Join` ou `Group Join`.  L'exemple de code suivant illustre une expression de requête qui combine des données de client et de commande et retourne une collection de types anonymes contenant ces deux types de données.  
  
 [!CODE [VbVbalrIntroToLINQ#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#5)]  
  
 Vous pouvez utiliser la clause `Group Join` pour créer un résultat de requête hiérarchique contenant une collection d'objets customer.  Chaque objet customer possède une propriété contenant une collection de toutes les commandes de ce client.  L'exemple de code suivant affiche une expression de requête qui combine des données client\/commande sous forme de résultat hiérarchique et retourne une collection de types anonymes.  La requête retourne un type qui inclut une propriété `CustomerOrders` contenant une collection de données de commande pour le client.  Il inclut également une propriété `OrderTotal` qui contient la somme des totaux pour toutes les commandes de ce client.  \(Cette requête est équivalente à une JOINTURE EXTERNE GAUCHE.\)  
  
 [!CODE [VbVbalrIntroToLINQ#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#6)]  
  
 Il existe plusieurs opérateurs de requête LINQ supplémentaires qui vous permettent de créer des expressions de requête puissantes.  La section suivante de cette rubrique présente les différentes clauses de requête que vous pouvez inclure dans une expression de requête.  Pour plus d'informations sur les clauses de requête [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], consultez [Queries](../../../../visual-basic/language-reference/queries/queries.md).  
  
##  <a name="VisualBasicLINQQueryOperators"></a> Opérateurs de requête LINQ Visual Basic  
 Les classes de l'espace de noms <xref:System.Linq> et des autres espaces de noms qui prennent en charge les requêtes LINQ incluent des méthodes que vous pouvez appeler pour créer et affiner les requêtes en fonction des besoins de votre application.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] inclut des mots clés pour les clauses de requête les plus courantes, comme indiqué dans le tableau suivant.  
  
|||  
|-|-|  
|Terme|Définition|  
|[From Clause](../../../../visual-basic/language-reference/queries/from-clause.md)|Une requête doit commencer par une clause `From` ou `Aggregate`.  Une clause `From` spécifie une collection de sources et une variable d'itération pour une requête.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#7)]|  
|[Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md)|Facultatif.  Déclare un jeu de variables d'itération pour une requête.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#8)]<br /><br /> Si une clause `Select` n'est pas spécifiée, les variables d'itération de la requête se composent des variables d'itération spécifiées par la clause `From` ou `Aggregate`.|  
|[Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md)|Facultatif.  Spécifie une condition de filtrage pour une requête.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#9)]|  
|[Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md)|Facultatif.  Spécifie l'ordre de tri des colonnes dans une requête.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#10)]|  
|[Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md)|Facultatif.  Combine deux collections en une collection unique.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#11)]|  
|[Group By, clause](../../../../visual-basic/language-reference/queries/group-by-clause.md)|Facultatif.  Regroupe les éléments d'un résultat de requête.  Peut être utilisée pour appliquer des fonctions d'agrégation à chaque groupe.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#12)]|  
|[Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md)|Facultatif.  Combine deux collections en une collection hiérarchique unique.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#13)]|  
|[Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md)|Une requête doit commencer par une clause `From` ou `Aggregate`.  Une clause `Aggregate` applique une ou plusieurs fonctions d'agrégation à une collection.  Par exemple, vous pouvez utiliser la clause `Aggregate` pour calculer une somme de tous les éléments retournés par une requête.<br /><br /> [!CODE [VbVbalrIntroToLINQ#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#14)]<br /><br /> Vous pouvez également utiliser la clause `Aggregate` pour modifier une requête.  Par exemple, vous pouvez utiliser la clause `Aggregate` pour effectuer un calcul sur une collection de requêtes connexe.<br /><br /> [!CODE [VbVbalrIntroToLINQ#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#15)]|  
|[Let Clause](../../../../visual-basic/language-reference/queries/let-clause.md)|Facultatif.  Calcule une valeur et l'assigne à une nouvelle variable dans la requête.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#16)]|  
|[Distinct Clause](../../../../visual-basic/language-reference/queries/distinct-clause.md)|Facultatif.  Restreint les valeurs de la variable d'itération actuelle pour éliminer les valeurs en double dans les résultats de la requête.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#17)]|  
|[Skip Clause](../../../../visual-basic/language-reference/queries/skip-clause.md)|Facultatif.  Ignore un nombre spécifié d'éléments dans une collection, puis retourne les éléments restants.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#18)]|  
|[Skip While Clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md)|Facultatif.  Ignore les éléments d'une collection tant qu'une condition spécifiée a la valeur `true`, puis retourne les éléments restants.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#19](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#19)]|  
|[Take Clause](../../../../visual-basic/language-reference/queries/take-clause.md)|Facultatif.  Retourne un nombre spécifié d'éléments contigus à partir du début d'une collection.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#20](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#20)]|  
|[Take While Clause](../../../../visual-basic/language-reference/queries/take-while-clause.md)|Facultatif.  Inclut les éléments d'une collection tant qu'une condition spécifiée a la valeur `true` et ignore les éléments restants.  Exemple :<br /><br /> [!CODE [VbVbalrIntroToLINQ#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#21)]|  
  
 Pour plus d'informations sur les clauses de requête [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], consultez [Queries](../../../../visual-basic/language-reference/queries/queries.md).  
  
 Vous pouvez utiliser des fonctionnalités de requête LINQ supplémentaires en appelant des membres des types énumérables et requêtables fournis par LINQ.  Vous pouvez utiliser ces fonctions supplémentaires en appelant un opérateur de requête particulier sur le résultat d'une expression de requête.  Par exemple, l'exemple de code suivant utilise la méthode <xref:System.Linq.Enumerable.Union%2A> pour fusionner les résultats de deux requêtes.  Il utilise la méthode <xref:System.Linq.Enumerable.ToList%2A> pour retourner le résultat de la requête sous forme de liste générique.  
  
 [!CODE [VbVbalrIntroToLINQ#22](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ#22)]  
  
 Pour plus d'informations sur les fonctions LINQ supplémentaires, consultez [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
##  <a name="ConnectingToADatabase"></a> Connexion à une base de données à l'aide de LINQ to SQL  
 Dans [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], vous identifiez les objets de base de données SQL Server, comme les tables, vues et procédures stockées, auxquels vous souhaitez accéder en utilisant un fichier LINQ to SQL.  Un fichier LINQ to SQL possède une extension .dbml.  
  
 Quand vous avez établi une connexion valide à une base de données SQL Server, vous pouvez ajouter un modèle d'élément **Classes LINQ to SQL** à votre projet.  Le Concepteur Objet Relationnel \(Concepteur O\/R\) s'affiche alors.  Le Concepteur O\/R vous permet de faire glisser les éléments auxquels vous souhaitez accéder dans votre code à partir de l'**Explorateur de serveurs**\/**Explorateur de bases de données** sur l'aire du concepteur.  Le fichier LINQ to SQL ajoute un objet <xref:System.Data.Linq.DataContext> à votre projet.  Cet objet inclut des propriétés et des collections pour les tables et vues auxquelles vous souhaitez accéder, et aux méthodes des procédures stockées que vous souhaitez appeler.  Après avoir enregistré vos modifications dans le fichier LINQ to SQL \(.dbml\), vous pouvez accéder à ces objets dans votre code en référençant l'objet <xref:System.Data.Linq.DataContext> défini par le Concepteur O\/R.  L'objet <xref:System.Data.Linq.DataContext> de votre projet est nommé d'après le nom de votre fichier LINQ to SQL.  Par exemple, un fichier LINQ to SQL nommé Northwind.dbml créera un objet <xref:System.Data.Linq.DataContext> nommé `NorthwindDataContext`.  
  
 Pour obtenir des exemples accompagnés d'instructions pas à pas, consultez [How to: Query a Database](../../../../visual-basic/programming-guide/language-features/linq/how-to-query-a-database-by-using-linq.md) et [How to: Call a Stored Procedure](../../../../visual-basic/programming-guide/language-features/linq/how-to-call-a-stored-procedure-by-using-linq.md).  
  
##  <a name="VisualBasicFeaturesThatSupportLINQ"></a> Fonctionnalités Visual Basic prenant en charge LINQ  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] inclut d'autres fonctionnalités notables qui facilitent l'utilisation de LINQ et réduisent la quantité de code que vous devez écrire pour effectuer des requêtes LINQ.  Notamment :  
  
-   les **types anonymes**, qui permettent de créer un type en fonction d'un résultat de requête ;  
  
-   les **variables implicitement typées**, qui vous permettent de différer la spécification d'un type et laisser le compilateur le déduire en fonction du résultat de la requête ;  
  
-   les **méthodes d'extension**, qui vous permettent d'étendre un type existant avec vos propres méthodes sans modifier le type lui\-même.  
  
 Pour plus d'informations, consultez [Visual Basic Features That Support LINQ](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md).  
  
##  <a name="QueryExecution"></a> Exécution de requête différée et immédiate  
 L'exécution d'une requête est distincte de sa création.  Après avoir créé une requête, son exécution est déclenchée par un mécanisme distinct.  Une requête peut être exécutée dès qu'elle est définie \(*exécution immédiate*\) ou la définition peut être stockée et la requête peut être exécutée ultérieurement \(*exécution différée*\).  
  
 Par défaut, quand vous créez une requête, cette dernière ne s'exécute pas immédiatement.  À la place, la définition de la requête est stockée dans la variable utilisée pour référencer le résultat de la requête.  Quand vous accédez à la variable de résultat de la requête ultérieurement dans le code, par exemple, dans une boucle `For…Next`, la requête est exécutée.  Ce processus est connu sous le nom d'*exécution différée*.  
  
 Les requêtes peuvent également être exécutées quand elles sont définies ; cette méthode est appelée *exécution immédiate*.  Vous pouvez déclencher l'exécution immédiate en appliquant une méthode qui requiert l'accès aux éléments individuels du résultat de la requête.  L'inclusion d'une fonction d'agrégation, telle que `Count`, `Sum`, `Average`, `Min` ou `Max` peut engendrer un tel résultat.  Pour plus d'informations sur les fonctions d'agrégation, consultez [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 L'utilisation de la méthode `ToList` ou `ToArray` force également l'exécution immédiate.  Cela peut être utile quand vous souhaitez exécuter immédiatement la requête et mettre en cache les résultats.  Pour plus d'informations sur ces méthodes, consultez [Converting Data Types](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 Pour plus d'informations sur l'exécution des requêtes, consultez [Écriture de votre première requête LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
##  <a name="XMLInVisualBasic"></a> XML en Visual Basic  
 Les fonctionnalités XML de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] incluent des littéraux XML et des propriétés d'axe XML, qui facilitent la création, l'accès, l'interrogation et la modification du XML dans votre code.  Les littéraux XML vous permettent d'écrire directement en XML dans votre code.  Le compilateur Visual Basic traite le XML comme un objet de donnée de première classe.  
  
 L'exemple de code suivant montre comment créer un élément XML, accéder à ses sous\-éléments et attributs, et interroger son contenu à l'aide de LINQ.  
  
 [!CODE [VbXmlSamples#8](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#8)]  
  
 Pour plus d'informations, consultez [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).  
  
##  <a name="RelatedResources"></a> Ressources connexes  
  
|||  
|-|-|  
|Rubrique|Description|  
|[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)|Décrit les fonctionnalités XML de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] qui peuvent être interrogées et qui vous permettent d'inclure du XML sous forme d'objets de données de première classe dans votre code [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].|  
|[Queries](../../../../visual-basic/language-reference/queries/queries.md)|Fournit des informations de référence sur les clauses de requête disponibles dans [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].|  
|[LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)|Inclut des informations générales, un guide de programmation et des exemples de requêtes LINQ.|  
|[LINQ à SQL](../Topic/LINQ%20to%20SQL.md)|Inclut des informations générales, un guide de programmation et des exemples de LINQ to SQL.|  
|[LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)|Inclut des informations générales, un guide de programmation et des exemples de LINQ to Objects.|  
|[LINQ to ADO.NET](../Topic/LINQ%20to%20ADO.NET%20\(Portal%20Page\)1.md)|Inclut des liens vers des informations générales, un guide de programmation et des exemples de LINQ to [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)].|  
|[LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)|Inclut des informations générales, un guide de programmation et des exemples de LINQ to XML.|  
  
##  <a name="HowToAndWalkthroughTopics"></a> Rubriques « Comment » et « Procédure pas à pas »  
 [How to: Query a Database](../../../../visual-basic/programming-guide/language-features/linq/how-to-query-a-database-by-using-linq.md)  
  
 [How to: Call a Stored Procedure](../../../../visual-basic/programming-guide/language-features/linq/how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [How to: Modify Data in a Database](../../../../visual-basic/programming-guide/language-features/linq/how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [How to: Combine Data with Joins](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)  
  
 [How to: Sort Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)  
  
 [How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)  
  
 [How to: Count, Sum, or Average Data](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [How to: Find the Minimum or Maximum Value in a Query Result](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Procédure pas à pas : création de classes LINQ to SQL \(Concepteur O\/R\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)  
  
 [Procédure : assigner des procédures stockées pour effectuer des mises à jour, des insertions et des suppressions \(Concepteur O\/R\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)  
  
## Chapitres proposés  
 [Chapitre 17 : LINQ](http://go.microsoft.com/fwlink/?LinkId=195277) dans [Programming Visual Basic 2008](http://go.microsoft.com/fwlink/?LinkId=195383)  
  
## Voir aussi  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)   
 [Vue d'ensemble de LINQ to DataSet](../Topic/LINQ%20to%20DataSet%20Overview.md)   
 [LINQ à SQL](../Topic/LINQ%20to%20SQL.md)   
 [Exemples LINQ](../Topic/LINQ%20Samples.md)   
 [Concepteur Objet\/Relationnel \(Concepteur O\/R\)](/visual-studio/data-tools/linq-to-sql-tools-in-visual-studio2)   
 [Méthodes DataContext \(Concepteur O\/R\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)