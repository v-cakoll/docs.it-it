---
title: Come trovare gli elementi in uno spazio dei nomi (XPath-LINQ to XML) (C
ms.date: 07/20/2015
ms.assetid: cae1c4ac-6cd5-46cf-9b1c-bd85bc9b7ea9
ms.openlocfilehash: da9d819be5234a2429b6eab276f89bd0d877d4a7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141074"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-c"></a><span data-ttu-id="61438-102">Come trovare gli elementi in uno spazio dei nomi (XPath-LINQ to XML) (C</span><span class="sxs-lookup"><span data-stu-id="61438-102">How to find elements in a namespace (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="61438-103">Le espressioni XPath consentono di trovare nodi in un determinato spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="61438-103">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="61438-104">Per specificare gli spazi dei nomi, nelle espressioni XPath si usano prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="61438-104">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="61438-105">Per analizzare un'espressione XPath che contiene prefissi di spazio dei nomi, è necessario passare ai metodi XPath un oggetto che implementa <xref:System.Xml.IXmlNamespaceResolver>.</span><span class="sxs-lookup"><span data-stu-id="61438-105">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="61438-106">In questo esempio viene utilizzato <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="61438-106">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>

<span data-ttu-id="61438-107">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="61438-107">The XPath expression is:</span></span>

`./aw:*`

## <a name="example"></a><span data-ttu-id="61438-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="61438-108">Example</span></span>

<span data-ttu-id="61438-109">Nell'esempio seguente viene letto un albero XML contenente due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="61438-109">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="61438-110">Per leggere il documento XML viene usato <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="61438-110">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="61438-111">Quindi si ottiene <xref:System.Xml.XmlNameTable> da <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlNamespaceManager> da <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="61438-111">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="61438-112">Viene usato <xref:System.Xml.XmlNamespaceManager> quando si selezionano gli elementi.</span><span class="sxs-lookup"><span data-stu-id="61438-112">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>

```csharp
XmlReader reader = XmlReader.Create("ConsolidatedPurchaseOrders.xml");
XElement root = XElement.Load(reader);
XmlNameTable nameTable = reader.NameTable;
XmlNamespaceManager namespaceManager = new XmlNamespaceManager(nameTable);
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com");
IEnumerable<XElement> list1 = root.XPathSelectElements("./aw:*", namespaceManager);
IEnumerable<XElement> list2 =
    from el in root.Elements()
    where el.Name.Namespace == "http://www.adventure-works.com"
    select el;
if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list2)
    Console.WriteLine(el);
```

<span data-ttu-id="61438-113">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="61438-113">This example produces the following output:</span></span>

```output
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
