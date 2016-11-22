---
title: "Tableau des valeurs par d&#233;faut (informations de r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "constructeurs [C#], valeurs de retour"
  - "mots clés [C#], nouveau"
  - "constructeur par défaut [C#]"
  - "valeurs par défaut [C#]"
  - "types de valeur [C#], initialisation"
  - "variables [C#], types de valeur"
  - "constructeurs [C#], constructeur par défaut"
  - "types [C#], valeurs de retour du constructeur par défaut"
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Tableau des valeurs par d&#233;faut (informations de r&#233;f&#233;rence C#)
Le tableau suivant indique les valeurs par défaut de types valeur qui sont retournées par les constructeurs par défaut.  Les constructeurs par défaut sont appelés au moyen de l'opérateur `new`, comme suit :  
  
```  
int myInt = new int();  
```  
  
 L'instruction qui précède produit le même résultat que la suivante :  
  
```  
int myInt = 0;  
```  
  
 Pour rappel, il n'est pas possible d'utiliser en C\# des variables qui n'ont pas été initialisées.  
  
|Type valeur|Valeur par défaut|  
|-----------------|-----------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`false`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|0|  
|[char](../../../csharp/language-reference/keywords/char.md)|'\\0'|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|0.0M|  
|[double](../../../csharp/language-reference/keywords/double.md)|0.0D|  
|[enum](../../../csharp/language-reference/keywords/enum.md)|Valeur retournée par l'expression \(E\)0, où E est l'identificateur de l'élément enum.|  
|[float](../../../csharp/language-reference/keywords/float.md)|0.0F|  
|[int](../../../csharp/language-reference/keywords/int.md)|0|  
|[long](../../../csharp/language-reference/keywords/long.md)|0L|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|0|  
|[short](../../../csharp/language-reference/keywords/short.md)|0|  
|[struct](../../../csharp/language-reference/keywords/struct.md)|Valeur retournée après avoir défini tous les champs de type valeur à leur valeur par défaut et tous les champs de type référence à la valeur `null`.|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|0|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|0|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|0|  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Tableau des types valeur](../../../csharp/language-reference/keywords/value-types-table.md)   
 [Types valeur](../../../csharp/language-reference/keywords/value-types.md)   
 [Tableau des types intégrés](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tableaux de référence des types](../../../csharp/language-reference/keywords/reference-tables-for-types.md)