---
title: 'Procedura: Concatenare chiamate al metodo dell''asse (LINQ to XML) (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 17793e0620969125de202de7edea89d748b98ee7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a><span data-ttu-id="4cae8-102">Procedura: Concatenare chiamate al metodo dell'asse (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="4cae8-102">How to: Chain Axis Method Calls (LINQ to XML) (C#)</span></span>
<span data-ttu-id="4cae8-103">Uno schema comune da usare nel codice consiste nel chiamare un metodo dell'asse e quindi chiamare uno degli assi del metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="4cae8-103">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="4cae8-104">Sono disponibili due assi denominati `Elements` che restituiscono una raccolta di elementi: il metodo <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> e il metodo <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4cae8-104">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="4cae8-105">È possibile combinare questi due assi per individuare tutti gli elementi con un nome specificato a una data profondità dell'albero.</span><span class="sxs-lookup"><span data-stu-id="4cae8-105">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cae8-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4cae8-106">Example</span></span>  
 <span data-ttu-id="4cae8-107">In questo esempio vengono usati <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> e <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> per individuare tutti gli elementi `Name` inclusi in tutti gli elementi `Address` di tutti gli elementi `PurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="4cae8-107">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="4cae8-108">Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4cae8-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="4cae8-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4cae8-109">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="4cae8-110">Questo esempio viene eseguito correttamente perché una delle implementazioni dell'asse `Elements` è un metodo di estensione su <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="4cae8-110">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="4cae8-111"><xref:System.Xml.Linq.XElement> deriva da <xref:System.Xml.Linq.XContainer>, pertanto è possibile chiamare il metodo <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> sui risultati di una chiamata al metodo <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4cae8-111"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cae8-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4cae8-112">Example</span></span>  
 <span data-ttu-id="4cae8-113">Talvolta si desidera recuperare tutti gli elementi presenti a una data profondità dell'elemento in cui possono o meno esistere elementi predecessori intermedi.</span><span class="sxs-lookup"><span data-stu-id="4cae8-113">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="4cae8-114">Ad esempio, nel documento seguente può essere necessario recuperare tutti gli elementi `ConfigParameter` che sono elementi figli dell'elemento `Customer`, ma non `ConfigParameter` che è un elemento figlio dell'elemento `Root`.</span><span class="sxs-lookup"><span data-stu-id="4cae8-114">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
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
  
 <span data-ttu-id="4cae8-115">A tale scopo, è possibile usare l'asse <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="4cae8-115">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> axis, as follows:</span></span>  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =   
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 <span data-ttu-id="4cae8-116">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4cae8-116">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="4cae8-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="4cae8-117">Example</span></span>  
 <span data-ttu-id="4cae8-118">Nell'esempio seguente è illustrata la stessa tecnica per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4cae8-118">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="4cae8-119">Per altre informazioni, vedere [Uso degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="4cae8-119">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="4cae8-120">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="4cae8-120">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="4cae8-121">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4cae8-121">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cae8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cae8-122">See Also</span></span>  
 [<span data-ttu-id="4cae8-123">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="4cae8-123">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)

