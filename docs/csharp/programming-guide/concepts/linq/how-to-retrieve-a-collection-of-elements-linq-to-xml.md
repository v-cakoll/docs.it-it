---
title: 'Procedura: recuperare una raccolta di elementi (LINQ to XML) (C#)'
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
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 24a9eee962554ac6082dd4df5676d7e169912583
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="cda12-102">Procedura: recuperare una raccolta di elementi (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="cda12-102">How to: Retrieve a Collection of Elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="cda12-103">In questo argomento viene illustrato il metodo <xref:System.Xml.Linq.XContainer.Elements%2A>,</span><span class="sxs-lookup"><span data-stu-id="cda12-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="cda12-104">che consente di recuperare una raccolta degli elementi figlio di un elemento.</span><span class="sxs-lookup"><span data-stu-id="cda12-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda12-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="cda12-105">Example</span></span>  
 <span data-ttu-id="cda12-106">In questo esempio vengono scorsi gli elementi figlio dell'elemento `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="cda12-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="cda12-107">Questo esempio usa il documento XML seguente: [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="cda12-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="cda12-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="cda12-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="cda12-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cda12-109">See Also</span></span>  
 [<span data-ttu-id="cda12-110">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="cda12-110">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)

