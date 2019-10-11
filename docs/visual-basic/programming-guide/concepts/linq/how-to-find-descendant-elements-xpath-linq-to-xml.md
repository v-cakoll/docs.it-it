---
title: 'Procedura: Trovare elementi discendenti (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: e7e2dc9e-bda9-420d-a5b1-4fabf1cca46b
ms.openlocfilehash: 3ee496c1a3e797a8edaf5878d9832583396a851f
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250126"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="715ca-102">Procedura: Trovare elementi discendenti (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="715ca-102">How to: Find Descendant Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="715ca-103">In questo argomento viene illustrato come ottenere gli elementi discendenti con un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="715ca-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="715ca-104">L'espressione XPath è `//Name`.</span><span class="sxs-lookup"><span data-stu-id="715ca-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="715ca-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="715ca-105">Example</span></span>  
 <span data-ttu-id="715ca-106">In questo esempio vengono trovati tutti i discendenti denominati `Name`.</span><span class="sxs-lookup"><span data-stu-id="715ca-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="715ca-107">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="715ca-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
      Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po...<Name>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("//Name")  
  
If (list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="715ca-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="715ca-108">This example produces the following output:</span></span>  
  
```console
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="715ca-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="715ca-109">See also</span></span>

- [<span data-ttu-id="715ca-110">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="715ca-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
