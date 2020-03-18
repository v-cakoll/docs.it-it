---
title: Come trovare l'elemento radice (XPath-LINQ to XML) (C
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 1c5526f436b5b9d88ca359ef7e0fc04c5c3cf43c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345954"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="06824-102">Come trovare l'elemento radice (XPath-LINQ to XML) (C</span><span class="sxs-lookup"><span data-stu-id="06824-102">How to find the root element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="06824-103">In questo argomento viene illustrato come ottenere l'elemento radice con XPath e [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06824-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="06824-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="06824-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="06824-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="06824-105">Example</span></span>  
 <span data-ttu-id="06824-106">In questo esempio viene trovato l'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="06824-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="06824-107">Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="06824-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="06824-108">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="06824-108">This example produces the following output:</span></span>  
  
```output  
Results are identical  
PurchaseOrders  
```  
