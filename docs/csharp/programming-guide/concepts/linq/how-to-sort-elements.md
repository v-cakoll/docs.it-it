---
title: Come ordinare gli elementi (c'è)How to sort elements (C
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 7fad9fcb43905072c88a5704c56672917bfc377c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347370"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="accdd-102">Come ordinare gli elementi (c'è)How to sort elements (C</span><span class="sxs-lookup"><span data-stu-id="accdd-102">How to sort elements (C#)</span></span>
<span data-ttu-id="accdd-103">In questo esempio viene illustrato come scrivere una query che ordina i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="accdd-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="accdd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="accdd-104">Example</span></span>  
 <span data-ttu-id="accdd-105">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="accdd-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="accdd-106">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="accdd-106">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="accdd-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="accdd-107">Example</span></span>  
 <span data-ttu-id="accdd-108">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="accdd-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="accdd-109">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="accdd-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="accdd-110">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici in uno spazio dei nomi](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="accdd-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="accdd-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="accdd-111">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="accdd-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="accdd-112">See also</span></span>

- [<span data-ttu-id="accdd-113">Ordinamento dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="accdd-113">Sorting Data (C#)</span></span>](./sorting-data.md)
