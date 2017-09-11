---
title: 'Procedura: trovare un elenco di elementi figlio (XPath-LINQ to XML) (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 2868abfd-9f7b-412a-9cb5-f643f0fed146
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 23e35e339f7330815980216b525bb1727f60cbfc
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-find-a-list-of-child-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="e50e2-102">Procedura: trovare un elenco di elementi figlio (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e50e2-102">How to: Find a List of Child Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="e50e2-103">Questo argomento vengono confrontate l'asse degli elementi figlio XPath e il [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A>asse.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="e50e2-103">This topic compares the XPath child elements axis to the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>  
  
 <span data-ttu-id="e50e2-104">L'espressione XPath è: `./*`.</span><span class="sxs-lookup"><span data-stu-id="e50e2-104">The XPath expression is: `./*`</span></span>  
  
## <a name="example"></a><span data-ttu-id="e50e2-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e50e2-105">Example</span></span>  
 <span data-ttu-id="e50e2-106">In questo esempio vengono individuati tutti gli elementi figlio dell'elemento `Address`.</span><span class="sxs-lookup"><span data-stu-id="e50e2-106">This example finds all of the child elements of the `Address` element.</span></span>  
  
 <span data-ttu-id="e50e2-107">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e50e2-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.<Address>.FirstOrDefault  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po.Elements()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("./*")  
  
If (list1.Count() = list2.Count()) AndAlso _  
    (list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="e50e2-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="e50e2-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Street>123 Maple Street</Street>  
<City>Mill Valley</City>  
<State>CA</State>  
<Zip>10999</Zip>  
<Country>USA</Country>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e50e2-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e50e2-109">See Also</span></span>  
 [<span data-ttu-id="e50e2-110">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e50e2-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

