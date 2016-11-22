---
title: "My.Response Object | Microsoft Docs"
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
  - "My.MyWebExtension.Response"
  - "My.Response"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Response object"
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# My.Response Object
Obtient l'objet <xref:System.Web.HttpResponse> associé à <xref:System.Web.UI.Page>.  Cet objet vous permet d'envoyer des données de réponse HTTP à un client, et contient des informations sur cette réponse.  
  
## Notes  
 L'objet `My.Response` contient l'objet <xref:System.Web.HttpResponse> actuel associé à la page.  
  
 L'objet `My.Response` n'est disponible que pour les applications [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].  
  
## Exemple  
 L'exemple suivant obtient la collection d'en\-têtes de l'objet `My.Request` et utilise l'objet `My.Response` pour l'écrire dans la page ASP.NET.  
  
 [!CODE [VbVbalrMyWeb#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyWeb#1)]  
  
## Voir aussi  
 <xref:System.Web.HttpResponse>   
 [My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)