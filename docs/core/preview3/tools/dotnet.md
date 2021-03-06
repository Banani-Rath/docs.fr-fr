---
title: Commande dotnet | SDK .NET Core
description: "En savoir plus sur la commande dotnet (le pilote générique des outils .NET Core CLI) et sur son utilisation."
keywords: dotnet, CLI, commandes CLI, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 93015521-2127-4fe9-8fce-ca79bcc4ff49
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: bbc13c8cca82e660f0f8ccf7d88c0340d9c06e68

---

#<a name="dotnet-command"></a>Commande dotnet

## <a name="name"></a>Nom

dotnet -- pilote générique pour l’exécution des commandes de l’interface de ligne de commande

## <a name="synopsis"></a>Résumé

`dotnet [--version] [--verbose] [--info] [command] [arguments] [--help]`

## <a name="description"></a>Description
`dotnet` est un pilote générique pour la chaîne d’outils de l’interface de ligne de commande (CLI). Appelé seul, il propose des instructions d’utilisation succinctes. 

Chaque fonctionnalité est implémentée comme une commande. Pour utiliser la fonctionnalité, la commande est spécifiée après `dotnet`, comme dans [`dotnet build`](dotnet-build.md). Tous les arguments qui suivent la commande sont ses arguments propres. 

Le seul cas où `dotnet` est utilisé comme une commande seule est lorsque des applications portables sont exécutées. Il suffit de spécifier une DLL d’application portable après le verbe `dotnet` pour exécuter l’application.    

## <a name="options"></a>Options

`-v|--verbose`

Active la sortie détaillée.

`--version`

Affiche la version des outils CLI.

`--info`

Affiche des informations plus détaillées sur les outils CLI, telles que le système d’exploitation actuel, le SHA de validation de la version, etc. 

`-h|--help`

Affiche une aide brève pour la commande. Si vous l’utilisez avec `dotnet` uniquement, il affiche également une liste des commandes disponibles.  

## <a name="dotnet-commands"></a>Commandes dotnet

Les commandes suivantes sont disponibles pour dotnet :

* [dotnet-new](dotnet-new.md)
   * Initialise un projet d’application console C# ou F#.
* [dotnet-restore](dotnet-restore.md)
  * Restaure les dépendances d’une application donnée. 
* [dotnet-build](dotnet-build.md)
  * Génère une application .NET Core.
* [dotnet-publish](dotnet-publish.md)
   * Publie une application .NET portable ou autonome.
* [dotnet-run](dotnet-run.md)
   * Exécute l’application à partir de la source.
* [dotnet-test](dotnet-test.md)
   * Exécute des tests à l’aide d’un Test Runner spécifié dans le project.json.
* [dotnet-pack](dotnet-pack.md)
   * Crée un package NuGet à partir de votre code.
* [dotnet-migrate](dotnet-migrate.md)
   * Migre un projet Preview 2 valide vers un projet Preview 3
* [dotnet-msbuild](dotnet-msbuild.md)
   * Fournit l’accès à la ligne de commande MSBuild

## <a name="examples"></a>Exemples

Initialisez un exemple d’application console .NET Core qui peut être compilé et exécuté :

`dotnet new`

Restaurez les dépendances d’une application donnée :

`dotnet restore`

Générez un projet et ses dépendances dans un répertoire donné : 

`dotnet build`

Exécutez une application portable nommée `myapp.dll` : `dotnet myapp.dll`

## <a name="environment"></a>Environnement 

`DOTNET_PACKAGES`

Cache du package principal. Si aucune valeur n’est définie, la valeur utilisée par défaut est $HOME/.nuget/packages pour Unix et %HOME%\NuGet\Packages pour Windows.

`DOTNET_SERVICING`

Spécifie l’emplacement de l’index de service que doit utiliser l’hôte partagé lors du chargement de l’exécution.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Spécifie si les données concernant l’utilisation des outils .NET Core doivent être collectées et envoyées à Microsoft. `true` pour ne pas adhérer à la fonctionnalité de télémétrie (valeurs : True, 1 ou Oui) ; sinon, `false` (valeurs : False, 0 ou Non). Si aucune valeur n’est définie, la valeur utilisée par défaut est `false`, c’est-à-dire que la fonctionnalité de télémétrie est activée.




<!--HONumber=Nov16_HO3-->


