---
title: 'Procedura: Trovare un elemento figlio (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 4fa6182d-6196-4ed1-9c9e-82949ff89c71
ms.openlocfilehash: 315cf782aa886bba484eb1fb06a4c4dbcf3cb4df
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593716"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="16bb9-102">Procedura: Trovare un elemento figlio (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="16bb9-102">How to: Find a Child Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="16bb9-103">Questo argomento confronta l'asse degli elementi figlio XPath con il metodo [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="16bb9-103">This topic compares the XPath child element axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  
  
 <span data-ttu-id="16bb9-104">L'espressione XPath è `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="16bb9-104">The XPath expression is `DeliveryNotes`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16bb9-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="16bb9-105">Example</span></span>  
 <span data-ttu-id="16bb9-106">In questo esempio viene trovato l'elemento figlio `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="16bb9-106">This example finds the child element `DeliveryNotes`.</span></span>  
  
 <span data-ttu-id="16bb9-107">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="16bb9-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="16bb9-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="16bb9-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  