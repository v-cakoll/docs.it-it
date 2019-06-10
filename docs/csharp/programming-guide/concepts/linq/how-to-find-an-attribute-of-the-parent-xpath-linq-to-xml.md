---
title: "Procedura: Trovare un attributo dell'elemento padre (XPath-LINQ to XML) (C#)"
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: f30c810483d8253132b9fe3e0959d04a8b4d26a0
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690068"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="b2f49-102">Procedura: Trovare un attributo dell'elemento padre (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b2f49-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="b2f49-103">In questo argomento viene illustrato come spostarsi all'elemento padre e trovare un relativo attributo.</span><span class="sxs-lookup"><span data-stu-id="b2f49-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="b2f49-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="b2f49-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="b2f49-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2f49-105">Example</span></span>

<span data-ttu-id="b2f49-106">Viene innanzitutto individuato un elemento `Author`.</span><span class="sxs-lookup"><span data-stu-id="b2f49-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="b2f49-107">Quindi, viene individuato l'attributo `id` dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="b2f49-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="b2f49-108">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b2f49-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement author =
    books
    .Root
    .Element("Book")
    .Element("Author");

// LINQ to XML query
XAttribute att1 =
    author
    .Parent
    .Attribute("id");

// XPath expression
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();

if (att1 == att2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(att1);
```

<span data-ttu-id="b2f49-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="b2f49-109">This example produces the following output:</span></span>

```
Results are identical
id="bk101"
```
