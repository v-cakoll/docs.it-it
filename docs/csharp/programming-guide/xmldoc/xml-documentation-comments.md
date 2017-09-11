---
title: Commenti relativi alla documentazione XML (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.xml
dev_langs:
- CSharp
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
caps.latest.revision: 26
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
ms.openlocfilehash: 408b2de29b15158499067da05dbb2f89eb1ba22f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="24c4e-102">Commenti relativi alla documentazione XML (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="24c4e-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="24c4e-103">In Visual C# è possibile creare la documentazione relativa al codice includendo elementi XML in campi di commento speciali (indicati da barre triple) nel codice sorgente, immediatamente prima del blocco di codice a cui i commenti fanno riferimento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="24c4e-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass{}  
```  
  
 <span data-ttu-id="24c4e-104">Quando si esegue la compilazione con l'opzione [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) il compilatore cerca tutti i tag XML presenti nel codice sorgente e crea un file di documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="24c4e-104">When you compile with the [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="24c4e-105">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="24c4e-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="24c4e-106">Per fare riferimento agli elementi XML (ad esempio, la funzione elabora elementi XML specifici che si desidera descrivere in un commento della documentazione XML), è possibile utilizzare il meccanismo standard (`<` e `>`).</span><span class="sxs-lookup"><span data-stu-id="24c4e-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="24c4e-107">Per fare riferimento agli identificatori generici in elementi di riferimento di codice (`cref`), è possibile usare caratteri di escape, ad esempio `cref="List<T>"`, o parentesi graffe (`cref="List{T}"`).</span><span class="sxs-lookup"><span data-stu-id="24c4e-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List<T>"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="24c4e-108">Come caso particolare, il compilatore analizza le parentesi graffe come parentesi uncinate per rendere il commento relativo alla documentazione meno complesso da creare quando viene fatto riferimento a identificatori generici.</span><span class="sxs-lookup"><span data-stu-id="24c4e-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24c4e-109">I commenti relativi alla documentazione XML non sono metadati, ovvero non vengono inclusi nell'assembly compilato e pertanto non sono accessibili mediante reflection.</span><span class="sxs-lookup"><span data-stu-id="24c4e-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24c4e-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="24c4e-110">In This Section</span></span>  
  
-   [<span data-ttu-id="24c4e-111">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="24c4e-111">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="24c4e-112">Elaborazione del file XML</span><span class="sxs-lookup"><span data-stu-id="24c4e-112">Processing the XML File</span></span>](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="24c4e-113">Delimitatori per i tag della documentazione</span><span class="sxs-lookup"><span data-stu-id="24c4e-113">Delimiters for Documentation Tags</span></span>](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [<span data-ttu-id="24c4e-114">Procedura: Usare le funzionalità relative alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="24c4e-114">How to: Use the XML Documentation Features</span></span>](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a><span data-ttu-id="24c4e-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="24c4e-115">Related Sections</span></span>  
 <span data-ttu-id="24c4e-116">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="24c4e-116">For more information, see:</span></span>  
  
-   [<span data-ttu-id="24c4e-117">/doc (elaborazione dei commenti per la documentazione)</span><span class="sxs-lookup"><span data-stu-id="24c4e-117">/doc (Process Documentation Comments)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="24c4e-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="24c4e-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24c4e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24c4e-119">See Also</span></span>  
 [<span data-ttu-id="24c4e-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="24c4e-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

