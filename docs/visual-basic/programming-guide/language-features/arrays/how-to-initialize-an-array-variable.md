---
title: "How to: Initialize an Array Variable in Visual Basic | Microsoft Docs"
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
  - "variables [Visual Basic], initializing"
  - "arrays [Visual Basic], variables"
  - "arrays [Visual Basic], initializing"
  - "arrays [Visual Basic], declaring"
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
caps.latest.revision: 42
caps.handback.revision: 42
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Initialize an Array Variable in Visual Basic
Vous initialisez une variable de tableau en incluant un littéral de tableau dans une clause `New` et en spécifiant les valeurs initiales du tableau.  Vous pouvez spécifier le type ou permettre de le déduire des valeurs du littéral de tableau.  Pour plus d'informations sur la façon dont le type est déduit, consultez « Remplissage d'un tableau avec des valeurs initiales » dans [Tableaux](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
### Pour initialiser une variable tableau à l'aide d'un littéral de tableau  
  
-   Dans la clause `New`, ou lorsque vous assignez la valeur de tableau, fournissez les valeurs d'élément en les plaçant entre accolades \(`{}`\).  L'exemple suivant illustre plusieurs méthodes permettant de déclarer, de créer et d'initialiser une variable destinée à contenir un tableau qui comporte des éléments de type `Char`.  
  
     [!CODE [VbVbalrArrays#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#16)]  
  
     Après l'exécution de chaque instruction , le tableau créé a une de longueur de 3, avec des éléments de l'index 0 à l'index 2 contenant les valeurs initiales.  Si vous fournissez à la fois la limite supérieure et les valeurs, vous devez inclure une valeur pour chaque élément de l'index 0 jusqu'à la limite supérieure.  
  
     Notez que vous n'êtes pas obligé de spécifier la limite supérieure d'index si vous fournissez des valeurs d'éléments dans un littéral de tableau.  Si aucune limite supérieure n'est spécifiée, la taille du tableau est déduite selon le nombre de valeurs présentes dans le littéral de tableau.  
  
### Pour initialiser une variable tableau multidimensionnel à l'aide des littéraux de tableaux  
  
-   Imbriquez des valeurs entre accolades \(`{}`\) au sein d'accolades.  Veillez à ce que les littéraux de tableaux imbriqués soient tous déduits en tant que tableaux du même type et de même longueur.  L'exemple de code suivant illustre plusieurs méthodes d'initialisation de tableau multidimensionnel.  
  
     [!CODE [VbVbalrArrays#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#17)]  
  
-   Vous pouvez spécifier explicitement les limites d'index de tableau ou les ignorer et laisser le compilateur les déduire selon les valeurs présentes dans le littéral de tableau.  Si vous fournissez à la fois les limites supérieures et les valeurs, vous devez inclure une valeur pour chaque élément de l'index 0 jusqu'à la limite supérieure dans chaque dimension.  L'exemple suivant illustre plusieurs méthodes permettant de déclarer, de créer et d'initialiser une variable destinée à contenir un tableau à deux dimensions qui comporte des éléments de type `Short`.  
  
     [!CODE [VbVbalrArrays#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#18)]  
  
     Après l'exécution de chaque instruction, le tableau créé contient six éléments initialisés ayant les index `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)` et `(1,2)`.  Chaque emplacement de tableau contient la valeur `10`.  
  
-   L'exemple suivant itère au sein d'un tableau multidimensionnel.  Dans une application console Windows qui est écrite en Visual Basic, collez le code dans la méthode `Sub Main()`.  Les derniers commentaires illustrent la sortie.  
  
     [!CODE [VbVbalrArrays#31](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#31)]  
  
### Pour initialiser une variable tableau en escalier à l'aide des littéraux de tableaux  
  
-   Imbriquez des valeurs d'objet entre accolades \(`{}`\).  Bien que vous puissiez également imbriquer des littéraux de tableaux qui spécifient des tableaux de longueurs différentes, dans le cas d'un tableau en escalier, veillez à ce que les littéraux de tableaux imbriqués soient placés entre parenthèses \(`()`\).  Les parenthèses forcent l'évaluation des littéraux de tableaux imbriqués et les tableaux obtenus sont utilisés comme valeurs initiales du tableau en escalier.  L'exemple de code suivant illustre deux méthodes d'initialisation de tableau en escalier.  
  
     [!CODE [VbVbalrArrays#19](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#19)]  
  
-   L'exemple suivant itère au sein d'un tableau en escalier.  Dans une application console Windows qui est écrite en Visual Basic, collez le code dans la méthode `Sub Main()`.  Les derniers commentaires du code illustrent la sortie.  
  
     [!CODE [VbVbalrArrays#32](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#32)]  
  
## Voir aussi  
 [Tableaux](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Troubleshooting Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)