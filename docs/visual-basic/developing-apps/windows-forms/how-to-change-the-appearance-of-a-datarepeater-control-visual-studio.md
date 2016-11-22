---
title: "How to: Change the Appearance of a DataRepeater Control (Visual Studio) | Microsoft Docs"
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
  - "DataRepeater, customizing"
  - "DataRepeater, changing run time appearance"
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# How to: Change the Appearance of a DataRepeater Control (Visual Studio)
Vous pouvez modifier l'apparence d'un contrôle <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> au moment du design en définissant ses propriétés ou au moment de l'exécution en gérant l'événement <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>.  
  
 Les propriétés que vous définissez au moment du design lorsque la section modèle d'élément du contrôle est sélectionnée sont répétées pour chaque <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> au moment de l'exécution.  Les propriétés relatives à l'apparence du contrôle <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> lui\-même sont uniquement visibles au moment de l'exécution si une partie du conteneur est laissée à découvert \(par exemple, si la valeur de la propriété <xref:System.Windows.Forms.Control.Padding%2A> est une valeur élevée\).  
  
 Des propriétés liées à l'apparence peuvent être définies en fonction de conditions au moment de l'exécution.  Par exemple, dans le cas d'une application de planification, vous pouvez modifier la couleur d'arrière\-plan d'un élément afin de prévenir les utilisateurs que la date d'échéance est dépassée.  Dans le gestionnaire d'événements <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>, si vous définissez une propriété dans une instruction conditionnelle, telle que `If…Then`, vous devez également utiliser une clause `Else` pour spécifier l'apparence lorsque la condition n'est pas remplie.  
  
### Pour modifier l'apparence au moment du design  
  
1.  Dans le Concepteur Windows Forms, sélectionnez la région \(supérieure\) du modèle d'élément du contrôle <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
2.  Dans la fenêtre Propriétés, sélectionnez une propriété et modifiez sa valeur.  Les propriétés communes qui affectent l'apparence sont <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A> et <xref:System.Windows.Forms.Control.ForeColor%2A>.  
  
### Pour modifier l'apparence au moment de l'exécution  
  
1.  Dans l'Éditeur de code, sous la liste déroulante Événement, cliquez sur **DrawItem**.  
  
2.  Dans le gestionnaire d'événements <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>, ajoutez le code suivant pour définir les propriétés :  
  
     [!CODE [VbPowerPacksDataRepeaterAppearance#1](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksDataRepeaterAppearance#1)]  
  
## Exemple  
 Certaines personnalisations courantes du contrôle <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> comprennent l'affichage des lignes dans différentes couleurs et la modification de la couleur d'un champ en fonction d'une condition.  L'exemple suivant montre comment effectuer ces personnalisations.  Cet exemple suppose qu'il existe un contrôle <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> lié à la table Products de la base de données Northwind.  
  
 [!CODE [VbPowerPacksDataRepeaterAlternateBackColor#1](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksDataRepeaterAlternateBackColor#1)]  
  
 Notez que pour que ces deux personnalisations, vous devez fournir le code définissant les propriétés des deux côtés de la condition.  Si vous ne spécifiez pas la condition `Else`, vous obtiendrez des résultats inattendus au moment de l'exécution.  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)