---
title: "In (Generic Modifier) (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.VarianceIn"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "contravariance, In keyword [Visual Basic]"
  - "In keyword [Visual Basic]"
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# In (Generic Modifier) (Visual Basic)
Pour les paramètres de type générique, le mot clé `In` spécifie que le paramètre de type est contravariant.  
  
## Notes  
 La contravariance vous permet d'utiliser un type moins dérivé que celui spécifié par le paramètre générique.  Cela permet la conversion implicite des classes qui implémentent des interfaces variantes et la conversion implicite des types délégués.  
  
 Pour plus d'informations, consultez [Covariance et contravariance](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Règles  
 Vous pouvez utiliser le mot clé `In` dans les interfaces et les délégués génériques.  
  
 Un paramètre de type peut être déclaré contravariant dans une interface ou un délégué générique s'il est utilisé uniquement comme type d'arguments de méthode et non utilisé comme type de retour de méthode.  Les paramètres `ByRef` ne peuvent pas être covariants ou contravariants.  
  
 La covariance et la contravariance sont prises en charge pour les types référence mais pas pour les types valeur.  
  
 En Visual Basic, vous ne pouvez pas déclarer d'événements dans des interfaces contravariantes sans spécifier le type délégué.  De même, les interfaces contravariantes ne peuvent pas avoir de classes, d'enums ou de structures imbriqués, mais elles peuvent inclure des interfaces imbriquées.  
  
## Comportement  
 Une interface ayant un paramètre de type contravariant autorise ses méthodes à accepter des arguments de types moins dérivés que ceux spécifiés par le paramètre de type d'interface.  Par exemple, comme dans le .NET Framework 4, dans l'interface <xref:System.Collections.Generic.IComparer%601>, le type T est contravariant, vous pouvez assigner un objet de type `IComparer(Of Person)` à un objet de type `IComparer(Of Employee)` sans utiliser des méthodes de conversion spéciales si `Person` hérite de  `Employee`.  
  
 Un autre délégué du même type peut être assigné à un délégué contravariant, mais avec un paramètre de type générique moins dérivé.  
  
## Exemple  
 L'exemple suivant indique comment déclarer, étendre et implémenter une interface générique contravariante.  Il montre également comment vous pouvez utiliser la conversion implicite pour les classes qui implémentent cette interface.  
  
 [!CODE [vbVarianceKeywords#1](../CodeSnippet/VS_Snippets_VBCSharp/vbvariancekeywords#1)]  
  
## Exemple  
 L'exemple suivant indique comment déclarer, instancier et appeler un délégué générique contravariant.  Il montre également comment vous pouvez convertir implicitement un type délégué.  
  
 [!CODE [vbVarianceKeywords#2](../CodeSnippet/VS_Snippets_VBCSharp/vbvariancekeywords#2)]  
  
## Voir aussi  
 [Variance dans les interfaces génériques](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)