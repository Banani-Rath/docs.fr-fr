---
title: "Walkthrough: Creating Custom Log Listeners (Visual Basic) | Microsoft Docs"
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
  - "custom log listeners"
  - "My.Application.Log object, custom log listeners"
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Walkthrough: Creating Custom Log Listeners (Visual Basic)
Cette procédure pas à pas illustre comment créer un écouteur de journalisation personnalisé et le configurer pour écouter la sortie de l'objet `My.Application.Log`.  
  
## Mise en route  
 Les écouteurs de journalisation doivent hériter de la classe <xref:System.Diagnostics.TraceListener>.  
  
#### Pour créer l'écouteur  
  
-   Dans votre application, créez une classe nommée `SimpleListener` qui hérite de <xref:System.Diagnostics.TraceListener>.  
  
     [!CODE [VbVbalrMyApplicationLog#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#16)]  
  
     Les méthodes <xref:System.Diagnostics.TraceListener.Write%2A> et <xref:System.Diagnostics.TraceListener.WriteLine%2A>, requises par la classe de base, appellent `MsgBox` pour afficher leur entrée.  
  
     L'attribut <xref:System.Security.Permissions.HostProtectionAttribute> est appliqué aux méthodes <xref:System.Diagnostics.TraceListener.Write%2A> et <xref:System.Diagnostics.TraceListener.WriteLine%2A> afin que leurs attributs correspondent aux méthodes de classe de base.  L'attribut <xref:System.Security.Permissions.HostProtectionAttribute> permet à l'hôte qui exécute le code de déterminer que ce dernier expose la synchronisation de la protection de l'hôte.  
  
    > [!NOTE]
    >  L'attribut <xref:System.Security.Permissions.HostProtectionAttribute> n'est effectif que sur les applications non managées, telles que SQL Server, qui hébergent le Common Language Runtime et implémentent la protection de l'hôte.  
  
 Pour vérifier que `My.Application.Log` utilise votre écouteur de journalisation, vous devez attribuer un nom fort à l'assembly qui le contient.  
  
 La procédure suivante fournit des étapes simples pour créer un assembly d'écouteur de journalisation portant un nom fort.  Pour plus d'informations, consultez [Création et utilisation d'assemblys avec nom fort](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
#### Pour attribuer un nom fort à l'assembly de l'écouteur de journalisation  
  
1.  Sélectionnez un projet dans l'**Explorateur de solutions**.  Dans le menu **Projet**, choisissez **Propriétés**.  Pour plus d'informations, consultez [Introduction to the Project Designer](http://msdn.microsoft.com/fr-fr/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Cliquez sur l'onglet **Signature**.  
  
3.  Sélectionnez la zone **Signer l'assembly**.  
  
4.  Sélectionnez **\<Nouveau\>** dans la liste déroulante **Choisir un fichier de clé de nom fort**.  
  
     La boîte de dialogue **Créer une clé de nom fort** s'ouvre.  
  
5.  Fournissez un nom pour le fichier de clé dans la zone **Nom du fichier de clé**.  
  
6.  Entrez un mot de passe dans les zones **Entrer le mot de passe** et **Confirmer le mot de passe**.  
  
7.  Cliquez sur **OK**.  
  
8.  Régénérez l'application.  
  
## Ajout de l'écouteur  
 Maintenant que l'assembly a un nom fort, vous devez déterminer le nom fort de l'écouteur afin que `My.Application.Log` utilise votre écouteur de journalisation.  
  
 Le format d'un type portant un nom fort se présente comme suit.  
  
 \<nom type\>, \<nom assembly\>, \<numéro version\>, \<culture\>, \< nom fort\>  
  
#### Pour déterminer le nom fort de l'écouteur  
  
-   Le code suivant indique comment déterminer le nom de type fort pour `SimpleListener`.  
  
     [!CODE [VbVbalrMyApplicationLog#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#17)]  
  
     Le nom fort du type dépend de votre projet.  
  
 Avec le nom fort, vous pouvez ajouter l'écouteur à la collection de l'écouteur de journalisation `My.Application.Log`.  
  
#### Pour ajouter l'écouteur à My.Application.Log  
  
1.  Cliquez avec le bouton droit sur app.config dans l'**Explorateur de solutions** et sélectionnez l'option **Ouvrir**.  
  
     ou  
  
     S'il y a un fichier app.config :  
  
    1.  Dans le menu **Projet**, choisissez **Ajouter un nouvel élément**.  
  
    2.  Dans la boîte de dialogue **Ajouter un nouvel élément**, choisissez **Fichier de configuration de l'application**.  
  
    3.  Cliquez sur **Ajouter**.  
  
2.  Recherchez la section `<listeners>`, dans la section `<source>` avec l'attribut `name` "DefaultSource", située dans la section `<sources>`.  La section `<sources>` se trouve dans la section `<system.diagnostics>`, section `<configuration>` de niveau supérieur.  
  
3.  Ajoutez cet élément à la section `<listeners>` :  
  
    ```  
    <add name="SimpleLog" />  
    ```  
  
4.  Recherchez la section `<sharedListeners>`, dans la section `<system.diagnostics>`, dans la section `<configuration>` de niveau supérieur.  
  
5.  Ajoutez cet élément à la section `<sharedListeners>` :  
  
    ```  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     Modifiez la valeur de `SimpleLogStrongName` pour qu'elle soit le nom fort de l'écouteur.  
  
## Voir aussi  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Utilisation des journaux des applications](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Comment : écrire des messages de journal](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Procédure pas à pas : modification de l'emplacement des informations My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)