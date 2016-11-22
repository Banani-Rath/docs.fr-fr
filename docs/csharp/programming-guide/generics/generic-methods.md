---
title: "M&#233;thodes g&#233;n&#233;riques (guide de programmation C#) | Microsoft Docs"
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
  - "génériques (C#), méthodes"
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# M&#233;thodes g&#233;n&#233;riques (guide de programmation C#)
Une méthode générique est une méthode qui est déclarée avec des paramètres de type, comme suit :  
  
 [!CODE [csProgGuideGenerics#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#22)]  
  
 L'exemple de code suivant montre une manière d'appeler la méthode, avec `int` comme argument de type :  
  
 [!CODE [csProgGuideGenerics#23](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#23)]  
  
 Vous pouvez également omettre l'argument de type et le compilateur le déduira.  L'appel suivant à `Swap` est équivalent à l'appel précédent :  
  
 [!CODE [csProgGuideGenerics#24](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#24)]  
  
 Les règles d'inférence de type s'appliquent aux méthodes statiques et aux méthodes d'instance.  Le compilateur peut déduire les paramètres de type d'après les arguments de méthode que vous passez. Il ne peut pas déduire les paramètres de type uniquement à partir d'une valeur de contrainte ou de retour.  Par conséquent, l'inférence de type ne fonctionne pas avec les méthodes qui n'ont pas de paramètres.  L'inférence de type a lieu au moment de la compilation avant que le compilateur essaie de résoudre toute signature de méthode surchargée.  Le compilateur applique la logique d'inférence de type à toutes les méthodes génériques qui partagent le même nom.  À l'étape de résolution de la surcharge, le compilateur inclut uniquement les méthodes génériques sur lesquelles l'inférence de type a réussi.  
  
 Dans une classe générique, les méthodes non génériques peuvent accéder aux paramètres de type de niveau de classe, comme suit :  
  
 [!CODE [csProgGuideGenerics#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#25)]  
  
 Si vous définissez une méthode générique qui accepte les mêmes paramètres de type que la classe conteneur, le compilateur génère l'avertissement CS0693, car, à l'intérieur de la portée de la méthode, l'argument fourni pour le `T` interne masque l'argument fourni pour le `T` externe.  Si vous avez besoin de la possibilité d'appeler une méthode de classe générique avec des arguments de type différents de ceux qui ont été fournis lorsque la classe a été instanciée, envisagez de fournir un autre identificateur pour le paramètre de type de la méthode, comme indiqué dans `GenericList2<T>` dans l'exemple suivant.  
  
 [!CODE [csProgGuideGenerics#26](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#26)]  
  
 Utilisez des contraintes pour activer des opérations plus spécialisées sur les paramètres de type dans les méthodes.  Cette version de `Swap<T>`, maintenant nommée `SwapIfGreater<T>`, peut s'utiliser uniquement avec des arguments de type qui implémentent <xref:System.IComparable%601>.  
  
 [!CODE [csProgGuideGenerics#27](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#27)]  
  
 Les méthodes génériques peuvent être surchargées sur plusieurs paramètres de type.  Par exemple, toutes les méthodes suivantes peuvent être situées dans la même classe :  
  
 [!CODE [csProgGuideGenerics#28](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#28)]  
  
## Spécification du langage C\#  
 Pour plus d'informations, consultez [Spécification du langage C\#](../../../csharp/language-reference/language-specification.md).  
  
## Voir aussi  
 <xref:System.Collections.Generic>   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Introduction aux génériques](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Méthodes](../../../csharp/programming-guide/classes-and-structs/methods.md)