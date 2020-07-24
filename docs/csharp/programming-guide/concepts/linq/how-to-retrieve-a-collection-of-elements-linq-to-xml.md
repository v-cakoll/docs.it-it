---
title: Come recuperare una raccolta di elementi (LINQ to XML) (C#)
description: Il metodo Elements in C# recupera una raccolta di elementi figlio di un elemento. Questo LINQ to XML esempio scorre gli elementi figlio di un elemento.
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 4f9b6ae4713af9ce1a4eeb5257f57cd9724f68b2
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103356"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="7f50d-104">Come recuperare una raccolta di elementi (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7f50d-104">How to retrieve a collection of elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="7f50d-105">In questo argomento viene illustrato il metodo <xref:System.Xml.Linq.XContainer.Elements%2A>,</span><span class="sxs-lookup"><span data-stu-id="7f50d-105">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="7f50d-106">che consente di recuperare una raccolta degli elementi figlio di un elemento.</span><span class="sxs-lookup"><span data-stu-id="7f50d-106">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f50d-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f50d-107">Example</span></span>  
 <span data-ttu-id="7f50d-108">In questo esempio vengono scorsi gli elementi figlio dell'elemento `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="7f50d-108">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="7f50d-109">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="7f50d-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="7f50d-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="7f50d-110">This example produces the following output.</span></span>  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f50d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f50d-111">See also</span></span>

- [<span data-ttu-id="7f50d-112">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="7f50d-112">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
