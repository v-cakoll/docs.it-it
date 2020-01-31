---
title: Come utilizzare le funzionalità della documentazione XML- C# Guida alla programmazione
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 57034fb835d4c82b5bf658e61ec78ef226c2551e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789778"
---
# <a name="how-to-use-the-xml-documentation-features"></a>Come usare le funzionalità relative alla documentazione XML

L'esempio seguente fornisce una panoramica di base di un tipo documentato.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

Nell'esempio viene generato un file con estensione *XML* con il contenuto seguente.

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member 
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a>Compilazione del codice

Per compilare l'esempio, digitare la riga di comando seguente:

`csc XMLsample.cs /doc:XMLsample.xml`

Tramite il comando verrà creato il file XML *XMLsample.xml*, che è possibile visualizzare nel browser o tramite il comando TYPE.

## <a name="robust-programming"></a>Programmazione efficiente

La documentazione XML inizia con ///. Quando si crea un nuovo progetto, le procedure guidate inseriscono alcune linee /// iniziali. L'elaborazione di questi commenti presenta alcune restrizioni:

- La documentazione deve essere in codice XML ben formato. Se il codice XML non è ben formato, viene generato un avviso e il file di documentazione conterrà un commento che segnalerà che si è verificato un errore.

- Gli sviluppatori sono liberi di creare set di tag personalizzati. È disponibile un [set di tag consigliato](recommended-tags-for-documentation-comments.md). Alcuni tag consigliati hanno un significato speciale:

  - Il tag \< viene usato per descrivere i parametri. Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione. Se la verifica ha esito negativo, il compilatore genera un avviso.

  - L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice. Il compilatore verifica l'esistenza di questo elemento. Se la verifica ha esito negativo, il compilatore genera un avviso. Il compilatore rispetta eventuali istruzioni `using` quando esegue la ricerca di un tipo descritto nell'attributo `cref`.

  - Il tag \< è usato da IntelliSense all'interno di Visual Studio per visualizzare altre informazioni su un tipo o su un membro.

    > [!NOTE]
    > Il file XML non fornisce informazioni complete sul tipo e sui membri, ad esempio, non contiene alcuna informazione sul tipo. Per ottenere informazioni complete su un tipo o su un membro, è necessario usare il file di documentazione con reflection sul tipo o sul membro effettivo.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [-DOC (C# opzioni del compilatore)](../../language-reference/compiler-options/doc-compiler-option.md)
- [Commenti relativi alla documentazione XML](./index.md)
- [Processore della documentazione di DocFX](https://dotnet.github.io/docfx/)
- [Processore di documentazione Sandcastle](https://github.com/EWSoftware/SHFB)
