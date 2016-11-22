---
title: "How to: Create a Collection Used by a Collection Initializer (Visual Basic) | Microsoft Docs"
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
  - "collection initializers [Visual Basic]"
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Create a Collection Used by a Collection Initializer (Visual Basic)
Lorsque vous utilisez un initialiseur de collection pour créer une collection, le compilateur de Visual Basic recherche une méthode `Add` du type de collection pour lequel les paramètres de la méthode `Add` correspondent aux types des valeurs dans l'initialiseur de collection.  Cette méthode `Add` est utilisée pour remplir la collection avec les valeurs de l'initialiseur de collection.  
  
## Exemple  
 L'exemple suivant affiche une collection `OrderCollection` contenant une méthode `Add` publique qu'un initialiseur de collection peut utiliser pour ajouter des objets de type `Order`.  La méthode `Add` vous permet d'utiliser la syntaxe raccourcie de l'initialiseur de collection.  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#4)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#1)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#2)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#3)]  
  
## Voir aussi  
 [Collection Initializers](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [How to: Create an Add Extension Method Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)