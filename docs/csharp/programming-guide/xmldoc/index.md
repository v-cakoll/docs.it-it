---
title: Commenti in formato documentazione XML - Guida per programmatori C#
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
ms.openlocfilehash: 07daff8b819220fad07e516281b93b24e39cba46
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711766"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="ea99d-102">Commenti relativi alla documentazione XML (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ea99d-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="ea99d-103">In Visual C# è possibile creare la documentazione relativa al codice includendo elementi XML in campi di commento speciali (indicati da barre triple) nel codice sorgente, immediatamente prima del blocco di codice a cui i commenti fanno riferimento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ea99d-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```csharp  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 <span data-ttu-id="ea99d-104">Quando si esegue la compilazione con l'opzione [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , il compilatore cerca tutti i tag XML nel codice sorgente e crea un file di documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="ea99d-104">When you compile with the [-doc](../../language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="ea99d-105">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="ea99d-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="ea99d-106">Per fare riferimento agli elementi XML (ad esempio, la funzione elabora elementi XML specifici che si desidera descrivere in un commento della documentazione XML), è possibile utilizzare il meccanismo standard (`<` e `>`).</span><span class="sxs-lookup"><span data-stu-id="ea99d-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="ea99d-107">Per fare riferimento agli identificatori generici in elementi di riferimento di codice (`cref`), è possibile usare caratteri di escape, ad esempio `cref="List&lt;T&gt;"`, o parentesi graffe (`cref="List{T}"`).</span><span class="sxs-lookup"><span data-stu-id="ea99d-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="ea99d-108">Come caso particolare, il compilatore analizza le parentesi graffe come parentesi uncinate per rendere il commento relativo alla documentazione meno complesso da creare quando viene fatto riferimento a identificatori generici.</span><span class="sxs-lookup"><span data-stu-id="ea99d-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea99d-109">I commenti relativi alla documentazione XML non sono metadati, ovvero non vengono inclusi nell'assembly compilato e pertanto non sono accessibili mediante reflection.</span><span class="sxs-lookup"><span data-stu-id="ea99d-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea99d-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ea99d-110">In This Section</span></span>  
  
- [<span data-ttu-id="ea99d-111">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="ea99d-111">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)  
  
- [<span data-ttu-id="ea99d-112">Elaborazione del file XML</span><span class="sxs-lookup"><span data-stu-id="ea99d-112">Processing the XML File</span></span>](./processing-the-xml-file.md)  
  
- [<span data-ttu-id="ea99d-113">Delimitatori per i tag della documentazione</span><span class="sxs-lookup"><span data-stu-id="ea99d-113">Delimiters for Documentation Tags</span></span>](./delimiters-for-documentation-tags.md)  
  
- [<span data-ttu-id="ea99d-114">Come utilizzare le funzionalità della documentazione XML</span><span class="sxs-lookup"><span data-stu-id="ea99d-114">How to use the XML documentation features</span></span>](./how-to-use-the-xml-documentation-features.md)
  
## <a name="related-sections"></a><span data-ttu-id="ea99d-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ea99d-115">Related Sections</span></span>  
 <span data-ttu-id="ea99d-116">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="ea99d-116">For more information, see:</span></span>  
  
- [<span data-ttu-id="ea99d-117">-DOC (elabora i commenti relativi alla documentazione)</span><span class="sxs-lookup"><span data-stu-id="ea99d-117">-doc (Process Documentation Comments)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="ea99d-118">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ea99d-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea99d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea99d-119">See also</span></span>

- [<span data-ttu-id="ea99d-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ea99d-120">C# Programming Guide</span></span>](../index.md)
