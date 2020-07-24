---
title: Come trovare l'elemento radice (XPath-LINQ to XML) (C#)
description: In questo esempio di C# viene confrontato XPath con LINQ to XML come ottenere l'elemento radice per un documento XML di esempio.
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 220899823210c5cd6e9834541ca87e4d8394b4ff
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105186"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="34dac-103">Come trovare l'elemento radice (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="34dac-103">How to find the root element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="34dac-104">In questo argomento viene illustrato come ottenere l'elemento radice con XPath e [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34dac-104">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="34dac-105">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="34dac-105">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="34dac-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="34dac-106">Example</span></span>  
 <span data-ttu-id="34dac-107">In questo esempio viene trovato l'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="34dac-107">This example finds the root element.</span></span>  
  
 <span data-ttu-id="34dac-108">Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="34dac-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="34dac-109">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="34dac-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
PurchaseOrders  
```  
