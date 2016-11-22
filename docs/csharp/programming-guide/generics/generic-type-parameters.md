---
title: "Param&#232;tres de type g&#233;n&#233;rique (guide de programmation C#) | Microsoft Docs"
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
  - "génériques (C#), paramètres de type"
  - "paramètres de type (C#)"
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Param&#232;tres de type g&#233;n&#233;rique (guide de programmation C#)
Dans un type ou une méthode générique, les paramètres de type représentent un espace réservé pour un type spécifique qu'un client spécifie quand il instancie une variable du type générique.  Une classe générique, telle que `GenericList<T>` répertoriée dans [Introduction aux génériques](../../../csharp/programming-guide/generics/introduction-to-generics.md), ne peut pas être utilisée en l'état car il ne s'agit pas vraiment d'un type ; c'est plus comme un plan pour un type.  Pour utiliser `GenericList<T>`, le code client doit déclarer et instancier un type construit en spécifiant un argument de type à l'intérieur de crochets.  L'argument de type pour cette classe particulière peut être tout type reconnu par le compilateur.  Il est possible de créer un nombre quelconque d'instances de type construit, chacun à l'aide d'un argument de type différent, comme suit :  
  
 [!CODE [csProgGuideGenerics#7](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#7)]  
  
 Dans chacun de ces instances de `GenericList<T>`, chaque occurrence de `T` dans la classe sera substituée au moment de l'exécution avec l'argument de type.  Par cette substitution, nous avons créé trois objets distincts de type sécurisé et efficaces à l'aide d'une seule définition de classe.  Pour plus d'informations sur la façon dont cette substitution est exécutée par le CLR, consultez [Génériques dans le runtime](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## Indications concernant l'attribution d'un nom aux paramètres de type  
  
-   **Nommez** les paramètres de type générique avec des noms descriptifs, sauf si un nom composé d'une seule lettre est explicite et un nom descriptif n'ajouterait pas de valeur.  
  
     [!CODE [csProgGuideGenerics#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#8)]  
  
-   **Envisagez** l'utilisation de T comme nom de paramètre de type pour les types ayant un paramètre de type d'une seule lettre.  
  
     [!CODE [csProgGuideGenerics#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#9)]  
  
-   **Préfixez** les noms des paramètres de type descriptifs avec « T ».  
  
     [!CODE [csProgGuideGenerics#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#10)]  
  
-   **Pensez** à indiquer les contraintes placées sur un paramètre de type dans le nom de paramètre.  Par exemple, un paramètre contraint à `ISession` peut être appelé `TSession`.  
  
## Voir aussi  
 <xref:System.Collections.Generic>   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Génériques](../../../csharp/programming-guide/generics/index.md)   
 [Différences entre les templates C\+\+ et les génériques C\#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)