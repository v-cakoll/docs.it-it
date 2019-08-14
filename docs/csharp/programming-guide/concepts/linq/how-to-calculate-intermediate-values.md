---
title: 'Procedura: Calcolare valori intermedi (C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 6fb04e1222563e557172edad7953c4646adafefd
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710167"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="20c2e-102">Procedura: Calcolare valori intermedi (C#)</span><span class="sxs-lookup"><span data-stu-id="20c2e-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="20c2e-103">In questo esempio viene illustrato come calcolare valori intermedi che è possibile usare in operazioni di ordinamento, filtro e selezione.</span><span class="sxs-lookup"><span data-stu-id="20c2e-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20c2e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="20c2e-104">Example</span></span>  
 <span data-ttu-id="20c2e-105">Nell'esempio seguente viene usata la clausola `Let`.</span><span class="sxs-lookup"><span data-stu-id="20c2e-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="20c2e-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="20c2e-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="20c2e-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="20c2e-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="20c2e-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="20c2e-108">Example</span></span>  
 <span data-ttu-id="20c2e-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="20c2e-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="20c2e-110">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="20c2e-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="20c2e-111">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: dati numerici in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="20c2e-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="20c2e-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="20c2e-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
