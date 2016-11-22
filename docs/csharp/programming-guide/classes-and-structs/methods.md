---
title: "M&#233;thodes (guide de programmation C#) | Microsoft Docs"
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
  - "langage C#, méthodes"
  - "méthodes (C#)"
ms.assetid: cc738f07-e8cd-4683-9585-9f40c0667c37
caps.latest.revision: 41
caps.handback.revision: 41
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# M&#233;thodes (guide de programmation C#)
Une méthode est un bloc de code qui contient une série d'instructions. Un programme provoque l'exécution des instructions en appelant la méthode et en spécifiant les éventuels arguments de méthode requis. En C\#, chaque instruction exécutée est effectuée dans le contexte d'une méthode. La méthode Main est le point d'entrée de chaque application C\# et elle est appelée par le Common Language Runtime \(CLR\) au démarrage du programme.  
  
> [!NOTE]
>  Cette rubrique décrit les méthodes nommées. Pour plus d’informations sur les fonctions anonymes, consultez [Fonctions anonymes](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## Signatures de méthode  
 Les méthodes sont déclarées dans une [classe](../../../csharp/language-reference/keywords/class.md) ou un [struct](../../../csharp/language-reference/keywords/struct.md) en spécifiant le niveau d'accès comme `public` ou `private`, les modificateurs facultatifs comme `abstract` ou `sealed`, la valeur de retour, le nom de la méthode et les éventuels paramètres de méthode. Ces parties forment ensemble la signature de la méthode.  
  
> [!NOTE]
>  Un type de retour d'une méthode ne fait pas partie de la signature de la méthode à des fins de surcharge de méthode. Toutefois, il fait partie de la signature de la méthode lors de la détermination de la compatibilité entre un délégué et la méthode vers laquelle il pointe.  
  
 Les paramètres de méthode sont placés entre parenthèses et séparés par des virgules. Des parenthèses vides indiquent que la méthode ne requiert aucun paramètre. Cette classe contient trois méthodes :  
  
 [!CODE [csProgGuideObjects#40](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#40)]  
  
## Accès aux méthodes  
 L'appel d'une méthode sur un objet revient à accéder à un champ. Après le nom de l'objet, ajoutez un point, le nom de la méthode et les parenthèses. Les arguments sont répertoriés entre les parenthèses et séparés par des virgules. Les méthodes de la classe `Motorcycle` peuvent donc être appelées comme dans l'exemple suivant :  
  
 [!CODE [csProgGuideObjects#41](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#41)]  
  
## Paramètres de méthode et Arguments  
 La définition de la méthode spécifie les noms et types des paramètres requis. Quand le code appelant appelle la méthode, il fournit des valeurs concrètes appelées arguments pour chaque paramètre. Les arguments doivent être compatibles avec le type de paramètre, mais le nom de l'argument \(le cas échéant\) utilisé dans le code appelant ne doit pas nécessairement être le même que celui du paramètre défini dans la méthode. Exemple :  
  
 [!CODE [csProgGuideObjects#74](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#74)]  
  
## Passer par référence et passer par valeur  
 Par défaut, quand un type valeur est passé à une méthode, une copie est passée au lieu de l'objet lui\-même. Ainsi, les modifications apportées à l'argument n'ont aucun effet sur la copie d'origine dans la méthode d'appel. Vous pouvez passer un type valeur par référence en utilisant le mot clé ref. Pour plus d'informations, consultez [Passage de paramètres de type valeur](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md). Pour obtenir la liste des types valeur intégrés, consultez [Tableau des types valeur](../../../csharp/language-reference/keywords/value-types-table.md).  
  
 Quand un objet d'un type référence est passé à une méthode, une référence à l'objet est passée. Autrement dit, la méthode ne reçoit pas l'objet lui\-même mais un argument qui indique l'emplacement de l'objet. Si vous modifiez un membre de l'objet à l'aide de cette référence, la modification est répercutée dans l'argument de la méthode d'appel, même si vous passez l'objet par valeur.  
  
 Vous créez un type référence à l'aide du mot clé `class`, comme le montre l'exemple suivant.  
  
 [!CODE [csProgGuideObjects#42](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#42)]  
  
 Maintenant, si vous passez un objet basé sur ce type à une méthode, une référence à l'objet est passée. L'exemple suivant passe un objet de type `SampleRefType` à la méthode `ModifyObject`.  
  
 [!CODE [csProgGuideObjects#75](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#75)]  
  
 L'exemple produit essentiellement la même chose que l'exemple précédent, dans la mesure où il passe un argument par valeur à une méthode. Mais, puisqu'un type référence est utilisé, le résultat est différent. La modification apportée dans `ModifyObject` au champ `value` du paramètre, `obj`, modifie également le champ `value` de l'argument, `rt`, dans la méthode `TestRefType`. La méthode `TestRefType` affiche 33 en tant que sortie.  
  
 Pour plus d’informations sur le passage de types référence par valeur et par référence, consultez [Passage de paramètres de type référence](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) et [Types référence](../../../csharp/language-reference/keywords/reference-types.md).  
  
## Valeurs de retour  
 Les méthodes peuvent retourner une valeur à l'appelant. Si le type de retour, le type répertorié avant le nom de la méthode, n'est pas `void`, la méthode peut retourner la valeur à l'aide du mot clé `return`. Une instruction avec le mot clé `return` suivi d'une valeur qui correspond au type de retour retourne cette valeur à l'appelant de la méthode. Le mot clé `return` arrête également l'exécution de la méthode. Si le type de retour est `void`, une instruction `return` sans valeur est quand même utile pour arrêter l'exécution de la méthode. Sans le mot clé `return`, la méthode arrête de s'exécuter quand elle atteint la fin du bloc de code. Les méthodes dotées d'un type de retour non void doivent utiliser le mot clé `return` pour retourner une valeur. Par exemple, ces deux méthodes utilisent le mot clé `return` pour retourner des entiers :  
  
 [!CODE [csProgGuideObjects#44](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#44)]  
  
 Pour utiliser une valeur retournée à partir d'une méthode, la méthode d'appel peut utiliser l'appel de méthode proprement dit partout où une valeur du même type peut suffire. Vous pouvez également affecter la valeur de retour à une variable. Par exemple, les deux exemples de code suivants remplissent le même objectif :  
  
 [!CODE [csProgGuideObjects#45](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#45)]  
  
 [!CODE [csProgGuideObjects#46](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#46)]  
  
 L'utilisation d'une variable locale, dans cet exemple, `result`, pour stocker une valeur est facultative. Elle peut favoriser la lisibilité du code ou s'avérer nécessaire si vous avez besoin de stocker la valeur d'origine de l'argument pour la portée entière de la méthode.  
  
 Retourner un tableau multidimensionnel à partir d’une méthode, M, qui modifie le contenu du tableau, n’est pas nécessaire si la fonction d’appel a passé le tableau à M. Vous pouvez retourner le tableau obtenu à partir de M pour le style approprié ou le flux fonctionnel des valeurs, mais cela n’est pas nécessaire.  Vous n’avez pas besoin de retourner le tableau modifié parce que C\# passe tous les types référence par valeur et parce que la valeur d’une référence de tableau est le pointeur vers ce tableau. Dans la méthode M, toute modification apportée au contenu du tableau est observable par tout code qui possède une référence au tableau, comme indiqué dans l’exemple suivant.  
  
```c#  
static void Main(string[] args) { int[,] matrix = new int[2, 2]; FillMatrix(matrix); // matrix is now full of -1 } public static void FillMatrix(int[,] matrix) { for (int i = 0; i < matrix.GetLength(0); i++) { for (int j = 0; j < matrix.GetLength(1); j++) { matrix[i, j] = -1; } } }  
  
```  
  
 Pour plus d'informations, consultez [return](../../../csharp/language-reference/keywords/return.md).  
  
## Méthodes async  
 La fonctionnalité async vous permet d'appeler des méthodes asynchrones sans utiliser de rappels explicites ni fractionner manuellement votre code entre plusieurs méthodes ou expressions lambda. La fonctionnalité async a été introduite dans [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs_dev11_long_md.md)].  
  
 Si vous marquez une méthode avec le modificateur [async](../../../csharp/language-reference/keywords/async.md), vous pouvez utiliser l'opérateur [await](../../../csharp/language-reference/keywords/await.md) dans la méthode. Quand le contrôle atteint une expression await dans la méthode async, il retourne à l'appelant, et la progression dans la méthode est interrompue jusqu'à ce que la tâche attendue se termine. Quand la tâche est terminée, l'exécution peut reprendre dans la méthode.  
  
> [!NOTE]
>  Une méthode async retourne à l'appelant quand elle rencontre le premier objet await qui n'est pas encore terminé ou quand elle atteint la fin de la méthode async, selon la première éventualité.  
  
 Une méthode async peut avoir un type de retour <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> ou void. Le type de retour void est principalement utilisé pour définir les gestionnaires d'événements, où un type de retour void est requis. Une méthode async qui retourne void ne peut pas être attendue, et l'appelant d'une méthode retournant void ne peut intercepter aucune exception levée par la méthode.  
  
 Dans l'exemple suivant, `DelayAsync` est une méthode async dont le type de retour est <xref:System.Threading.Tasks.Task%601>.`DelayAsync` a une instruction `return` qui retourne un entier. Ainsi, la déclaration de méthode de `DelayAsync` doit avoir un type de retour de `Task<int>`. Étant donné que le type de retour est `Task<int>`, l'évaluation de l'expression `await` dans `DoSomethingAsync` produit un entier, comme le montre l'instruction suivante : `int result = await delayTask`.  
  
 La méthode `startButton_Click` est un exemple de méthode async dont le type de retour est void. Étant donné que `DoSomethingAsync` est une méthode async, la tâche pour l'appel à `DoSomethingAsync` doit être attendue, comme le montre l'instruction suivante : `await DoSomethingAsync();`. La méthode `startButton_Click` doit être définie avec le modificateur `async` car la méthode a une expression `await`.  
  
 [!CODE [csAsyncMethod#2](../CodeSnippet/VS_Snippets_VBCSharp/csasyncmethod#2)]  
  
 Une méthode async ne peut pas déclarer de paramètres [ref](../../../csharp/language-reference/keywords/ref.md) ou [out](../../../csharp/language-reference/keywords/out.md), mais elle peut appeler des méthodes qui comportent ces paramètres.  
  
 Pour plus d’informations sur les méthodes asynchrones, consultez [Programmation asynchrone avec Async et Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md), [Flux de contrôle dans les programmes Async](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md) et [Types de retour Async](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Définitions de corps d'expression  
 Il est courant d'avoir des définitions de méthode qui retournent tout simplement le résultat d'une expression immédiatement, ou qui ont une seule instruction en tant que corps de la méthode.  Il existe un raccourci de syntaxe pour définir de telles méthodes en utilisant `=>` :  
  
```c#  
public Point Move(int dx, int dy) => new Point(x + dx, y + dy); public void Print() => Console.WriteLine(First + " " + Last); // Works with operators, properties, and indexers too. public static Complex operator +(Complex a, Complex b) => a.Add(b); public string Name => First + " " + Last; public Customer this[long id] => store.LookupCustomer(id);  
```  
  
 Si la méthode retourne `void` ou est une méthode async, alors le corps de la méthode doit être une expression d'instruction \(même chose avec les expressions lambda\).  En ce qui concerne les propriétés et indexeurs, ils doivent être en lecture seule et vous n'utilisez pas le mot clé d'accesseur `get`.  
  
## Itérateurs  
 Un itérateur exécute une itération personnalisée sur une collection, comme une liste ou un tableau. Un itérateur utilise l'instruction [yield return](../../../csharp/language-reference/keywords/yield.md) pour retourner chaque élément un par un. Quand une instruction [yield return](../../../csharp/language-reference/keywords/yield.md) est atteinte, l'emplacement actuel dans le code est mémorisé. L'exécution redémarre à partir de cet emplacement au prochain appel de l'itérateur.  
  
 Vous appelez un itérateur depuis le code client en utilisant une instruction [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
 Le type de retour d'un itérateur peut être <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> ou <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Pour plus d'informations, consultez [Itérateurs](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Classes et structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Modificateurs d'accès](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Classes statiques et membres de classe statique](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [Héritage](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Classes abstract et sealed et membres de classe](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [params](../../../csharp/language-reference/keywords/params.md)   
 [return](../../../csharp/language-reference/keywords/return.md)   
 [out](../../../csharp/language-reference/keywords/out.md)   
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [Passage de paramètres](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)