---
title: 'Procedura: Trovare elementi in uno spazio dei nomi (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: c7cb3b77-3424-4b54-9efa-4dc715948e41
ms.openlocfilehash: 3663516e6b6289fe3b1d0599ff3ed4b7dad6a80a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405196"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="d6b6d-102">Procedura: trovare elementi in uno spazio dei nomi (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6b6d-102">How to: Find Elements in a Namespace (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="d6b6d-103">Le espressioni XPath consentono di trovare nodi in un determinato spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-103">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="d6b6d-104">Per specificare gli spazi dei nomi, nelle espressioni XPath si usano prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-104">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="d6b6d-105">Per analizzare un'espressione XPath che contiene prefissi di spazio dei nomi, è necessario passare ai metodi XPath un oggetto che implementa <xref:System.Xml.IXmlNamespaceResolver>.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-105">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="d6b6d-106">In questo esempio viene utilizzato <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-106">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>  
  
 <span data-ttu-id="d6b6d-107">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="d6b6d-107">The XPath expression is:</span></span>  
  
 `./aw:*`  
  
## <a name="example"></a><span data-ttu-id="d6b6d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6b6d-108">Example</span></span>  
 <span data-ttu-id="d6b6d-109">Nell'esempio seguente viene letto un albero XML contenente due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-109">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="d6b6d-110">Per leggere il documento XML viene usato <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-110">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="d6b6d-111">Quindi si ottiene <xref:System.Xml.XmlNameTable> da <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlNamespaceManager> da <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-111">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="d6b6d-112">Viene usato <xref:System.Xml.XmlNamespaceManager> quando si selezionano gli elementi.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-112">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>  
  
```vb  
Dim reader As XmlReader = _  
        XmlReader.Create("ConsolidatedPurchaseOrders.xml")  
Dim root As XElement = XElement.Load(reader)  
Dim nameTable As XmlNameTable = reader.NameTable  
Dim namespaceManager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)  
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com")  
  
Dim list1 As IEnumerable(Of XElement) = _  
        root.XPathSelectElements("./aw:*", namespaceManager)  
Dim list2 As IEnumerable(Of XElement) = _  
    From el In root.Elements() _  
    Where el.Name.Namespace = "http://www.adventure-works.com" _  
    Select el  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list2  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="d6b6d-113">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="d6b6d-113">This example produces the following output:</span></span>  
  
```console
Results are identical  
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
```  
  
## <a name="see-also"></a><span data-ttu-id="d6b6d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6b6d-114">See also</span></span>

- [<span data-ttu-id="d6b6d-115">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6b6d-115">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)
