---
title: "&#39;As Any&#39; is not supported in &#39;Declare&#39; statements | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30828"
  - "vbc30828"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30828"
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &#39;As Any&#39; is not supported in &#39;Declare&#39; statements
Le type de données `Any` était utilisé avec les instructions `Declare` dans Visual Basic 6.0 et dans les versions antérieures pour permettre d'utiliser des arguments pouvant contenir n'importe quel type de données.  Toutefois, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] prend en charge la surcharge et rend ainsi le type de données `Any` obsolète.  
  
 **ID d'erreur :** BC30828  
  
### Pour corriger cette erreur  
  
1.  Déclarez les paramètres du type spécifique que vous souhaitez utiliser, comme dans l'exemple suivant.  
  
     [!CODE [VbVbalrStatements#95](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#95)]  
  
2.  Utilisez l'attribut <xref:System.Runtime.InteropServices.MarshalAsAttribute> pour spécifier `As Any` lorsque `Void*` est attendu par la procédure appelée.  
  
     [!CODE [VbVbalrStatements#96](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#96)]  
  
## Voir aussi  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Creating Prototypes in Managed Code](../Topic/Creating%20Prototypes%20in%20Managed%20Code.md)