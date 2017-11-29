---
title: 'Procedura: trovare un elenco di elementi figlio (XPath-LINQ to XML) (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2868abfd-9f7b-412a-9cb5-f643f0fed146
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 110aa447a4804e5162eb45d3d59f12fb174e4473
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-a-list-of-child-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="afdf8-102">Procedura: trovare un elenco di elementi figlio (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afdf8-102">How to: Find a List of Child Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="afdf8-103">Questo argomento confronta l'asse degli elementi figlio XPath con l'asse [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="afdf8-103">This topic compares the XPath child elements axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>  
  
 <span data-ttu-id="afdf8-104">L'espressione XPath è: `./*`.</span><span class="sxs-lookup"><span data-stu-id="afdf8-104">The XPath expression is: `./*`</span></span>  
  
## <a name="example"></a><span data-ttu-id="afdf8-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="afdf8-105">Example</span></span>  
 <span data-ttu-id="afdf8-106">In questo esempio vengono individuati tutti gli elementi figlio dell'elemento `Address`.</span><span class="sxs-lookup"><span data-stu-id="afdf8-106">This example finds all of the child elements of the `Address` element.</span></span>  
  
 <span data-ttu-id="afdf8-107">Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="afdf8-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="afdf8-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="afdf8-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Street>123 Maple Street</Street>  
<City>Mill Valley</City>  
<State>CA</State>  
<Zip>10999</Zip>  
<Country>USA</Country>  
```  
  
## <a name="see-also"></a><span data-ttu-id="afdf8-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afdf8-109">See Also</span></span>  
 [<span data-ttu-id="afdf8-110">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afdf8-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
