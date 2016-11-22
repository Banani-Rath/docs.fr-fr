---
title: "Lecture et &#233;criture dans le Registre &#224; l&#39;aide de l&#39;espace de noms Microsoft.Win32 (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
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
  - "registre, Visual Basic"
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Lecture et &#233;criture dans le Registre &#224; l&#39;aide de l&#39;espace de noms Microsoft.Win32 (Visual Basic)
Bien que `My.Computer.Registry` doive normalement couvrir vos besoins de base quand vous programmez le Registre, vous pouvez également utiliser les classes <xref:Microsoft.Win32.Registry> et <xref:Microsoft.Win32.RegistryKey> dans l’espace de noms <xref:Microsoft.Win32> du [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
## Clés dans la classe de Registre  
 La classe <xref:Microsoft.Win32.Registry> fournit les clés de Registre de base qui peuvent être utilisées pour accéder aux sous\-clés et à leurs valeurs. Les clés de base proprement dites sont en lecture seule. Le tableau suivant répertorie et décrit les sept clés exposées par la classe <xref:Microsoft.Win32.Registry>.  
  
|**Clé**|**Description**|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|Définit les types de documents et les propriétés associées à ces types.|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|Contient des informations sur la configuration matérielle qui ne sont pas propres à l’utilisateur.|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|Contient des informations sur les préférences de l’utilisateur actuel, telles que les variables d’environnement.|  
|<xref:Microsoft.Win32.Registry.DynData>|Contient des données de Registre dynamiques, telles que celles utilisées par les pilotes de périphériques virtuels.|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|Contient cinq sous\-clés \(Hardware, SAM, Security, Software et System\) qui contiennent les données de configuration de l’ordinateur local.|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|Contient des informations sur les performances des composants logiciels.|  
|<xref:Microsoft.Win32.Registry.Users>|Contient des informations sur les préférences de l’utilisateur par défaut.|  
  
> [!IMPORTANT]
>  Il est plus sûr d’écrire des données dans l’utilisateur actuel \(<xref:Microsoft.Win32.Registry.CurrentUser>\) que dans l’ordinateur local \(<xref:Microsoft.Win32.Registry.LocalMachine>\). Une condition généralement appelée « usurpation » se produit quand la clé que vous créez a été créée précédemment par un autre processus, potentiellement malveillant. Pour éviter ce problème, utilisez une méthode, telle que <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, qui retourne `Nothing` si la clé n’existe pas encore.  
  
## Lecture d’une valeur à partir du Registre  
 Le code suivant montre comment lire une chaîne à partir de HKEY\_CURRENT\_USER.  
  
 [!CODE [VbResourceTasks#20](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#20)]  
  
 Le code suivant lit, incrémente puis écrit une chaîne dans HKEY\_CURRENT\_USER.  
  
 [!CODE [VbResourceTasks#21](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#21)]  
  
## Voir aussi  
 <xref:System.SystemException>   
 <xref:System.ApplicationException>   
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)   
 [Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)