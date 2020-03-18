---
title: Come trovare un'unione di due percorsi di percorso (XPath-LINQ to XML) (C
ms.date: 07/20/2015
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: 17a3310f367cb68b3b80b1a3f30af40428f6d2c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141218"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a><span data-ttu-id="a9204-102">Come trovare un'unione di due percorsi di percorso (XPath-LINQ to XML) (C</span><span class="sxs-lookup"><span data-stu-id="a9204-102">How to find a union of two location paths (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="a9204-103">In XPath è possibile trovare l'unione dei risultati di due percorsi di posizione XPath.</span><span class="sxs-lookup"><span data-stu-id="a9204-103">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="a9204-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="a9204-104">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="a9204-105">È possibile ottenere gli stessi risultati usando l'operatore di query standard <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9204-105">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9204-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9204-106">Example</span></span>  
 <span data-ttu-id="a9204-107">In questo esempio vengono trovati tutti gli elementi `Category` e tutti gli elementi `Price`, che vengono concatenati in un'unica raccolta.</span><span class="sxs-lookup"><span data-stu-id="a9204-107">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="a9204-108">Si noti che la query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] chiama <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> per ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a9204-108">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="a9204-109">Anche i risultati della valutazione dell'espressione di XPath sono nell'ordine del documento.</span><span class="sxs-lookup"><span data-stu-id="a9204-109">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="a9204-110">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a9204-110">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument data = XDocument.Load("Data.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    data  
    .Descendants("Category")  
    .Concat(  
        data  
        .Descendants("Price")  
    )  
    .InDocumentOrder();  
  
// XPath expression  
IEnumerable<XElement> list2 = data.XPathSelectElements("//Category|//Price");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="a9204-111">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="a9204-111">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  