---
title: "&lt;summary&gt; (guide de programmation C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<summary>"
  - "summary"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<summary> (balise XML C#)"
  - "summary (balise XML C#)"
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
caps.latest.revision: 17
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;summary&gt; (guide de programmation C#)
## Syntaxe  
  
```  
<summary>description</summary>  
```  
  
#### Paramètres  
 `description`  
 Résumé de l'objet.  
  
## Notes  
 La balise \<summary\> doit être utilisée pour décrire un type ou un membre d'un type.  Utilisez [\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md) pour ajouter des informations complémentaires à une description de type.  Utilisez l'[attribut cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) pour activer des outils documentaires tels que [Sandcastle \(page éventuellement en anglais\)](http://go.microsoft.com/fwlink/?LinkId=124061) permettant de créer des liens hypertexte internes aux pages de documentation pour les éléments de code.  
  
 Le texte de la balise \<summary\> est la seule source d'information sur le type dans IntelliSense. Il est également affiché dans l'[Object Browser Window](http://msdn.microsoft.com/fr-fr/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).  
  
 Compilez avec [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) pour traiter les commentaires de documentation et les placer dans un fichier.  Pour créer la documentation finale qui est basée sur le fichier généré par le compilateur, vous pouvez créer un outil personnalisé ou utiliser un outil de type [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061).  
  
## Exemple  
 [!CODE [csProgGuideDocComments#12](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDocComments#12)]  
  
 L'exemple précédent génère le fichier XML suivant.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## Exemple  
 L'exemple suivant indique comment faire une référence `cref` à un type générique.  
  
 [!CODE [csProgGuideDocComments#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDocComments#11)]  
  
 L'exemple précédent génère le fichier XML suivant.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
  
```  
  
## Voir aussi  
 [Guide de programmation C\#](../../../csharp/programming-guide/index.md)   
 [Balises recommandées pour les commentaires de documentation](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)