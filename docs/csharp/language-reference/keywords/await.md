---
title: "await (R&#233;f&#233;rence C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "await_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "await [C#]"
  - "await (mot clé) (C#)"
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
caps.latest.revision: 36
caps.handback.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# await (R&#233;f&#233;rence C#)
L'opérateur `await` est appliqué à une tâche dans une méthode asynchrone pour interrompre l'exécution de la méthode jusqu'à ce que la tâche attendue se termine.  La tâche représente un travail en cours.  
  
 La méthode asynchrone dans laquelle `await` est utilisé doit être modifiée par le mot clé [async](../../../csharp/language-reference/keywords/async.md).  Une telle méthode, définie à l'aide du modificateur `async` et contenant généralement une ou plusieurs expressions `await`, est appelée *méthode async*.  
  
> [!NOTE]
>  Les mots clés `async` et `await` ont été introduites dans Visual Studio 2012.  Pour une introduction à la programmation asynchrone, consultez [Programmation asynchrone avec Async et Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 La tâche à laquelle l'opérateur `await` est appliqué correspond généralement à la valeur de retour d'un appel à une méthode qui implémente le [modèle asynchrone basé sur des tâches](http://go.microsoft.com/fwlink/?LinkId=204847).  Les valeurs de type <xref:System.Threading.Tasks.Task> ou <xref:System.Threading.Tasks.Task%601> en sont des exemples.  
  
 Dans le code suivant, la méthode <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> renvoie un `Task\<byte[]>`, `getContentsTask`.  La tâche est une promesse de produire le tableau d'octets réel quand la tâche est terminée.  L'opérateur `await` est appliqué à `getContentsTask` pour suspendre l'exécution dans `SumPageSizesAsync` jusqu'à ce que `getContentsTask` soit terminé.  Entre\-temps, le contrôle revient à l'appelant de `SumPageSizesAsync`.  Quand `getContentsTask` est terminé, l'expression `await` s'évalue en tableau d'octets.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  Pour obtenir un exemple complet, consultez [Procédure pas à pas : accès au Web avec Async et Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Vous pouvez télécharger l'exemple depuis les [exemples de code pour développeur](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) sur le site Web Microsoft.  L'exemple est dans le projet AsyncWalkthrough\_HttpClient.  
  
 Comme indiqué dans l'exemple précédent, si `await` est appliqué au résultat d'un appel de méthode qui retourne un `Task<TResult>`, alors le type de l'expression `await` est TResult.  Si `await` est appliqué au résultat d'un appel de méthode qui retourne un `Task`, alors le type de l'expression `await` est void.  L'exemple suivant illustre la différence.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Une expression `await` ne bloque pas le thread sur lequel elle s'exécute.  Elle indique plutôt au compilateur de signer le reste de la méthode async comme une continuation sur la tâche attendue.  Le contrôle revient alors à l'appelant de la méthode async.  Quand la tâche est terminée, elle appelle sa continuation et l'exécution de la méthode async reprend là où elle s'était arrêtée.  
  
 Une expression `await` peut se produire uniquement dans le corps d'une méthode immédiatement englobante, une expression lambda ou une méthode anonyme marquée par un modificateur `async`.  Le terme *await* sert de mot clé uniquement dans ce contexte.  Partout ailleurs, il est interprété en tant qu'identificateur.  Au sein de la méthode, l'expression lambda ou la méthode anonyme, une expression `await` ne peut pas se produire dans le corps d'une fonction synchrone, dans une expression de requête, dans le bloc d'une [instruction lock](../../../csharp/language-reference/keywords/lock-statement.md) ou dans un contexte [non sécurisé](../../../csharp/language-reference/keywords/unsafe.md).  
  
## Exceptions  
 La plupart des méthodes async retournent un <xref:System.Threading.Tasks.Task> ou <xref:System.Threading.Tasks.Task%601>.  Les propriétés de la tâche retournée comportent des informations sur son état et son historique. Celles\-ci indiquent notamment si la tâche est terminée ou non, si la méthode async a levé une exception ou a été annulée et quel est le résultat final.  L'opérateur `await` accède à ces propriétés.  
  
 Si vous attendez une méthode async retournant des tâches qui lève une exception, l'opérateur `await` lève de nouveau l'exception.  
  
 Si vous attendez une méthode async retournant des tâches qui est annulée, l'opérateur `await` lève de nouveau une exception <xref:System.OperationCanceledException>.  
  
 Une tâche qui se trouve dans un état d'erreur peut refléter plusieurs exceptions.  Par exemple, la tâche peut être le résultat d'un appel à <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  Quand vous attendez une telle tâche, l'opération await lève à nouveau une seule des exceptions.  Toutefois, vous ne pouvez pas prédire laquelle de ces exceptions est de nouveau levée.  
  
 Pour obtenir des exemples de gestion des erreurs dans les méthodes asynchrones, consultez [try\-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## Exemple  
 L'exemple Windows Forms suivant illustre l'utilisation de `await` dans une méthode async, `WaitAsynchronouslyAsync`.  Comparez le comportement de cette méthode avec celui de `WaitSynchronously`.  Sans opérateur `await` appliqué à une tâche, `WaitSynchronously` s'exécute de façon synchrone en dépit de l'utilisation du modificateur `async` dans sa définition et d'un appel à <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> dans son corps.  
  
```c#  
  
private async void button1_Click(object sender, EventArgs e)  
{  
    // Call the method that runs asynchronously.  
    string result = await WaitAsynchronouslyAsync();  
  
    // Call the method that runs synchronously.  
    //string result = await WaitSynchronously ();  
  
    // Display the result.  
    textBox1.Text += result;  
}  
  
// The following method runs asynchronously. The UI thread is not  
// blocked during the delay. You can move or resize the Form1 window   
// while Task.Delay is running.  
public async Task<string> WaitAsynchronouslyAsync()  
{  
    await Task.Delay(10000);  
    return "Finished";  
}  
  
// The following method runs synchronously, despite the use of async.  
// You cannot move or resize the Form1 window while Thread.Sleep  
// is running because the UI thread is blocked.  
public async Task<string> WaitSynchronously()  
{  
    // Add a using directive for System.Threading.  
    Thread.Sleep(10000);  
    return "Finished";  
}  
```  
  
## Voir aussi  
 [Programmation asynchrone avec Async et Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Procédure pas à pas : accès au Web avec Async et Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [async](../../../csharp/language-reference/keywords/async.md)