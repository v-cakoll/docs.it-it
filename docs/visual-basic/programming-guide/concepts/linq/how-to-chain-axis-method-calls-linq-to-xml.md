---
title: 'Procedura: concatenare chiamate al metodo Axis (LINQ to XML) (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: e4e22942-39bd-460f-b3c0-9f09e53d3aa9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 4997f7e91f968f080c22ca9d3a204c748758f832
ms.contentlocale: it-it
ms.lasthandoff: 06/01/2017


---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-visual-basic"></a><span data-ttu-id="5548d-102">Procedura: concatenare chiamate al metodo Axis (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5548d-102">How to: Chain Axis Method Calls (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="5548d-103">Uno schema comune da usare nel codice consiste nel chiamare un metodo dell'asse e quindi chiamare uno degli assi del metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="5548d-103">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="5548d-104">Sono disponibili due assi con il nome del `Elements` che restituiscono una raccolta di elementi: il <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>(metodo) e <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>metodo.</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5548d-104">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="5548d-105">È possibile combinare questi due assi per individuare tutti gli elementi con un nome specificato a una data profondità dell'albero.</span><span class="sxs-lookup"><span data-stu-id="5548d-105">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5548d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5548d-106">Example</span></span>  
 <span data-ttu-id="5548d-107">Questo esempio viene utilizzato <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>e <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>per individuare tutti `Name` gli elementi in tutte `Address` gli elementi in tutte `PurchaseOrder` elementi.</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5548d-107">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="5548d-108">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5548d-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim purchaseOrders As XElement = XElement.Load("PurchaseOrders.xml")  
Dim names As IEnumerable(Of XElement) = _  
    From el In purchaseOrders.<PurchaseOrder>.<Address>.<Name> _  
    Select el  
For Each e As XElement In names  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="5548d-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="5548d-109">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="5548d-110">Questo procedimento funziona perché una delle implementazioni di `Elements` asse è un metodo di estensione in <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5548d-110">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="5548d-111"><xref:System.Xml.Linq.XElement>deriva da <xref:System.Xml.Linq.XContainer>, pertanto è possibile chiamare il <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>sui risultati di una chiamata al metodo di <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>(metodo).</xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="5548d-111"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5548d-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="5548d-112">Example</span></span>  
 <span data-ttu-id="5548d-113">Talvolta si desidera recuperare tutti gli elementi presenti a una data profondità dell'elemento in cui possono o meno esistere elementi predecessori intermedi.</span><span class="sxs-lookup"><span data-stu-id="5548d-113">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="5548d-114">Ad esempio, nel documento seguente può essere necessario recuperare tutti gli elementi `ConfigParameter` che sono elementi figli dell'elemento `Customer`, ma non `ConfigParameter` che è un elemento figlio dell'elemento `Root`.</span><span class="sxs-lookup"><span data-stu-id="5548d-114">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
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
  
 <span data-ttu-id="5548d-115">A tale scopo, è possibile utilizzare il <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>asse, come indicato di seguito:</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5548d-115">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> axis, as follows:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Irregular.xml")  
Dim configParameters As IEnumerable(Of XElement) = _  
    root.<Customer>.<Config>.<ConfigParameter>  
For Each cp As XElement In configParameters  
    Console.WriteLine(cp)  
Next  
```  
  
 <span data-ttu-id="5548d-116">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="5548d-116">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="5548d-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="5548d-117">Example</span></span>  
 <span data-ttu-id="5548d-118">Nell'esempio seguente è illustrata la stessa tecnica per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5548d-118">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="5548d-119">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="5548d-119">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="5548d-120">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: più ordini di acquisto in un Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="5548d-120">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim purchaseOrders As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim names As IEnumerable(Of XElement) = _  
            From el In purchaseOrders.<aw:PurchaseOrder>.<aw:Address>.<aw:Name> _  
            Select el  
        For Each e As XElement In names  
            Console.WriteLine(e)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="5548d-121">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="5548d-121">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5548d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5548d-122">See Also</span></span>  
 [<span data-ttu-id="5548d-123">Assi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5548d-123">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
