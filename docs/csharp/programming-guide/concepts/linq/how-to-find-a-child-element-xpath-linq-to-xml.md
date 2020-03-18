---
title: Come trovare un elemento figlio (XPath-LINQ to XML) (C
ms.date: 07/20/2015
ms.assetid: 4fa6182d-6196-4ed1-9c9e-82949ff89c71
ms.openlocfilehash: 37ce6c9d91d4edf2576ccddabd1d7f14a96b0a33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141242"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="3569a-102">Come trovare un elemento figlio (XPath-LINQ to XML) (C</span><span class="sxs-lookup"><span data-stu-id="3569a-102">How to find a child element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="3569a-103">In questo argomento viene confrontato l'asse degli elementi figlio XPath con il [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="3569a-103">This topic compares the XPath child element axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  
  
 <span data-ttu-id="3569a-104">L'espressione XPath è `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="3569a-104">The XPath expression is `DeliveryNotes`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3569a-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="3569a-105">Example</span></span>  
 <span data-ttu-id="3569a-106">In questo esempio viene trovato l'elemento figlio `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="3569a-106">This example finds the child element `DeliveryNotes`.</span></span>  
  
 <span data-ttu-id="3569a-107">Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3569a-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder");  
  
// LINQ to XML query  
XElement el1 = po.Element("DeliveryNotes");  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("DeliveryNotes");  
// same as "child::DeliveryNotes"  
// same as "./DeliveryNotes"  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 <span data-ttu-id="3569a-108">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="3569a-108">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  