---
title: "Procedura: trovare l'elemento radice (XPath-LINQ to XML) (Visual Basic)"
ms.date: 07/20/2015
ms.assetid: 72c3aed5-9522-4454-a876-2070aad13f2e
ms.openlocfilehash: d8ac28b698b0c61a4d9e3beea61ff8a8e1074b88
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320589"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="b4627-102">Procedura: trovare l'elemento radice (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4627-102">How to: Find the Root Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b4627-103">In questo argomento viene illustrato come ottenere l'elemento radice con XPath e [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4627-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="b4627-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="b4627-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="b4627-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4627-105">Example</span></span>  
 <span data-ttu-id="b4627-106">In questo esempio viene trovato l'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="b4627-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="b4627-107">Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b4627-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim el1 As XElement = po.Root  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("/PurchaseOrders")  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1.Name)  
```  
  
 <span data-ttu-id="b4627-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="b4627-108">This example produces the following output:</span></span>  
  
```console  
Results are identical  
PurchaseOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4627-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4627-109">See also</span></span>

- [<span data-ttu-id="b4627-110">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4627-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
