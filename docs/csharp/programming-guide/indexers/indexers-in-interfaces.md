---
title: "Indexeurs dans les interfaces (Guide de programmation C#) | Microsoft Docs"
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
  - "accesseurs (C#), indexeurs"
  - "indexeurs (C#), dans les interfaces"
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Indexeurs dans les interfaces (Guide de programmation C#)
Les indexeurs peuvent être déclarés sur une [interface](../../../csharp/language-reference/keywords/interface.md).  Les accesseurs des indexeurs d'interface diffèrent des accesseurs des indexeurs de [classe](../../../csharp/language-reference/keywords/class.md) sur les points suivants :  
  
-   Les accesseurs d'interface n'utilisent pas de modificateurs.  
  
-   Un accesseur d'interface ne possède pas de corps.  
  
 Ainsi, l'accesseur a pour objet d'indiquer si l'indexeur est en lecture\-écriture, en écriture seule ou en lecture seule.  
  
 Exemple d'accesseur d'indexeur d'interface :  
  
 [!CODE [csProgGuideIndexers#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideIndexers#3)]  
  
 La signature d'un indexeur doit différer des signatures de tous les autres indexeurs déclarés dans la même interface.  
  
## Exemple  
 L'exemple suivant montre comment implémenter des indexeurs d'interface.  
  
 [!CODE [csProgGuideIndexers#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideIndexers#4)]  
  
 Dans l'exemple précédent, vous pouvez utiliser l'implémentation explicite du membre d'interface à l'aide du nom qualifié complet du membre d'interface.  Par exemple :  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 Toutefois, le nom qualifié complet est requis uniquement pour éviter toute ambiguïté lorsque la classe implémente plusieurs interfaces avec la même signature d'indexeur.  Par exemple, si la classe  `Employee` implémente deux interfaces, `ICitizen` et `IEmployee`, et que ces deux interfaces ont la même signature d'indexeur, l'implémentation explicite des membres d'interface est nécessaire.  Ainsi, la déclaration d'indexeur suivante :  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 implémente l'indexeur sur l'interface `IEmployee`, tandis que la déclaration suivante :  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 implémente l'indexeur sur l'interface `ICitizen`.  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Indexeurs](../../../csharp/programming-guide/indexers/index.md)   
 [Propriétés](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)