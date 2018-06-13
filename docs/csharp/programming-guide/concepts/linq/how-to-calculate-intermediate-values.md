---
title: 'Procedura: Calcolare valori intermedi (C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 47b84e7186cf579d9229dc82b12ed621e1f58e2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316998"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="144fd-102">Procedura: Calcolare valori intermedi (C#)</span><span class="sxs-lookup"><span data-stu-id="144fd-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="144fd-103">In questo esempio viene illustrato come calcolare valori intermedi che è possibile usare in operazioni di ordinamento, filtro e selezione.</span><span class="sxs-lookup"><span data-stu-id="144fd-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="144fd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="144fd-104">Example</span></span>  
 <span data-ttu-id="144fd-105">Nell'esempio seguente viene usata la clausola `Let`.</span><span class="sxs-lookup"><span data-stu-id="144fd-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="144fd-106">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="144fd-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="144fd-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="144fd-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="144fd-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="144fd-108">Example</span></span>  
 <span data-ttu-id="144fd-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="144fd-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="144fd-110">Per altre informazioni, vedere [Utilizzo degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="144fd-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="144fd-111">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="144fd-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="144fd-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="144fd-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="144fd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="144fd-113">See Also</span></span>  
 [<span data-ttu-id="144fd-114">Query di base (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="144fd-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
