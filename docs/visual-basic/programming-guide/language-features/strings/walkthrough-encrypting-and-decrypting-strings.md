---
title: "Walkthrough: Encrypting and Decrypting Strings in Visual Basic | Microsoft Docs"
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
  - "encryption, strings"
  - "strings [Visual Basic], encrypting"
  - "decryption, strings"
  - "strings [Visual Basic], decrypting"
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Walkthrough: Encrypting and Decrypting Strings in Visual Basic
Cette procédure pas à pas vous explique comment utiliser la classe <xref:System.Security.Cryptography.DESCryptoServiceProvider> pour chiffrer et déchiffrer des chaînes à l'aide de la version du fournisseur de services de chiffrement \(CSP\) de l'algorithme Triple Data Encryption Standard \(<xref:System.Security.Cryptography.TripleDES>\).  La première étape consiste à créer une classe wrapper simple qui encapsule l'algorithme 3DES et stocke les données chiffrées sous forme de chaîne encodée en base 64.  Ensuite, ce wrapper est utilisé pour stocker en toute sécurité les données utilisateur privées dans un fichier texte accessible publiquement.  
  
 Vous pouvez utiliser le chiffrement pour protéger des données utilisateur confidentielles \(par exemple, des mots de passe\) et rendre les informations d'identification illisibles par les utilisateurs non autorisés.  Cela peut empêcher le vol de l'identité d'un utilisateur autorisé ce qui protège les ressources de l'utilisateur et garantit la non\-répudiabilité.  Le chiffrement empêche également l'accès aux données d'un utilisateur par des utilisateurs non autorisés.  
  
 Pour plus d’informations, consultez [Services de chiffrement](../Topic/Cryptographic%20Services.md).  
  
> [!IMPORTANT]
>  Les algorithmes Rijndael \(maintenant appelé Advanced Ecryption Standard \[AES\]\) et Triple Data Encryption Standard \(3DES\) offrent une plus grande sécurité que DES parce qu'ils sollicitent beaucoup de ressources informatiques.  Pour plus d'informations, consultez <xref:System.Security.Cryptography.DES> et <xref:System.Security.Cryptography.Rijndael>.  
  
### Pour créer le wrapper de chiffrement  
  
1.  Créez la classe d' `Simple3Des` pour encapsuler les méthodes de chiffrement et de déchiffrement.  
  
     [!CODE [VbVbalrStrings#38](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#38)]  
  
2.  Ajoutez une importation de l'espace de noms de chiffrement au début du fichier qui contient la classe d' `Simple3Des` .  
  
     [!CODE [VbVbalrStrings#77](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#77)]  
  
3.  Dans la classe d' `Simple3Des` , ajoutez un champ privé pour stocker le fournisseur de services de chiffrement 3DES.  
  
     [!CODE [VbVbalrStrings#39](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#39)]  
  
4.  Ajoutez une méthode privée qui crée un tableau d'octets d'une longueur spécifiée à partir du hachage de la clé spécifiée.  
  
     [!CODE [VbVbalrStrings#41](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#41)]  
  
5.  Ajoutez un constructeur pour initialiser le fournisseur de services de chiffrement 3DES.  
  
     Le paramètre `key` contrôle les méthodes `EncryptData` et `DecryptData`.  
  
     [!CODE [VbVbalrStrings#40](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#40)]  
  
6.  Ajoutez une méthode publique qui chiffre une chaîne.  
  
     [!CODE [VbVbalrStrings#42](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#42)]  
  
7.  Ajoutez une méthode publique qui déchiffre une chaîne.  
  
     [!CODE [VbVbalrStrings#43](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#43)]  
  
     La classe wrapper peut maintenant être utilisée pour protéger les ressources de l'utilisateur.  Dans cet exemple, elle est utilisée pour stocker en toute sécurité les données utilisateur privées dans un fichier texte accessible publiquement.  
  
### Pour tester le wrapper de chiffrement  
  
1.  Dans une classe distincte, ajoutez une méthode qui utilise la méthode `EncryptData` du wrapper pour chiffrer une chaîne et l'écrire dans le dossier Mes documents de l'utilisateur.  
  
     [!CODE [VbVbalrStrings#78](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#78)]  
  
2.  Ajoutez une méthode qui lit la chaîne chiffrée du dossier Mes documents de l'utilisateur et la déchiffre à l'aide de la méthode `DecryptData` du wrapper.  
  
     [!CODE [VbVbalrStrings#79](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#79)]  
  
3.  Ajoutez le code d'interface utilisateur pour appeler les méthodes `TestEncoding` et `TestDecoding`.  
  
4.  Exécutez l'application.  
  
     Lorsque vous testez l'application, notez qu'elle ne déchiffrera pas les données si vous entrez un mot de passe incorrect.  
  
## Voir aussi  
 <xref:System.Security.Cryptography>   
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>   
 <xref:System.Security.Cryptography.DES>   
 <xref:System.Security.Cryptography.TripleDES>   
 <xref:System.Security.Cryptography.Rijndael>   
 [Services de chiffrement](../Topic/Cryptographic%20Services.md)