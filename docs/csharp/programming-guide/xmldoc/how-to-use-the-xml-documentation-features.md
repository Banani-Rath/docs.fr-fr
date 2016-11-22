---
title: "Comment&#160;: utiliser les fonctionnalit&#233;s de la documentation XML (Guide de programmation C#) | Microsoft Docs"
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
  - "langage C#, fonctionnalités de documentation XML"
  - "documentation XML (C#)"
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Comment&#160;: utiliser les fonctionnalit&#233;s de la documentation XML (Guide de programmation C#)
L'exemple suivant fournit une introduction de base d'un type qui a été documenté.  
  
## Exemple  
 [!CODE [csProgGuideDocComments#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDocComments#15)]  
  
  **\/\/Ce fichier .xml a été généré avec l'exemple de code précédent.  \<?xml version\="1.0"?\>**  
**\<doc\>**  
 **\<assembly\>**  
 **\<name\> xmlsample\<\/name\>**  
 **\<\/assembly\>**  
 **\<members\>**  
 **\<member name\="T:SomeClass"\>**   
 **\<summary\>**  
 **Emplacement des informations de résumé de la classe.\<\/summary\>**  
 **\<remarks\>**  
 **Des commentaires plus longs peuvent être associés à un type ou un membre**   
 **via les notes tag\<\/remarks\>**  
 **\<\/member\>**  
 **\<member name\="F:SomeClass.m\_Name"\>**   
 **\<summary\>**  
 **Le magasin pour le nom property\<\/summary\>**  
 **\<\/member\>**  
 **\<member name\="M:SomeClass.\#ctor"\>**   
 **\<summary\> la classe constructor.\<\/summary\>**   
 **\<\/member\>**  
 **\<member name\="M:SomeClass.SomeMethod\(System.String\)"\>**   
 **\<summary\>**  
 **Description de SomeMethod.\<\/summary\>**  
 **\<param name\="s"\> La description du paramètre de s disparaît here\<\/param\>**  
 **\<seealso cref\="T:System.String"\>**  
 **Vous pouvez utiliser l'attribut cref sur n'importe quelle balise pour faire référence à un type ou un membre**   
 **et le compilateur vérifiera que cette référence existe.  \<\/seealso\>**  
 **\<\/member\>**  
 **\<member name\="M:SomeClass.SomeOtherMethod"\>**   
 **\<summary\>**  
 **Une autre méthode.  \<\/summary\>**  
 **\<returns\>**  
 **Les résultats retournés sont décrits grâce à la balise returns.\<\/returns\>**  
 **\<seealso cref\="M:SomeClass.SomeMethod\(System.String\)"\>**   
 **Notez l'utilisation de l'attribut cref pour faire référence à une méthode spécifique \<\/seealso\>**  
 **\<\/member\>**  
 **\<member name\="M:SomeClass.Main\(System.String\[\]\)"\>**   
 **\<summary\>**  
 **Point d'entrée de l'application.  \<\/summary\>**  
 **\<param name\="args"\> une liste de la ligne de commande arguments\<\/param\>**  
 **\<\/member\>**  
 **\<member name\="P:SomeClass.Name"\>**   
 **\<summary\>**  
 **propriété Name \<\/summary\>**  
 **\<value\>**  
 **Un indicateur de valeur est utilisée pour décrire la propriété value\<\/value\>**  
 **\<\/member\>**  
 **\<\/members\>**  
**\<\/doc\>**    
## Compilation du code  
 pour compiler l'exemple, tapez la ligne de commande suivante :  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 Cette commande crée le fichier XML XMLsample.xml, que vous pouvez afficher dans votre navigateur ou à l'aide de la commande de TYPE.  
  
## Programmation fiable  
 La documentation XML commence par \/\/\/.  Lorsque vous créez un projet, les assistants sont des lignes de \/\/\/de départ pour vous.  Le traitement de ces commentaires s'accompagne de certaines restrictions :  
  
-   Le XML utilisé dans la documentation doit être correct.  Si le XML n'est pas correct, un avertissement est généré et le fichier de documentation contient un commentaire indiquant qu'une erreur est survenue.  
  
-   Les développeurs sont libres de créer leur propre jeu de balises.  Il existe un jeu de balises recommandé \(consultez la section plus de lecture\).  Certaines des balises recommandées ont des significations spéciales :  
  
    -   La balise \<param\> est employée pour décrire les paramètres.  Si elle est utilisée, le compilateur vérifiera que le paramètre existe et que tous les paramètres sont décrits dans la documentation.  Si la vérification échoue, le compilateur émet un avertissement.  
  
    -   L'attribut `cref` peut être rattaché à n'importe quelle balise pour fournir une référence à un élément de code.  Le compilateur vérifiera que cet élément de code.  Si la vérification échoue, le compilateur émet un avertissement.  Le compilateur respecte les instructions `using` lorsqu'il recherche un type décrit dans l'attribut `cref`.  
  
    -   La balise \<summary\> est employée par IntelliSense dans Visual Studio pour afficher d'autres informations sur un type ou un membre.  
  
        > [!NOTE]
        >  Le fichier XML ne fournit pas d'informations complètes sur le type et des membres \(par exemple, il ne contient aucune information de type\).  Pour obtenir des informations complètes sur un type ou un membre, vous devez utiliser le fichier de documentation avec la réflexion sur le type ou le membre réel.  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Commentaires de documentation XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)