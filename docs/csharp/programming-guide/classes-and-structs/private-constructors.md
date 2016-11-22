---
title: "Constructeurs priv&#233;s (guide de programmation C#) | Microsoft Docs"
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
  - "langage C#, constructeurs privés"
  - "constructeurs privés (C#)"
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Constructeurs priv&#233;s (guide de programmation C#)
Un constructeur privé est une instance spéciale de constructeur.  Un tel constructeur est généralement utilisé dans les classes qui contiennent uniquement des membres statiques.  Si une classe possède un ou plusieurs constructeurs privés et aucun constructeur public, les autres classes \(à l'exception des classes imbriquées\) ne peuvent pas créer des instances de cette classe.  Par exemple :  
  
 [!CODE [csProgGuideObjects#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#11)]  
  
 La déclaration du constructeur vide empêche la génération automatique d'un constructeur par défaut.  Notez que si vous n'utilisez pas un modificateur d'accès avec le constructeur, ce dernier sera néanmoins privé par défaut.  Toutefois, le modificateur [private](../../../csharp/language-reference/keywords/private.md) est habituellement utilisé explicitement pour qu'il soit clair que la classe ne peut pas être instanciée.  
  
 Les constructeurs privés sont utilisés pour empêcher la création d'instances d'une classe lorsqu'il n'existe pas de champ d'instance ou de méthode, telle que la classe <xref:System.Math>, ou lorsqu'une méthode est appelée pour obtenir une instance d'une classe.  Si toutes les méthodes dans la classe sont statiques, envisagez de rendre la classe entière statique.  Pour plus d'informations, consultez [Classes statiques et membres de classe statique](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## Exemple  
 Exemple de classe qui utilise un constructeur privé :  
  
 [!CODE [csProgGuideObjects#12](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#12)]  
  
 Notez que si vous supprimez les marques de commentaire de l'instruction suivante tirée de l'exemple, une erreur est générée, car le constructeur est alors inaccessible à cause de son niveau de protection :  
  
 [!CODE [csProgGuideObjects#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#13)]  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Classes et structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Constructeurs](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Destructeurs](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [privées](../../../csharp/language-reference/keywords/private.md)   
 [public](../../../csharp/language-reference/keywords/public.md)