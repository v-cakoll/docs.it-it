---
title: 'Procedura: Trovare un''unione di due percorsi (XPath-LINQ to XML) (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b15991b6a97c19cd038114649bcef90f53ea5ace
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a><span data-ttu-id="4bf6d-102">Procedura: Trovare un'unione di due percorsi (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="4bf6d-102">How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="4bf6d-103">In XPath è possibile trovare l'unione dei risultati di due percorsi di posizione XPath.</span><span class="sxs-lookup"><span data-stu-id="4bf6d-103">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="4bf6d-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="4bf6d-104">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="4bf6d-105">È possibile ottenere gli stessi risultati usando l'operatore di query standard <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="4bf6d-105">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bf6d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bf6d-106">Example</span></span>  
 <span data-ttu-id="4bf6d-107">In questo esempio vengono trovati tutti gli elementi `Category` e tutti gli elementi `Price`, che vengono concatenati in un'unica raccolta.</span><span class="sxs-lookup"><span data-stu-id="4bf6d-107">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="4bf6d-108">Si noti che la query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] chiama <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> per ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="4bf6d-108">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="4bf6d-109">Anche i risultati della valutazione dell'espressione di XPath sono nell'ordine del documento.</span><span class="sxs-lookup"><span data-stu-id="4bf6d-109">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="4bf6d-110">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4bf6d-110">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="4bf6d-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4bf6d-111">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="4bf6d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bf6d-112">See Also</span></span>  
 [<span data-ttu-id="4bf6d-113">LINQ to XML per gli utenti di XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="4bf6d-113">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

