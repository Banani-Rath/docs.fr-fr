---
title: "&lt;exception&gt; (guide de programmation C#) | Microsoft Docs"
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
  - "exception"
  - "<exception>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<exception> (balise XML C#)"
  - "exception (balise XML C#)"
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;exception&gt; (guide de programmation C#)
## Syntaxe  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Paramètres  
 cref \= "`member`"  
 Référence à une exception disponible dans l'environnement de compilation en cours.  Le compilateur vérifie que l'exception donnée existe et traduit `member` dans le nom d'élément canonique dans le code XML de sortie.  `member` doit apparaître dans des guillemets doubles \(" "\).  
  
 Pour plus d'informations sur la création d'une référence cref à un type générique, consultez [\<see\>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Description de l'exception.  
  
## Notes  
 La balise \<exception\> permet de spécifier les exceptions qui peuvent être levées.  Cette balise peut être appliquée aux définitions des méthodes, propriétés, événements et indexeurs.  
  
 Compilez avec [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
 Pour plus d'informations sur la gestion des exceptions, consultez [Exceptions et gestion des exceptions](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md).  
  
## Exemple  
 [!CODE [csProgGuideDocComments#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDocComments#4)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Balises recommandées pour les commentaires de documentation](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)