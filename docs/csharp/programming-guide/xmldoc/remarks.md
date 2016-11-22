---
title: "&lt;remarks&gt; (Guide de programmation&#160;C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<remarks> (balise XML C#)"
  - "remarks (balise XML C#)"
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
caps.latest.revision: 15
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;remarks&gt; (Guide de programmation&#160;C#)
## Syntaxe  
  
```  
<remarks>description</remarks>  
```  
  
#### Paramètres  
 `Description`  
 Description du membre.  
  
## Notes  
 La balise \<remarks\> permet d'ajouter des informations sur un type et de compléter les informations spécifiées par [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md).  Ces informations sont affichées dans [Object Browser Window](http://msdn.microsoft.com/fr-fr/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).  
  
 Compilez avec [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
 [!CODE [csProgGuideDocComments#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDocComments#9)]  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Balises recommandées pour les commentaires de documentation](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)