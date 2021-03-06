---
title: "Génération d’une solution .NET Core complète sur Windows à l’aide de Visual Studio 2017"
description: "Génération d’une solution .NET Core complète sur Windows à l’aide de Visual Studio 2017"
keywords: .NET, .NET Core
author: bleroy
manager: wpickett
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d743134a-08a3-4ff6-aab7-49f71f0568c3
translationtype: Human Translation
ms.sourcegitcommit: 07b62bd7163193eff8dc8f61fda7a45a924bba2b
ms.openlocfilehash: 9e65979d2f41e39e89109c2c5480acaebbef757f

---

# <a name="building-a-complete-net-core-solution-on-windows-using-visual-studio-2017"></a>Génération d’une solution .NET Core complète sur Windows à l’aide de Visual Studio 2017

par [Bertrand Le Roy](https://github.com/bleroy) et [Phillip Carter](https://github.com/cartermp)

Visual Studio 2017 fournit un environnement de développement complet pour le développement d’applications .NET Core. Les procédures décrites dans ce document expliquent comment créer une solution .NET Core classique qui inclut des bibliothèques réutilisables, des tests et utilise des bibliothèques tierces. 

## <a name="prerequisites"></a>Conditions préalables

Suivez les instructions stipulées dans [notre page de prérequis](../windows-prerequisites.md) pour mettre à jour votre environnement.

# <a name="a-solution-using-only-net-core-projects"></a>Une solution utilisant uniquement des projets .NET Core

## <a name="writing-the-library"></a>Écriture de la bibliothèque

1. Dans Visual Studio, choisissez **Fichier**, **Nouveau**, **Projet**. Dans la boîte de dialogue **Nouveau projet**, développez le nœud **Visual C#**, choisissez le nœud **.NET Core**, puis choisissez **Bibliothèque de classes (.NET Standard)**. 

2. Nommez le projet « Library » et la solution « Golden ». Laissez l’option **Créer le répertoire pour la solution** activée. Cliquez sur **OK**.

3. Dans l’Explorateur de solutions, ouvrez le menu contextuel du nœud **Dépendances**, puis choisissez **Gérer les packages NuGet**.

4. Choisissez « nuget.org » comme **Source de package**, puis choisissez l’onglet **Parcourir**. Recherchez **Newtonsoft.Json**. Cliquez sur **Installer** et acceptez le contrat de licence. Le package doit maintenant apparaître sous **Dependencies/NuGet** (Dépendances/NuGet) et être automatiquement restauré.

5. Renommer le fichier `Class1.cs` en `Thing.cs`. Acceptez le renommage de la classe. Ajouter une méthode : `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`

7. Dans le menu **Générer** , choisissez **Générer la solution**.

   La solution doit se générer sans erreur.

### <a name="writing-the-test-project"></a>Écriture du projet de test

1. Dans l’Explorateur de solutions, ouvrez le menu contextuel du nœud **Solution** et sélectionnez **Ajouter**, **Nouveau projet**. Dans la boîte de dialogue **Nouveau projet**, sous **Visual C#**, choisissez **Projet de test unitaire (.NET Core)**. Nommez-le « TestLibrary » et cliquez sur OK. 

2. Dans le projet **TestLibrary**, ouvrez le menu contextuel du nœud **Dépendances**, puis choisissez **Ajouter une référence**. Cliquez sur **Projets**, puis enregistrez le projet de bibliothèque et cliquez sur OK. Cette opération ajoute une référence à votre bibliothèque à partir du projet de test.

3. Renommez le fichier `UnitTest1.cs` en `LibraryTests.cs` et acceptez le changement de nom de classe. Ajoutez `using Library;` au début du fichier et remplacez la méthode `TestMethod1` par le code suivant :
    ```csharp
    [TestMethod]
    public void ThingGetsObjectValFromNumber()
    {
        Assert.AreEqual(42, new Thing().Get(42));
    }
    ```

   Vous devez maintenant être en mesure de générer la solution. 
   
4. Dans le menu **Test**, choisissez **Windows**, **Explorateur de tests** afin d’intégrer la fenêtre Explorateur de tests à votre espace de travail. Après quelques secondes, le test `ThingGetsObjectValFromNumber` doit s’afficher dans l’Explorateur de tests. Choisissez **Exécuter tout**.
   
   Le test doit réussir.

### <a name="writing-the-console-app"></a>Écriture de l’application console

1. Dans l’Explorateur de solutions, ouvrez le menu contextuel de la solution et ajoutez un nouveau projet **Application console (.NET Core)**. Nommez-le « App », puis définissez l’emplacement sur `Golden\src`.

2. Dans le projet **App**, ouvrez le menu contextuel du nœud **Dépendances**, puis choisissez **Ajouter**, **Référence**. 

3. Dans la boîte de dialogue **Gestionnaire de références**, cochez **Bibliothèque** sous le nœud **Projets**, **Solution**, puis cliquez sur **OK**.

6. Ouvrez le menu contextuel du nœud **App**, puis choisissez **Définir comme projet de démarrage**. Ainsi, il est possible d’appuyer sur F5 ou Ctrl+F5 pour démarrer l’application console.

7. Ouvrez le fichier `Program.cs`, ajoutez une directive `using Library;` en haut du fichier, puis ajoutez `Console.WriteLine($"The answer is {new Thing().Get(42)}");` à la méthode `Main`.

8. Définissez un point d’arrêt après la ligne que vous venez d’ajouter.

9. Appuyez sur F5 pour exécuter l’application.

   L’application doit se générer sans erreur et atteindre le point d’arrêt. Vous pouvez également vérifier que la sortie de l’application est « The answer is 42. ».



<!--HONumber=Nov16_HO3-->


