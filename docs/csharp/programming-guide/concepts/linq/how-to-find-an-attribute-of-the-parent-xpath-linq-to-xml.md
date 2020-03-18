---
title: Come trovare un attributo dell'elemento padre (XPath-LINQ to XML) (C
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: bfe7554a5c767adde5e7170c8e1ea0537155f6df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141168"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>Come trovare un attributo dell'elemento padre (XPath-LINQ to XML) (C

In questo argomento viene illustrato come spostarsi all'elemento padre e trovare un relativo attributo.

L'espressione XPath è:

`../@id`

## <a name="example"></a>Esempio

Viene innanzitutto individuato un elemento `Author`. Quindi, viene individuato l'attributo `id` dell'elemento padre.

Nell'esempio viene usato il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).

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

Nell'esempio viene prodotto l'output seguente:

```output
Results are identical
id="bk101"
```
