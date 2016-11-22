---
title: "String Basics in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "strings [Visual Basic], Like operator"
  - "strings [Visual Basic], Visual Basic"
  - "strings [Visual Basic], regular expressions"
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# String Basics in Visual Basic
Le type de données `String` représente une série de caractères \(chacun représentant à son tour une instance du type de données `Char`\).  Cette rubrique présente les concepts de base des chaînes en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## Variables de chaîne  
 Il est possible d'assigner à une instance de chaîne une valeur littérale représentant une série de caractères.  Exemple :  
  
 [!CODE [VbVbalrStrings#63](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#63)]  
  
 Une variable `String` peut également accepter une expression quelconque qui prend la valeur d'une chaîne.  En voici quelques exemples :  
  
 [!CODE [VbVbalrStrings#64](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#64)]  
  
 Tout littéral assigné à une variable `String` doit être placé entre guillemets \(""\).  Cela signifie que des guillemets dans une chaîne ne peuvent pas être représentés par des guillemets.  Par exemple, le code suivant génère une erreur du compilateur :  
  
 [!CODE [VbVbalrStrings#65](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#65)]  
  
 Ce code entraîne une erreur car le compilateur arrête la chaîne après les deuxièmes guillemets, et le reste de la chaîne est interprété comme du code.  Pour résoudre ce problème, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] interprète deux guillemets dans un littéral de chaîne comme des guillemets simples dans la chaîne.  L'exemple suivant illustre comment inclure correctement des guillemets dans une chaîne :  
  
 [!CODE [VbVbalrStrings#66](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#66)]  
  
 Dans l'exemple précédent, les deux guillemets qui précèdent le mot `Look` deviennent des guillemets simples dans la chaîne.  Les trois guillemets à la fin de la ligne correspondent aux guillemets simples dans la chaîne et au caractère de fin de chaîne.  
  
 Les littéraux de chaîne peuvent contenir plusieurs lignes :  
  
```vb  
Dim x = "hello  
world"  
  
```  
  
 La chaîne obtenue contient les séquences de saut de ligne que vous utilisiez dans votre littéral de chaîne \(vbcr, vbcrlf, etc.\).  Vous n'avez plus besoin d'utiliser l'ancienne solution de contournement :  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
  
```  
  
## Caractères dans des chaînes  
 Une chaîne peut être considérée comme une série de valeurs `Char` et le type `String` possède des fonctions intégrées qui vous permettent d'exécuter de nombreuses manipulations sur une chaîne qui ressemblent aux manipulations autorisées par les tableaux.  Comme tous les tableaux dans le [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], ce sont des tableaux de base zéro.  Vous pouvez vous référer à un caractère spécifique dans une chaîne via la propriété `Chars`, ce qui permet d'accéder à un caractère à la position où il apparaît dans la chaîne.  Exemple :  
  
 [!CODE [VbVbalrStrings#67](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#67)]  
  
 Dans l'exemple ci\-dessus, la propriété `Chars` de la chaîne retourne le quatrième caractère de la chaîne, qui est `D`, et l'assigne à `myChar`.  Vous pouvez également obtenir la longueur d'une chaîne particulière via la propriété `Length`.  Si vous devez exécuter plusieurs manipulations de type tableau sur une chaîne, vous pouvez la convertir en tableau d'instances `Char` à l'aide de la fonction `ToCharArray` de la chaîne.  Exemple :  
  
 [!CODE [VbVbalrStrings#68](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#68)]  
  
 La variable `myArray` contient à présent un tableau de valeurs `Char`, dont chacune représente un caractère issu de `myString`.  
  
## Immuabilité des chaînes  
 Une chaîne est *immuable*, ce qui signifie que sa valeur ne peut pas être modifiée une fois qu'elle a été créée.  Toutefois, cela ne vous empêche pas d'assigner plusieurs valeurs à une variable de chaîne.  Prenons l'exemple suivant :  
  
 [!CODE [VbVbalrStrings#69](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#69)]  
  
 Ici, une variable de chaîne est créée, une valeur lui est attribuée, puis sa valeur est modifiée.  
  
 Plus spécifiquement, dans la première ligne, une instance de type `String` est créée et la valeur `This string is immutable` lui est attribuée.  Dans la seconde ligne de l'exemple, une nouvelle instance est créée et la valeur `Or is it?` lui est attribuée. La variable de chaîne ignore sa référence à la première instance et stocke une référence à la nouvelle instance.  
  
 Contrairement à d'autres types de données intrinsèques, `String` est un type référence.  Quand une variable de type référence est passée en tant qu'argument à une fonction ou à une sous\-routine, une référence à l'adresse mémoire où sont stockées les données est passée à la place de la valeur réelle de la chaîne.  Ainsi, dans l'exemple précédent, le nom de la variable reste le même, mais il pointe vers une instance nouvelle et différente de la classe `String`, qui contient la nouvelle valeur.  
  
## Voir aussi  
 [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Opérations de chaînes de base](../Topic/Basic%20String%20Operations%20in%20the%20.NET%20Framework.md)