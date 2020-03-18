---
title: Commenti relativi alla documentazione XML - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: f5a507bc35b0cc0a679fd055bfc255bb3cb9a090
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "76789790"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="de726-102">Commenti relativi alla documentazione XML (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="de726-102">XML documentation comments (C# programming guide)</span></span>

<span data-ttu-id="de726-103">Nel linguaggio C, è possibile creare la documentazione per il codice includendo elementi XML in campi di commento speciali (indicati da barre triple) nel codice sorgente direttamente prima del blocco di codice a cui fanno riferimento i commenti, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="de726-103">In C#, you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example.</span></span>

```csharp
/// <summary>
///  This class performs an important function.
/// </summary>
public class MyClass {}
```

<span data-ttu-id="de726-104">Quando si esegue la compilazione con l'opzione [-doc,](../../language-reference/compiler-options/doc-compiler-option.md) il compilatore cercherà tutti i tag XML nel codice sorgente e creerà un file di documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="de726-104">When you compile with the [-doc](../../language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="de726-105">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="de726-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="de726-106">Per fare riferimento agli elementi XML (ad esempio, la funzione elabora elementi XML specifici che si desidera descrivere in un commento della documentazione XML), è possibile utilizzare il meccanismo standard (`<` e `>`).</span><span class="sxs-lookup"><span data-stu-id="de726-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="de726-107">Per fare riferimento agli identificatori generici in elementi di riferimento di codice (`cref`), è possibile usare caratteri di escape, ad esempio `cref="List&lt;T&gt;"`, o parentesi graffe (`cref="List{T}"`).</span><span class="sxs-lookup"><span data-stu-id="de726-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="de726-108">Come caso particolare, il compilatore analizza le parentesi graffe come parentesi uncinate per rendere il commento relativo alla documentazione meno complesso da creare quando viene fatto riferimento a identificatori generici.</span><span class="sxs-lookup"><span data-stu-id="de726-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="de726-109">I commenti relativi alla documentazione XML non sono metadati, ovvero non vengono inclusi nell'assembly compilato e pertanto non sono accessibili mediante reflection.</span><span class="sxs-lookup"><span data-stu-id="de726-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="de726-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="de726-110">In this section</span></span>

- [<span data-ttu-id="de726-111">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="de726-111">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)

- [<span data-ttu-id="de726-112">Elaborazione del file XML</span><span class="sxs-lookup"><span data-stu-id="de726-112">Processing the XML file</span></span>](./processing-the-xml-file.md)

- [<span data-ttu-id="de726-113">Delimitatori per i tag della documentazione</span><span class="sxs-lookup"><span data-stu-id="de726-113">Delimiters for documentation tags</span></span>](./delimiters-for-documentation-tags.md)

- [<span data-ttu-id="de726-114">Come usare le funzionalità relative alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="de726-114">How to use the XML documentation features</span></span>](./how-to-use-the-xml-documentation-features.md)

## <a name="related-sections"></a><span data-ttu-id="de726-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="de726-115">Related sections</span></span>

<span data-ttu-id="de726-116">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="de726-116">For more information, see:</span></span>

- [<span data-ttu-id="de726-117">-doc (Elabora i commenti della documentazione)</span><span class="sxs-lookup"><span data-stu-id="de726-117">-doc (Process Documentation Comments)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)

## <a name="c-language-specification"></a><span data-ttu-id="de726-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="de726-118">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="de726-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de726-119">See also</span></span>

- [<span data-ttu-id="de726-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="de726-120">C# Programming Guide</span></span>](../index.md)
