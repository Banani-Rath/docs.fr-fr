---
title: "&#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31103"
  - "bc31103"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31103"
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible
Une instruction essaie de récupérer la valeur d'une propriété alors qu'elle n'a pas accès à la procédure `Get` de la propriété.  
  
 Si l'[Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) est marquée avec un niveau d'accès plus restrictif que son [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), une tentative de lecture de la valeur de la propriété peut échouer dans les cas suivants :  
  
-   L'instruction `Get` est marquée [Private](../../../visual-basic/language-reference/modifiers/private.md) et le code appelant est situé à l'extérieur de la classe ou la structure dans laquelle la propriété est définie.  
  
-   L'instruction `Get` est marquée [Protected](../../../visual-basic/language-reference/modifiers/protected.md) et le code appelant ne figure pas dans la classe ou la structure dans laquelle la propriété est définie, ni dans une classe dérivée.  
  
-   L'instruction `Get` est marquée [Friend](../../../visual-basic/language-reference/modifiers/friend.md) et le code appelant ne figure pas dans l'assembly dans lequel la propriété est définie.  
  
 **ID d'erreur :** BC31103  
  
### Pour corriger cette erreur  
  
-   Si vous avez le contrôle du code source qui définit la propriété, vous devez déclarer la procédure `Get` avec le même niveau d'accès que la propriété proprement dite.  
  
-   Si vous n'avez pas le contrôle du code source qui définit la propriété, ou si vous devez limiter davantage le niveau d'accès de la procédure `Get` que celui de la propriété proprement dite, essayez de déplacer l'instruction qui lit la valeur de la propriété vers une zone de code qui offre un meilleur accès à la propriété.  
  
## Voir aussi  
 [Procédures de propriété](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)