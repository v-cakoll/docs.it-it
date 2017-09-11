---
title: 'Procedura: Trovare un elemento figlio (XPath-LINQ to XML) (C#)'
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
ms.assetid: 4fa6182d-6196-4ed1-9c9e-82949ff89c71
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8950b74ff05b7a5383a570c971161f88a261d7ea
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="63349-102">Procedura: Trovare un elemento figlio (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="63349-102">How to: Find a Child Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="63349-103">Questo argomento confronta l'asse degli elementi figlio XPath con il metodo [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="63349-103">This topic compares the XPath child element axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  
  
 <span data-ttu-id="63349-104">L'espressione XPath è `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="63349-104">The XPath expression is `DeliveryNotes`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63349-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="63349-105">Example</span></span>  
 <span data-ttu-id="63349-106">In questo esempio viene trovato l'elemento figlio `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="63349-106">This example finds the child element `DeliveryNotes`.</span></span>  
  
 <span data-ttu-id="63349-107">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="63349-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="63349-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="63349-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63349-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63349-109">See Also</span></span>  
 [<span data-ttu-id="63349-110">LINQ to XML per gli utenti di XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="63349-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

