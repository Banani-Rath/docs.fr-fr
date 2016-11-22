---
title: "Comment&#160;: acc&#233;der &#224; un &#233;l&#233;ment de tableau &#224; l&#39;aide d&#39;un pointeur (Guide de programmation C#) | Microsoft Docs"
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
  - "pointeurs (C#), accès au tableau"
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: acc&#233;der &#224; un &#233;l&#233;ment de tableau &#224; l&#39;aide d&#39;un pointeur (Guide de programmation C#)
Dans un contexte unsafe, vous pouvez accéder à un élément en mémoire en utilisant l'accès à un élément de pointeur, comme illustré dans l'exemple suivant :  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 L'expression entre crochets peut être implicitement convertie en `int`, `uint`, `long` ou `ulong`.  L'opération p\[e\] équivaut à \*\(p\+e\).  Comme C et C\+\+, l'accès à un élément de pointeur ne vérifie pas les erreurs de dépassement des limites.  
  
## Exemple  
 Dans cet exemple, 123 emplacements de mémoire sont alloués à un tableau de caractères, `charPointer`.  Le tableau est utilisé pour afficher les lettres minuscules et les lettres majuscules dans deux boucles [for](../../../csharp/language-reference/keywords/for.md).  
  
 Remarquez que l'expression `charPointer[i]` équivaut à l'expression `*(charPointer + i)`, et vous pouvez obtenir le même résultat en utilisant l'une ou l'autre expression.  
  
 [!CODE [csProgGuidePointers#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#11)]  
  
 [!CODE [csProgGuidePointers#12](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#12)]  
  
  **Lettres majuscules :**  
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**  
**Lettres minuscules :**  
**abcdefghijklmnopqrstuvwxyz**   
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Expressions de pointeur](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Types pointeur](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Types](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed, instruction](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)