---
title: 'Procedura: Trovare elementi discendenti (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: c75b797f876df7696a26bb39792fa7cc7566e6f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320989"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="04f1b-102">Procedura: Trovare elementi discendenti (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="04f1b-102">How to: Find Descendant Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="04f1b-103">In questo argomento viene illustrato come ottenere gli elementi discendenti con un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="04f1b-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="04f1b-104">L'espressione XPath è `//Name`.</span><span class="sxs-lookup"><span data-stu-id="04f1b-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04f1b-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="04f1b-105">Example</span></span>  
 <span data-ttu-id="04f1b-106">In questo esempio vengono trovati tutti i discendenti denominati `Name`.</span><span class="sxs-lookup"><span data-stu-id="04f1b-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="04f1b-107">Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="04f1b-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="04f1b-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="04f1b-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="04f1b-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04f1b-109">See Also</span></span>  
 [<span data-ttu-id="04f1b-110">LINQ to XML per gli utenti di XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="04f1b-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
