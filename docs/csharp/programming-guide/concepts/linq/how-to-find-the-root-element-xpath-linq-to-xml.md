---
title: "Procedura: Trovare l'elemento radice (XPath-LINQ to XML) (C#)"
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 1fea4cc630dd708a86a0f0595ac727f8b8fa40af
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593385"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="655c8-102">Procedura: Trovare l'elemento radice (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="655c8-102">How to: Find the Root Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="655c8-103">In questo argomento viene illustrato come ottenere l'elemento radice con XPath e [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="655c8-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="655c8-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="655c8-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="655c8-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="655c8-105">Example</span></span>  
 <span data-ttu-id="655c8-106">In questo esempio viene trovato l'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="655c8-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="655c8-107">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="655c8-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="655c8-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="655c8-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
PurchaseOrders  
```  
