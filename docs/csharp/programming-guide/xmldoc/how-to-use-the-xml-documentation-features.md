---
title: "Procedura: utilizzare le funzionalità relative alla documentazione XML (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eeee77db523bc0ad97f425d4ba8076ae5740dfe8
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a>Procedura: utilizzare le funzionalità relative alla documentazione XML (Guida per programmatori C#)
L'esempio seguente fornisce una panoramica di base di un tipo documentato.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 **// Questo file con estensione xml è stato generato con il codice di esempio precedente.**  
**\<?xml version="1.0"?>**  
**\<doc>**  
 **\<assembly>**  
 **\<name>xmlsample\</name>**  
 **\</assembly>**  
 **\<members>**  
 **\<member name="T:SomeClass">**  
 **\<summary>**  
 **Class level summary documentation goes here.\</summary>**  
 **\<remarks>**  
 **È possibile associare commenti più estesi a un tipo o un membro**   
 **tramite il tag remarks\</remarks>**  
 **\</member>**  
 **\<member name="F:SomeClass.m_Name">**  
 **\<summary>**  
 **Store for the name property\</summary>**  
 **\</member>**  
 **\<member name="M:SomeClass.#ctor">**  
 **\<summary>The class constructor.\</summary>**   
 **\</member>**  
 **\<member name="M:SomeClass.SomeMethod(System.String)">**  
 **\<summary>**  
 **Description for SomeMethod.\</summary>**  
 **\<param name="s"> Parameter description for s goes here\</param>**  
 **\<seealso cref="T:System.String">**  
 **È possibile utilizzare l'attributo cref in qualsiasi tag per fare riferimento a un tipo o un membro.**   
 **Il compilatore verificherà l'esistenza del riferimento. \</seealso>**  
 **\</member>**  
 **\<member name="M:SomeClass.SomeOtherMethod">**  
 **\<summary>**  
 **Some other method. \</summary>**  
 **\<returns>**  
 **Return results are described through the returns tag.\</returns>**  
 **\<seealso cref="M:SomeClass.SomeMethod(System.String)">**  
 **Notice the use of the cref attribute to reference a specific method \</seealso>**  
 **\</member>**  
 **\<member name="M:SomeClass.Main(System.String[])">**  
 **\<summary>**  
 **Punto di ingresso dell'applicazione.**  
 **\</summary>**  
 **\<param name="args"> A list of command line arguments\</param>**  
 **\</member>**  
 **\<member name="P:SomeClass.Name">**  
 **\<summary>**  
 **Name property \</summary>**  
 **\<value>**  
 **A value tag is used to describe the property value\</value>**  
 **\</member>**  
 **\</members>**  
**\</doc>**   
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare l'esempio, digitare la riga di comando seguente:  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 Verrà creato il file XML XMLsample.xml, che è possibile visualizzare nel browser o tramite il comando TYPE.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 La documentazione XML inizia con ///. Quando si crea un nuovo progetto, le procedure guidate inseriscono alcune linee /// iniziali. L'elaborazione di questi commenti presenta alcune restrizioni:  
  
-   La documentazione deve essere in codice XML ben formato. Se il codice XML non è ben formato, viene generato un avviso e il file di documentazione conterrà un commento che segnalerà che si è verificato un errore.  
  
-   Gli sviluppatori sono liberi di creare set di tag personalizzati. È disponibile un set di tag consigliato (vedere la sezione Altre informazioni). Alcuni tag consigliati hanno un significato speciale:  
  
    -   Il tag \< viene usato per descrivere i parametri. Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione. Se la verifica ha esito negativo, il compilatore genera un avviso.  
  
    -   L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice. Il compilatore verifica l'esistenza di questo elemento. Se la verifica ha esito negativo, il compilatore genera un avviso. Il compilatore rispetta eventuali istruzioni `using` quando esegue la ricerca di un tipo descritto nell'attributo `cref`.  
  
    -   Il tag \< è usato da IntelliSense all'interno di Visual Studio per visualizzare altre informazioni su un tipo o su un membro.  
  
        > [!NOTE]
        >  Il file XML non fornisce informazioni complete sul tipo e sui membri, ad esempio, non contiene alcuna informazione sul tipo. Per ottenere informazioni complete su un tipo o su un membro, è necessario usare il file di documentazione con reflection sul tipo o sul membro effettivo.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [/doc (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Commenti relativi alla documentazione XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

