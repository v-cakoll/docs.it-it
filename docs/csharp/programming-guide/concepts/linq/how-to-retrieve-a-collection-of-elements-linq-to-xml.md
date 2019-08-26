---
title: 'Procedura: Recuperare una raccolta di elementi (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 0ca40b77a78f155292dfbb26471442450bf16b9b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592635"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="25205-102">Procedura: Recuperare una raccolta di elementi (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="25205-102">How to: Retrieve a Collection of Elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="25205-103">In questo argomento viene illustrato il metodo <xref:System.Xml.Linq.XContainer.Elements%2A>,</span><span class="sxs-lookup"><span data-stu-id="25205-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="25205-104">che consente di recuperare una raccolta degli elementi figlio di un elemento.</span><span class="sxs-lookup"><span data-stu-id="25205-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25205-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="25205-105">Example</span></span>  
 <span data-ttu-id="25205-106">In questo esempio vengono scorsi gli elementi figlio dell'elemento `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="25205-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="25205-107">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="25205-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="25205-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="25205-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="25205-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25205-109">See also</span></span>

- [<span data-ttu-id="25205-110">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="25205-110">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
