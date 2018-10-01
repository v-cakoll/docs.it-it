---
title: "Procedura: Trovare l'elemento radice (XPath-LINQ to XML) (C#)"
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: a0197a34f2e9d1b42a71d3c8cb1a4281ba495c4f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195621"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="6587c-102">Procedura: Trovare l'elemento radice (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6587c-102">How to: Find the Root Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="6587c-103">In questo argomento viene illustrato come ottenere l'elemento radice con XPath e [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6587c-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="6587c-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="6587c-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="6587c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6587c-105">Example</span></span>  
 <span data-ttu-id="6587c-106">In questo esempio viene trovato l'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="6587c-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="6587c-107">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6587c-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="6587c-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="6587c-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
PurchaseOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="6587c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6587c-109">See Also</span></span>

- [<span data-ttu-id="6587c-110">LINQ to XML per gli utenti di XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="6587c-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
