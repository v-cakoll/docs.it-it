---
title: 'Procedura: Ordinare elementi (C#)'
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: ac79690ce45f6875900418b39e0f5e86596dceff
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710059"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="03799-102">Procedura: Ordinare elementi (C#)</span><span class="sxs-lookup"><span data-stu-id="03799-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="03799-103">In questo esempio viene illustrato come scrivere una query che ordina i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="03799-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03799-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="03799-104">Example</span></span>  
 <span data-ttu-id="03799-105">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="03799-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> prices =  
    from el in root.Elements("Data")  
    let price = (decimal)el.Element("Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="03799-106">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="03799-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="03799-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="03799-107">Example</span></span>  
 <span data-ttu-id="03799-108">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="03799-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="03799-109">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="03799-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="03799-110">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: dati numerici in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="03799-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace aw = "http://www.adatum.com";  
IEnumerable<decimal> prices =  
    from el in root.Elements(aw + "Data")  
    let price = (decimal)el.Element(aw + "Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="03799-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="03799-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="03799-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03799-112">See also</span></span>

- [<span data-ttu-id="03799-113">Ordinamento dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="03799-113">Sorting Data (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/sorting-data.md)
