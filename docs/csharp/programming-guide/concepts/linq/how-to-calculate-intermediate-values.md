---
title: 'Procedura: Calcolare valori intermedi (C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 7b2dfc4e26fc7648cbd93b1e590079e4b105ad43
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594139"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="b2ba1-102">Procedura: Calcolare valori intermedi (C#)</span><span class="sxs-lookup"><span data-stu-id="b2ba1-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="b2ba1-103">In questo esempio viene illustrato come calcolare valori intermedi che è possibile usare in operazioni di ordinamento, filtro e selezione.</span><span class="sxs-lookup"><span data-stu-id="b2ba1-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2ba1-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2ba1-104">Example</span></span>  
 <span data-ttu-id="b2ba1-105">Nell'esempio seguente viene usata la clausola `Let`.</span><span class="sxs-lookup"><span data-stu-id="b2ba1-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="b2ba1-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: dati numerici (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b2ba1-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="b2ba1-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b2ba1-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="b2ba1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2ba1-108">Example</span></span>  
 <span data-ttu-id="b2ba1-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b2ba1-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b2ba1-110">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b2ba1-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b2ba1-111">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: dati numerici in uno spazio dei nomi](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b2ba1-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="b2ba1-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b2ba1-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
