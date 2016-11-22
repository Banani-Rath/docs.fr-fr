---
title: "Friend assembly reference &lt;reference&gt; is invalid | Microsoft Docs"
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
  - "vbc31535"
  - "bc31535"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31535"
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Friend assembly reference &lt;reference&gt; is invalid
La référence d'assembly Friend \<référence\> n'est pas valide.Les assemblys signés avec un nom fort doivent spécifier une clé publique dans leurs déclarations InternalsVisibleTo.  
  
 Le nom de l'assembly passé au constructeur d'attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> identifie un assembly avec un nom fort, mais il n'inclut pas d'attribut `PublicKey`.  
  
 **ID d'erreur :** BC31535  
  
### Pour corriger cette erreur  
  
1.  Déterminez la clé publique pour l'assembly friend avec un nom fort.  Incluez la clé publique dans le nom de l'assembly passé au constructeur d'attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> à l'aide de l'attribut `PublicKey`.  
  
## Voir aussi  
 <xref:System.Reflection.AssemblyName>   
 [Assemblys friend](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Comment : créer des assemblys Friend signés](../Topic/How%20to:%20Create%20Signed%20Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)