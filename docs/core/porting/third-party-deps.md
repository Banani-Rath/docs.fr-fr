---
title: "Portage sur .NET Core - Analyse de vos dépendances tierces"
description: "Portage sur .NET Core - Analyse de vos dépendances tierces"
keywords: .NET, .NET Core
author: cartermp
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
translationtype: Human Translation
ms.sourcegitcommit: 46061efa8e33c6a73befa5181eb33b8deb2fa637
ms.openlocfilehash: 7e4e96183484d102d102eeab97191f8be9b9be8a

---

# <a name="porting-to-net-core-analyzing-your-thirdparty-party-dependencies"></a>Portage sur .NET Core - Analyse de vos dépendances tierces

La première étape du processus de portage est de comprendre vos dépendances tierces.  Vous devez déterminer ceux d’entre eux (s’il y en a) qui ne s’exécutent pas encore sur .NET Core et développer un plan d’urgence pour ceux qui ne s’exécutent pas sur .NET Core.

## <a name="prerequisites"></a>Prérequis

Cet article suppose que vous utilisez Windows et Visual Studio, et que vous disposez d’un code qui s’exécute aujourd’hui sur le .NET Framework.

## <a name="analyzing-nuget-packages"></a>Analyse des packages NuGet

L’analyse des packages NuGet pour la portabilité est très facile.  Un package NuGet étant lui-même un ensemble de dossiers qui contiennent des assemblys spécifiques à une plateforme, il vous suffit de vérifier s’il existe un dossier qui contient un assembly .NET Core.

L’examen des dossiers d’un package NuGet est plus facile avec l’outil [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).  Voici comment faire.

1. Téléchargez et ouvrez NuGet Package Explorer.
2. Cliquez sur « Open package from online feed ».
3. Recherchez le nom du package.
4. Développez le dossier « lib » du côté droit et examinez les noms de dossier.

Vous pouvez également voir ce qu’un package prend en charge sur [nuget.org](https://www.nuget.org/) sous la section **Dependencies** de la page pour ce package.

Dans les deux cas, vous devez rechercher un dossier ou une entrée [nuget.org](https://www.nuget.org/) avec un des noms suivants :

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netcoreapp1.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

Voici les monikers du Framework cible qui correspondent aux versions de [la bibliothèque .NET Standard](../../standard/library.md) et les profils de bibliothèque de classes portable traditionnels qui sont compatibles avec .NET Core.  Notez que `netcoreapp1.0`, bien que compatible, est destiné aux applications et non pas aux bibliothèques.  Bien que ce ne soit pas un problème d’utiliser une bibliothèque basée sur `netcoreapp1.0`, il est possible que cette bibliothèque ne soit pas destinée à *autre chose* qu’à la consommation par d’autres applications `netcoreapp1.0`.

Il existe également certains monikers du Framework cible hérités utilisés dans des préversions de .NET Core qui peuvent également être compatibles :

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

**Bien que ceux-ci puissent probablement fonctionner avec votre code, il n’existe aucune garantie de compatibilité**.  Les packages avec ces monikers du Framework cible ont été créés avec des packages .NET Core en préversion.  Notez quand (ou si) des packages comme ceci sont mis à jour pour être basés sur `netstandard`.

> [!NOTE]
> Pour utiliser un package ciblant une bibliothèque de classes portable traditionnelle ou une cible de .NET Core en préversion, vous devez utiliser la directive `imports` dans votre fichier `project.json`.

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a>Ce qu’il faut faire quand votre dépendance de package NuGet ne s’exécute pas sur .NET Core

Voici quelques actions possibles si un package NuGet dont vous dépendez ne s’exécute pas sur .NET Core.

1. Si le projet est open source et hébergé à un endroit comme GitHub, vous pouvez demander aux développeurs de le modifier.
2. Vous pouvez contacter l’auteur directement sur [nuget.org](https://www.nuget.org/) en recherchant le package et en cliquant sur « Contact Owners » sur le côté gauche de la page du package.
3. Vous pouvez rechercher un autre package qui s’exécute sur .NET Core et qui réalise la même tâche que le package que vous utilisez.
4. Vous pouvez essayer d’écrire vous-même le code qui était exécuté par le package.
5. Vous pouvez éliminer la dépendance du package en modifiant les fonctionnalités de votre application, au moins jusqu’à ce qu’une version compatible du package soit disponible.

N’oubliez pas que les personnes qui maintiennent les projets open source et celles qui publient des packages NuGet sont souvent des bénévoles qui apportent leur contribution car elles s’intéressent à un domaine donné, le font gratuitement et ont souvent un autre travail au quotidien. Si vous les contactez, il peut être convenable d’émettre d’abord un avis positif sur la bibliothèque avant de parler d’une prise en charge de .NET Core.

Si vous ne parvenez pas à résoudre votre problème via une des actions ci-dessus, il peut être nécessaire de porter sur .NET Core à une date ultérieure.

L’équipe .NET aimerait savoir quelles sont les prochaines bibliothèques les plus importantes à prendre en charge avec .NET Core. Vous pouvez également nous envoyer un e-mail à l’adresse dotnet@microsoft.com sur les bibliothèques que vous voudriez utiliser.

## <a name="analyzing-dependencies-which-arent-nuget-packages"></a>Analyse des dépendances qui ne sont pas des packages NuGet

Vous pouvez avoir une dépendance qui n’est pas un package NuGet, comme une DLL dans le système de fichiers.  La seule façon de déterminer la portabilité de cette dépendance est d’exécuter l’[outil ApiPort](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).

## <a name="next-steps"></a>Étapes suivantes

Si vous portez une bibliothèque, consultez [Portage de vos bibliothèques](libraries.md).



<!--HONumber=Nov16_HO3-->


