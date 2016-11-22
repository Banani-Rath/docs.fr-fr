---
title: "const (r&#233;f&#233;rence C#) | Microsoft Docs"
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
  - "const_CSharpKeyword"
  - "const"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "const (mot clé C#)"
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# const (r&#233;f&#233;rence C#)
Vous utilisez le mot clé `const` pour déclarer un champ constant ou un élément local constant.  Les champs et les éléments locaux constants ne sont pas des variables et ne peuvent pas être modifiés.  Les constantes peuvent être des chiffres, des valeurs booléennes, des chaînes ou une référence null.  Ne créez pas une constante pour représenter des informations qui doivent être modifiées.  Par exemple, n'utilisez pas un champ constant pour stocker le prix d'un service, le numéro de version du produit ou le nom de la marque d'une société.  Ces valeurs peuvent changer dans le temps, et dans la mesure où les compilateurs propagent les constantes, le code compilé avec vos bibliothèques devra être recompilé pour refléter ces modifications.  Voir également le mot clé [readonly](../../../csharp/language-reference/keywords/readonly.md).  Par exemple :  
  
```  
  
      const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## Notes  
 Le type d'une déclaration constante indique le type des membres introduit par la déclaration.  L'initialiseur d'un élément local constant ou d'un champ constant doit être une expression constante qui peut être implicitement convertie en type cible.  
  
 Une expression constante est une expression qui peut être complètement évaluée au moment de la compilation.  C'est pourquoi, les seules valeurs possibles pour les constantes des types référence sont `string` et une référence null.  
  
 La déclaration constante peut déclarer plusieurs constantes, notamment :  
  
```  
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 Le modificateur `static` n'est pas autorisé dans une déclaration constante.  
  
 Une constante peut être utilisée dans une expression constante, comme suit :  
  
```  
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  Le mot clé [readonly](../../../csharp/language-reference/keywords/readonly.md) est différent du mot clé `const`.  Un champ `const` ne peut être initialisé qu'au moment de la déclaration du champ.  Un champ `readonly` peut être initialisé dans la déclaration ou dans un constructeur.  C'est pourquoi, les champs `readonly` peuvent avoir des valeurs différentes en fonction du constructeur utilisé.  De même, bien qu'un champ `const` soit une constante au moment de la compilation, le champ `readonly` peut être utilisé pour des constantes au moment de l'exécution, comme ci\-après : `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`  
  
## Exemple  
 [!CODE [csrefKeywordsModifiers#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#5)]  
  
## Exemple  
 Cet exemple montre comment utiliser des constantes en tant que variables locales.  
  
 [!CODE [csrefKeywordsModifiers#6](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#6)]  
  
## Spécification du langage C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Voir aussi  
 [Référence C\#](../../../csharp/language-reference/index.md)   
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Mots clés C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificateurs](../../../csharp/language-reference/keywords/modifiers.md)   
 [readonly](../../../csharp/language-reference/keywords/readonly.md)