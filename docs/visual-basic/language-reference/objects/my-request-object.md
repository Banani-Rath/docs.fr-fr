---
title: "My.Request Object | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.MyWebExtension.Request"
  - "My.Request"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Request object"
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# My.Request Object
Obtient l'objet <xref:System.Web.HttpRequest> pour la page demandée.  
  
## Notes  
 L'objet `My.Request` contient des informations sur la demande HTTP actuelle.  
  
 L'objet `My.Request` n'est disponible que pour les applications ASP.NET.  
  
## Exemple  
 L'exemple suivant obtient la collection d'en\-têtes de l'objet `My.Request` et utilise l'objet `My.Response` pour l'écrire dans la page ASP.NET.  
  
 [!CODE [VbVbalrMyWeb#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyWeb#1)]  
  
## Voir aussi  
 <xref:System.Web.HttpRequest>   
 [My.Response Object](../../../visual-basic/language-reference/objects/my-response-object.md)