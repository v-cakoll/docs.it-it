---
title: "Procedura: Trovare un attributo dell'elemento padre (XPath-LINQ to XML) (C#)"
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 2e6c124d2653fb4426b3abb693f0b58daa5413c2
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593621"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="42a21-102">Procedura: Trovare un attributo dell'elemento padre (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="42a21-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="42a21-103">In questo argomento viene illustrato come spostarsi all'elemento padre e trovare un relativo attributo.</span><span class="sxs-lookup"><span data-stu-id="42a21-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="42a21-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="42a21-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="42a21-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="42a21-105">Example</span></span>

<span data-ttu-id="42a21-106">Viene innanzitutto individuato un elemento `Author`.</span><span class="sxs-lookup"><span data-stu-id="42a21-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="42a21-107">Quindi, viene individuato l'attributo `id` dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="42a21-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="42a21-108">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="42a21-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

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

<span data-ttu-id="42a21-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="42a21-109">This example produces the following output:</span></span>

```
Results are identical
id="bk101"
```
