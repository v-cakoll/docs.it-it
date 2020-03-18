---
title: Cref (attributo) - Guida alla programmazione in C
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: b06d0c9d447124dec7d8cf3c0cbbfd0daca78fe3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79157013"
---
# <a name="cref-attribute-c-programming-guide"></a>attributo cref (Guida per programmatori C

L'attributo `cref` in un tag della documentazione XML indica un "riferimento al codice". Specifica che il testo all'interno del tag è un elemento di codice, ad esempio un tipo, un metodo o una proprietà. Gli strumenti per la creazione di documentazione, come [DocFX](https://dotnet.github.io/docfx/) e [Sandcastle](https://github.com/EWSoftware/SHFB), usano attributi `cref` per generare automaticamente collegamenti ipertestuali alla pagina in cui è documentato il tipo o il membro.

## <a name="example"></a>Esempio

L'esempio `cref` seguente mostra gli attributi utilizzati nei [ \<](./see.md) tag>.

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

Durante la compilazione, il programma crea il file XML seguente. Si noti che l'attributo `cref` del metodo `GetZero`, ad esempio, è stato trasformato dal compilatore in `"M:TestNamespace.TestClass.GetZero"`. Il prefisso "M:" significa "metodo" ed è una convenzione riconosciuta dagli strumenti di creazione della documentazione come DocFX e Sandcastle. Per un elenco completo dei prefissi, vedere [Elaborazione del file XML](./processing-the-xml-file.md).

```xml  
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:TestNamespace.TestClass">
            <summary>
            TestClass contains several cref examples.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor">
            <summary>
            This sample shows how to specify the <see cref="T:TestNamespace.TestClass"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor(System.Int32)">
            <summary>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.#ctor(System.Int32)"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.GetZero">
            <summary>
            The GetZero method.
            </summary>
            <example>
            This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.
            <code>
            class TestClass
            {
                static int Main()
                {
                    return GetZero();
                }
            }
            </code>
            </example>
        </member>
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">
            <summary>
            The GetGenericValue method.
            </summary>
            <remarks>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.
            </remarks>
        </member>
        <member name="T:TestNamespace.GenericClass`1">
            <summary>
            GenericClass.
            </summary>
            <remarks>
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.
            </remarks>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a>Vedere anche

- [Commenti relativi alla documentazione XML](./index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
