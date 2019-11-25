---
title: Come trovare tutti i nodi in uno spazio deiC#nomi ()
ms.date: 07/20/2015
ms.assetid: 3a38b913-a53e-4d0e-a19d-8782bffd3364
ms.openlocfilehash: 408f4207798720428d0dd3821d33fd3edf2f897e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141190"
---
# <a name="how-to-find-all-nodes-in-a-namespace-c"></a><span data-ttu-id="3c28b-102">Come trovare tutti i nodi in uno spazio deiC#nomi ()</span><span class="sxs-lookup"><span data-stu-id="3c28b-102">How to find all nodes in a namespace (C#)</span></span>
<span data-ttu-id="3c28b-103">È possibile applicare un filtro sullo spazio dei nomi di ogni elemento o attributo per trovare tutti i nodi inclusi in questo determinato spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3c28b-103">You can filter on the namespace of each element or attribute to find all nodes in that particular namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c28b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c28b-104">Example</span></span>  
 <span data-ttu-id="3c28b-105">Nell'esempio seguente viene creato un albero XML con due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3c28b-105">The following example creates an XML tree with two namespaces.</span></span> <span data-ttu-id="3c28b-106">L'albero viene quindi scorso e vengono stampati i nomi di tutti gli elementi e gli attributi inclusi in uno dei tali spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3c28b-106">It then iterates through the tree and prints the names of all the elements and attributes in one of those namespaces.</span></span>  
  
```csharp  
string markup = @"<aw:Root xmlns:aw='http://www.adventure-works.com' xmlns:fc='www.fourthcoffee.com'>  
  <fc:Child1>abc</fc:Child1>  
  <fc:Child2>def</fc:Child2>  
  <aw:Child3>ghi</aw:Child3>  
  <fc:Child4>  
    <fc:GrandChild1>jkl</fc:GrandChild1>  
    <aw:GrandChild2>mno</aw:GrandChild2>  
  </fc:Child4>  
</aw:Root>";  
XElement xmlTree = XElement.Parse(markup);  
Console.WriteLine("Nodes in the http://www.adventure-works.com namespace");  
IEnumerable<XElement> awElements =  
    from el in xmlTree.Descendants()  
    where el.Name.Namespace == "http://www.adventure-works.com"  
    select el;  
foreach (XElement el in awElements)  
    Console.WriteLine(el.Name.ToString());  
```  
  
 <span data-ttu-id="3c28b-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3c28b-107">This code produces the following output:</span></span>  
  
```output  
Nodes in the http://www.adventure-works.com namespace  
{http://www.adventure-works.com}Child3  
{http://www.adventure-works.com}GrandChild2  
```  
  
## <a name="example"></a><span data-ttu-id="3c28b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c28b-108">Example</span></span>  
 <span data-ttu-id="3c28b-109">Il file XML cui accede la seguente query contiene gli ordini di acquisto in due spazi dei nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="3c28b-109">The XML file accessed by the following query contains purchase orders in two different namespaces.</span></span> <span data-ttu-id="3c28b-110">Con la query viene creato un nuovo albero contenente solo gli elementi di uno degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3c28b-110">The query creates a new tree with just the elements in one of the namespaces.</span></span>  
  
 <span data-ttu-id="3c28b-111">Questo esempio usa il documento XML seguente: [File XML di esempio: ordini di acquisto consolidati](./sample-xml-file-consolidated-purchase-orders.md).</span><span class="sxs-lookup"><span data-stu-id="3c28b-111">This example uses the following XML document: [Sample XML File: Consolidated Purchase Orders](./sample-xml-file-consolidated-purchase-orders.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("ConsolidatedPurchaseOrders.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement newTree = new XElement("Root",  
    from el in cpo.Root.Elements()  
    where el.Name.Namespace == aw  
    select el  
);  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="3c28b-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3c28b-112">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:PurchaseOrder PONumber="11223" Date="2000-01-15" xmlns:aw="http://www.adventure-works.com">  
    <aw:ShippingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:ShippingAddress>  
    <aw:BillingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:BillingAddress>  
    <aw:DeliveryInstructions>Ship only complete order.</aw:DeliveryInstructions>  
    <aw:Item PartNum="LIT-01">  
      <aw:ProductID>Litware Networking Card</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>20.99</aw:Price>  
    </aw:Item>  
    <aw:Item PartNum="LIT-25">  
      <aw:ProductID>Litware 17in LCD Monitor</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>199.99</aw:Price>  
    </aw:Item>  
  </aw:PurchaseOrder>  
</Root>  
```  
