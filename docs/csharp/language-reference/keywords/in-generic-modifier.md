---
title: "in (modificateur g&#233;n&#233;rique) (R&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "contravariance, in (mot clé C#)"
  - "in (mot clé C#)"
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# in (modificateur g&#233;n&#233;rique) (R&#233;f&#233;rence C#)
Pour les paramètres de type générique, le mot clé `in` spécifie que le paramètre de type est contravariant.  Vous pouvez utiliser le mot clé `in` dans les interfaces et les délégués génériques.  
  
 La contravariance vous permet d'utiliser un type moins dérivé que celui spécifié par le paramètre générique.  Cela permet la conversion implicite des classes qui implémentent des interfaces variantes et la conversion implicite des types délégués.  La covariance et contravariance dans les paramètres de type générique sont prises en charge pour les types référence, mais elles ne sont pas prises en charge pour les types valeur.  
  
 Un type peut être déclaré contravariant dans une interface ou un délégué générique s'il est utilisé uniquement comme type d'arguments de méthode et non comme type de retour de méthode.  Les paramètres `Ref` et `out` ne peuvent pas être variants.  
  
 Une interface ayant un paramètre de type contravariant autorise ses méthodes à accepter des arguments de types moins dérivés que ceux spécifiés par le paramètre de type d'interface.  Par exemple, comme dans le .NET Framework 4, dans l'interface <xref:System.Collections.Generic.IComparer%601>, le type T est contravariant, vous pouvez assigner un objet de type `IComparer(Of Person)` à un objet de type `IComparer(Of Employee)` sans utiliser des méthodes de conversion spéciales si `Employee` hérite de  `Person`.  
  
 Un autre délégué du même type peut être assigné à un délégué contravariant, mais avec un paramètre de type générique moins dérivé.  
  
 Pour plus d'informations, consultez [Covariance et contravariance](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Exemple  
 L'exemple suivant indique comment déclarer, étendre et implémenter une interface générique contravariante.  Il montre également comment vous pouvez utiliser la conversion implicite pour les classes qui implémentent cette interface.  
  
 [!CODE [csVarianceKeywords#1](../CodeSnippet/VS_Snippets_VBCSharp/csvariancekeywords#1)]  
  
## Exemple  
 L'exemple suivant indique comment déclarer, instancier et appeler un délégué générique contravariant.  Il montre également comment vous pouvez convertir implicitement un type délégué.  
  
 [!CODE [csVarianceKeywords#2](../CodeSnippet/VS_Snippets_VBCSharp/csvariancekeywords#2)]  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)   
 [Covariance et contravariance](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [Modificateurs](../../../csharp/language-reference/keywords/modifiers.md)