---
title: 'Procedura: Ordinare elementi (C#)'
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
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a5c17b13f6f637559e2f99426b71947e795e0516
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="00dac-102">Procedura: Ordinare elementi (C#)</span><span class="sxs-lookup"><span data-stu-id="00dac-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="00dac-103">In questo esempio viene illustrato come scrivere una query che ordina i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="00dac-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00dac-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="00dac-104">Example</span></span>  
 <span data-ttu-id="00dac-105">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="00dac-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="00dac-106">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="00dac-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="00dac-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="00dac-107">Example</span></span>  
 <span data-ttu-id="00dac-108">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="00dac-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="00dac-109">Per altre informazioni, vedere [Uso degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="00dac-109">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="00dac-110">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="00dac-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="00dac-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="00dac-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="00dac-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00dac-112">See Also</span></span>  
 <span data-ttu-id="00dac-113">[Ordinamento dei dati (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md) </span><span class="sxs-lookup"><span data-stu-id="00dac-113">[Sorting Data (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md) </span></span>  
 [<span data-ttu-id="00dac-114">Query di base (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="00dac-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

