---
title: Come calcolare valori intermedi (C#)
description: In questo LINQ to XML esempio in C# viene illustrato come calcolare valori intermedi che possono essere utilizzati per l'ordinamento, il filtro e la selezione.
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: fc648f20550de13735a1f6da6b2f811fd0d39004
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103617"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="4ce44-103">Come calcolare valori intermedi (C#)</span><span class="sxs-lookup"><span data-stu-id="4ce44-103">How to calculate intermediate values (C#)</span></span>
<span data-ttu-id="4ce44-104">In questo esempio viene illustrato come calcolare valori intermedi che è possibile usare in operazioni di ordinamento, filtro e selezione.</span><span class="sxs-lookup"><span data-stu-id="4ce44-104">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ce44-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ce44-105">Example</span></span>  
 <span data-ttu-id="4ce44-106">Nell'esempio seguente viene usata la clausola `Let`.</span><span class="sxs-lookup"><span data-stu-id="4ce44-106">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="4ce44-107">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4ce44-107">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="4ce44-108">Questo codice genera l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="4ce44-108">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="4ce44-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ce44-109">Example</span></span>  
 <span data-ttu-id="4ce44-110">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4ce44-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="4ce44-111">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4ce44-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="4ce44-112">Questo esempio usa il documento XML seguente: [File XML di esempio: dati numerici in uno spazio dei nomi](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="4ce44-112">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="4ce44-113">Questo codice genera l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="4ce44-113">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
