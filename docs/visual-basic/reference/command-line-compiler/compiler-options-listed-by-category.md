---
title: "Visual Basic Compiler Options Listed by Category | Microsoft Docs"
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
  - "Visual Basic compiler, options"
ms.assetid: fbe36f7a-7cfa-4f77-a8d4-2be5958568e3
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Visual Basic Compiler Options Listed by Category
Le compilateur de ligne de commande [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] est fourni comme alternative aux programmes de compilation issus de l'environnement de développement intégré \(IDE\) [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  Voici la liste des options du compilateur de ligne de commande [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] triées par catégorie fonctionnelle.  
  
## Résultats de la compilation  
  
|||  
|-|-|  
|Option|Objectif|  
|[\/nologo](../../../visual-basic/reference/command-line-compiler/nologo.md)|Supprime les informations de bannière du compilateur.|  
|[\/utf8output](../../../visual-basic/reference/command-line-compiler/utf8output.md)|Affiche les résultats de la compilation au format d'encodage UTF\-8.|  
|[\/verbose](../../../visual-basic/reference/command-line-compiler/verbose.md)|Génère des informations supplémentaires lors de la compilation.|  
|`/modulename:<string>`|Spécifiez le nom du module source.|  
|[\/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Spécifiez un langage pour les résultats de la compilation.|  
  
## Optimisation  
  
|||  
|-|-|  
|Option|Objectif|  
|[\/filealign](../../../visual-basic/reference/command-line-compiler/filealign.md)|Spécifie où les sections du fichier de sortie doivent être alignées.|  
|[\/optimize](../../../visual-basic/reference/command-line-compiler/optimize.md)|Active\/désactive les optimisations.|  
  
## Fichiers de sortie  
  
|||  
|-|-|  
|Option|Objectif|  
|[\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)|Traite les commentaires de documentation pour les diriger vers un fichier XML.|  
|[\/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)|Configure le compilateur pour cibler le [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].|  
|[\/out](../../../visual-basic/reference/command-line-compiler/out.md)|Spécifie un fichier de sortie.|  
|[\/target](../../../visual-basic/reference/command-line-compiler/target.md)|Spécifie le format de la sortie.|  
  
## Assemblys .NET  
  
|||  
|-|-|  
|Option|Objectif|  
|[\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)|Entraîne la mise à disposition par le compilateur de toutes les informations de type à partir du ou des fichiers spécifiés, pour le projet en cours de compilation.|  
|[\/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)|Spécifie si l'assembly sera complètement ou partiellement signé.|  
|[\/imports](../../../visual-basic/reference/command-line-compiler/imports.md)|Importe un espace de noms à partir d'un assembly spécifié.|  
|[\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)|Spécifie un nom de conteneur de clé pour une paire de clés afin d'attribuer un nom fort à un assembly.|  
|[\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)|Spécifie un fichier contenant une clé ou une paire de clés afin d'attribuer un nom fort à un assembly.|  
|[\/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)|Spécifie l'emplacement des assemblys référencés par l'option [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md).|  
|[\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)|Importe des métadonnées à partir d'un assembly.|  
|[\/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)|Spécifie le nom de l'assembly dont un module fera partie.|  
|`/analyzer`|Exécutez les analyseurs à partir de cet assembly \(forme abrégée : \/a\).|  
|`/additionalfile`|Nomme des fichiers supplémentaires qui n'affectent pas directement la génération de code, mais peuvent être utilisés par des analyseurs pour produire des erreurs ou des avertissements.|  
  
## Débogage\/vérification des erreurs  
  
|||  
|-|-|  
|Option|Objectif|  
|[\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)|Crée un fichier qui contient des informations qui facilitent le signalement d'un bogue.|  
|[\/debug](../../../visual-basic/reference/command-line-compiler/debug.md)|Génère des informations de débogage.|  
|[\/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)|Supprime la capacité du compilateur à générer des avertissements.|  
|[\/quiet](../../../visual-basic/reference/command-line-compiler/quiet.md)|Empêche le compilateur d'afficher le code pour les erreurs et les avertissements liés à la syntaxe.|  
|[\/removeintchecks](../../../visual-basic/reference/command-line-compiler/removeintchecks.md)|Désactive les contrôles de dépassement sur les entiers.|  
|[\/warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)|Transforme les avertissements en erreurs.|  
|`/ruleset:<file>`|Spécifiez un fichier ruleset qui désactive des diagnostics spécifiques.|  
  
## Aide  
  
|||  
|-|-|  
|Option|Objectif|  
|[\/?](../../../visual-basic/reference/command-line-compiler/help.md)|Affiche les options du compilateur.  Cette commande est identique à l'option `/help`.  Aucune compilation n'a lieu.|  
|[\/help](../../../visual-basic/reference/command-line-compiler/help.md)|Affiche les options du compilateur.  Cette commande est identique à l'option `/?`.  Aucune compilation n'a lieu.|  
  
## Langage  
  
|||  
|-|-|  
|Option|Objectif|  
|[\/langversion](../../../visual-basic/reference/command-line-compiler/langversion.md)|Spécifiez la version de langage : 9&#124;9.0&#124;10&#124;10.0&#124;11&#124;11.0.|  
|[\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)|Applique la déclaration explicite des variables.|  
|[\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)|Applique une sémantique de type stricte.|  
|[\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)|Spécifie si les comparaisons de chaînes doivent être binaires ou utiliser une sémantique spécifique aux paramètres régionaux.|  
|[\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)|Permet l'utilisation de l'inférence de type de variable locale dans les déclarations de variable.|  
  
## Préprocesseur  
  
|||  
|-|-|  
|Option|Objectif|  
|[\/define](../../../visual-basic/reference/command-line-compiler/define.md)|Définit des symboles de compilation conditionnelle.|  
  
## Ressources  
  
|||  
|-|-|  
|Option|Objectif|  
|[\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)|Crée un lien à une ressource managée.|  
|[\/resource](../../../visual-basic/reference/command-line-compiler/resource.md)|Incorpore une ressource managée dans un assembly.|  
|[\/win32icon](../../../visual-basic/reference/command-line-compiler/win32icon.md)|Insère un fichier .ico dans le fichier de sortie.|  
|[\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)|Insère une ressource Win32 dans le fichier de sortie.|  
  
## Divers  
  
|||  
|-|-|  
|Option|Objectif|  
|[@ \(spécifier un fichier réponse\)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)|Spécifie un fichier réponse.|  
|[\/baseaddress](../../../visual-basic/reference/command-line-compiler/baseaddress.md)|Spécifie l'adresse de base d'une DLL.|  
|[\/codepage](../../../visual-basic/reference/command-line-compiler/codepage.md)|Spécifie la page de codes à utiliser pour tous les fichiers de code source inclus dans la compilation.|  
|[\/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)|Indique comment le compilateur [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] doit signaler les erreurs internes du compilateur.|  
|[\/highentropyva](../../../visual-basic/reference/command-line-compiler/highentropyva.md)|Indique au noyau Windows si un fichier exécutable particulier prend en charge la randomisation du format d'espace d'adresse \(ASLR\) de forte entropie.|  
|[\/main](../../../visual-basic/reference/command-line-compiler/main.md)|Spécifie la classe qui contient la procédure `Sub``Main` à utiliser au démarrage.|  
|[\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)|Ne compilez pas avec Vbc.rsp.|  
|[\/nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)|Configure le compilateur pour ne pas référencer les bibliothèques standard.|  
|[\/nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)|Indique au compilateur de ne pas incorporer de manifeste d'application dans le fichier exécutable.|  
|[\/platform](../../../visual-basic/reference/command-line-compiler/platform.md)|Spécifie la plateforme de processeur ciblée par le compilateur pour le fichier de sortie.|  
|[\/recurse](../../../visual-basic/reference/command-line-compiler/recurse.md)|Recherche des fichiers sources à compiler dans les sous\-répertoires.|  
|[\/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)|Spécifie un espace de noms pour toutes les déclarations de type.|  
|[\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)|Spécifie l'emplacement de Mscorlib.dll et de Microsoft.VisualBasic.dll.|  
|[\/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)|Spécifie que le compilateur doit compiler sans référence à la bibliothèque runtime Visual Basic, ou avec une référence à une bibliothèque runtime spécifique.|  
|[\/win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md)|Identifie un fichier manifeste d'application Win32 défini par l'utilisateur à incorporer dans le fichier exécutable portable \(PE\) d'un projet.|  
|`/parallel[+&#124;-]`|Indique s'il faut utiliser la build simultanée \(\+\).|  
|`/checksumalgorithm:<alg>`|Spécifiez l'algorithme de calcul de la somme de contrôle du fichier source stockée dans le fichier PDB.  Les valeurs prises en charge sont : SHA1 \(par défaut\) ou SHA256.|  
  
## Voir aussi  
 [Visual Basic Compiler Options Listed Alphabetically](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically.md)   
 [Introduction to the Project Designer](http://msdn.microsoft.com/fr-fr/898dd854-c98d-430c-ba1b-a913ce3c73d7)   
 [C\# Compiler Options Listed Alphabetically](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)   
 [C\# Compiler Options Listed by Category](../../../csharp/language-reference/compiler-options/listed-by-category.md)