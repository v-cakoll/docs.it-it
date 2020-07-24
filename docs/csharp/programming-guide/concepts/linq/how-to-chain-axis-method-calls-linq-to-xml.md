---
title: Come concatenare le chiamate al metodo axis (LINQ to XML) (C#)
description: Questi LINQ to XML esempi in C# illustrano le chiamate a due assi per trovare tutti gli elementi con un nome specificato a una profondità specificata nell'albero.
ms.date: 07/20/2015
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
ms.openlocfilehash: f26efd2ca918fd36916eb4f01462af70066219a0
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105384"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a><span data-ttu-id="21552-103">Come concatenare le chiamate al metodo axis (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="21552-103">How to chain axis method calls (LINQ to XML) (C#)</span></span>
<span data-ttu-id="21552-104">Uno schema comune da usare nel codice consiste nel chiamare un metodo dell'asse e quindi chiamare uno degli assi del metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="21552-104">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="21552-105">Sono disponibili due assi denominati `Elements` che restituiscono una raccolta di elementi: il metodo <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> e il metodo <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="21552-105">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="21552-106">È possibile combinare questi due assi per individuare tutti gli elementi con un nome specificato a una data profondità dell'albero.</span><span class="sxs-lookup"><span data-stu-id="21552-106">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21552-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="21552-107">Example</span></span>  
 <span data-ttu-id="21552-108">In questo esempio vengono usati <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> e <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> per individuare tutti gli elementi `Name` inclusi in tutti gli elementi `Address` di tutti gli elementi `PurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="21552-108">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="21552-109">Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="21552-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XElement purchaseOrders = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements("PurchaseOrder")  
        .Elements("Address")  
        .Elements("Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="21552-110">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="21552-110">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="21552-111">Questo esempio viene eseguito correttamente perché una delle implementazioni dell'asse `Elements` è un metodo di estensione su <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="21552-111">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="21552-112"><xref:System.Xml.Linq.XElement> deriva da <xref:System.Xml.Linq.XContainer>, pertanto è possibile chiamare il metodo <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> sui risultati di una chiamata al metodo <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="21552-112"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21552-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="21552-113">Example</span></span>  
 <span data-ttu-id="21552-114">Talvolta si desidera recuperare tutti gli elementi presenti a una data profondità dell'elemento in cui possono o meno esistere elementi predecessori intermedi.</span><span class="sxs-lookup"><span data-stu-id="21552-114">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="21552-115">Ad esempio, nel documento seguente può essere necessario recuperare tutti gli elementi `ConfigParameter` che sono elementi figli dell'elemento `Customer`, ma non `ConfigParameter` che è un elemento figlio dell'elemento `Root`.</span><span class="sxs-lookup"><span data-stu-id="21552-115">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 <span data-ttu-id="21552-116">A tale scopo, è possibile usare l'asse <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="21552-116">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> axis, as follows:</span></span>  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 <span data-ttu-id="21552-117">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="21552-117">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="21552-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="21552-118">Example</span></span>  
 <span data-ttu-id="21552-119">Nell'esempio seguente è illustrata la stessa tecnica per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="21552-119">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="21552-120">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="21552-120">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="21552-121">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto in uno spazio dei nomi](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="21552-121">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement purchaseOrders = XElement.Load("PurchaseOrdersInNamespace.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements(aw + "PurchaseOrder")  
        .Elements(aw + "Address")  
        .Elements(aw + "Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="21552-122">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="21552-122">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="21552-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21552-123">See also</span></span>

- [<span data-ttu-id="21552-124">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="21552-124">LINQ to XML Axes (C#)</span></span>](linq-to-xml-axes-overview.md)
