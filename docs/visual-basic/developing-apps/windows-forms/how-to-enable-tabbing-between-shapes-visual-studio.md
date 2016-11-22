---
title: "How to: Enable Tabbing Between Shapes (Visual Studio) | Microsoft Docs"
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
  - "Line control, implementing tabbing"
  - "Shape control, implementing tabbing"
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Enable Tabbing Between Shapes (Visual Studio)
Les contrôles Line et Shape n'ont pas de propriété `TabStop` ou `TabIndex`, mais vous pouvez quand même activer la tabulation en leur sein.  Dans l'exemple suivant, le fait d'appuyer simultanément sur les touches CTRL et TABULATION permet de passer d'une forme à l'autre. Si vous appuyez uniquement sur la touche TAB, vous passerez d'un bouton à l'autre.  
  
> [!NOTE]
>  Il est possible que pour certains des éléments de l'interface utilisateur de Visual Studio, votre ordinateur affiche des noms ou des emplacements différents de ceux indiqués dans les instructions suivantes.  Ces éléments dépendent de l'édition de Visual Studio dont vous disposez et des paramètres que vous utilisez.  Pour plus d'informations, consultez [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/fr-fr/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Pour activer le passage d'une forme à l'autre  
  
1.  Faites glisser trois contrôles <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> et deux contrôles <xref:System.Windows.Forms.Button> depuis la **Boîte à outils** sur un formulaire.  
  
2.  Dans l'**Éditeur de code**, ajoutez une instruction `Imports` ou `using` au début du module :  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
3.  Ajoutez le code suivant à une procédure événementielle :  
  
     [!CODE [VbPowerPacksTabbing#1](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksTabbing#1)]  
  
4.  Ajoutez le code suivant à la procédure événementielle `Button1_PreviewKeyDown` :  
  
     [!CODE [VbPowerPacksTabbing#2](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksTabbing#2)]  
  
## Voir aussi  
 [How to: Draw Shapes with the OvalShape and RectangleShape Controls](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)   
 [How to: Draw Lines with the LineShape Control](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)   
 [Introduction to the Line and Shape Controls](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)