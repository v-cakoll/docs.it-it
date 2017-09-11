---
title: 'Procedura: recuperare una raccolta di elementi (LINQ to XML) (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bb9cd9b3a7e30ba87c748899510794f4a66248ba
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a><span data-ttu-id="87382-102">Procedura: recuperare una raccolta di elementi (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87382-102">How to: Retrieve a Collection of Elements (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="87382-103">Questo argomento viene illustrato il <xref:System.Xml.Linq.XContainer.Elements%2A>(metodo).</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="87382-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="87382-104">che consente di recuperare una raccolta degli elementi figlio di un elemento.</span><span class="sxs-lookup"><span data-stu-id="87382-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87382-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="87382-105">Example</span></span>  
 <span data-ttu-id="87382-106">In questo esempio vengono scorsi gli elementi figlio dell'elemento `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="87382-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="87382-107">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="87382-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim childElements As IEnumerable(Of XElement)  
childElements = _  
    From el In po.Elements() _  
    Select el  
For Each el As XElement In childElements  
    Console.WriteLine("Name: " & el.Name.ToString())  
Next  
```  
  
 <span data-ttu-id="87382-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="87382-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="87382-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87382-109">See Also</span></span>  
 [<span data-ttu-id="87382-110">Assi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87382-110">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
