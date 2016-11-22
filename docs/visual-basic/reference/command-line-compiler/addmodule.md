---
title: "/addmodule | Microsoft Docs"
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
  - "/addmodule compiler option [Visual Basic]"
  - "addmodule compiler option [Visual Basic]"
  - "-addmodule compiler option [Visual Basic]"
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# /addmodule
Entraîne le compilateur à donner des informations de type dans le ou les fichiers spécifiés disponibles pour le projet en cours de compilation.  
  
## Syntaxe  
  
```  
/addmodule:fileList  
```  
  
## Arguments  
 `fileList`  
 Obligatoire.  Liste de fichiers délimitée par des virgules qui contient des métadonnées, mais pas de manifestes des assemblys.  Les noms de fichiers contenant des espaces doivent être mis entre guillemets \(" "\).  
  
## Notes  
 Les fichiers répertoriés par le paramètre `fileList` doivent être créés à l'aide de l'option `/target:module` ou avec l'équivalent de `/target:module` d'un autre compilateur.  
  
 Tous les modules ajoutés par `/addmodule` doivent se trouver dans le même répertoire que le fichier de sortie au moment de l'exécution.  Vous pouvez donc spécifier un module dans n'importe quel répertoire au moment de la compilation, mais le module doit se trouver dans le répertoire de l'application au moment de l'exécution.  Si tel n'est pas le cas, une erreur <xref:System.TypeLoadException> se produit.  
  
 Si vous spécifiez \(implicitement ou explicitement\) une option [\/target](../../../visual-basic/reference/command-line-compiler/target.md) différente de `/target:module` avec `/addmodule`, les fichiers passés à `/addmodule` sont inclus dans l'assembly du projet.  Un assembly est requis pour exécuter un fichier de sortie contenant un ou plusieurs fichiers ajoutés avec `/addmodule`.  
  
 Utilisez [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md) pour importer les métadonnées à partir d'un fichier qui contient un assembly.  
  
> [!NOTE]
>  L'option `/addmodule` n'est pas disponible dans l'environnement de développement Visual Studio. Elle est disponible uniquement lors de la compilation à partir de la ligne de commande.  
  
## Exemple  
 Le code suivant crée un module.  
  
 [!CODE [VbVbalrCompiler#47](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCompiler#47)]  
  
 Le code suivant importe les types du module.  
  
 [!CODE [VbVbalrCompiler#48](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCompiler#48)]  
  
 Lorsque vous exécutez `t1`, la sortie correspond à `802`.  
  
## Voir aussi  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Exemples de lignes de commande de compilation](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)