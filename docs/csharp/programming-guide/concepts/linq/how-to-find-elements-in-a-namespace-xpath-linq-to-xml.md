---
title: 'Procedura: Trovare elementi in uno spazio dei nomi (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: cae1c4ac-6cd5-46cf-9b1c-bd85bc9b7ea9
ms.openlocfilehash: a0375641f9f5e75c51fe27936c07c32020e5dc0d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505745"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-c"></a><span data-ttu-id="a6e75-102">Procedura: Trovare elementi in uno spazio dei nomi (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a6e75-102">How to: Find Elements in a Namespace (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="a6e75-103">Le espressioni XPath consentono di trovare nodi in un determinato spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a6e75-103">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="a6e75-104">Per specificare gli spazi dei nomi, nelle espressioni XPath si usano prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a6e75-104">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="a6e75-105">Per analizzare un'espressione XPath che contiene prefissi di spazio dei nomi, è necessario passare ai metodi XPath un oggetto che implementa <xref:System.Xml.IXmlNamespaceResolver>.</span><span class="sxs-lookup"><span data-stu-id="a6e75-105">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="a6e75-106">In questo esempio viene usato <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="a6e75-106">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>  
  
 <span data-ttu-id="a6e75-107">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="a6e75-107">The XPath expression is:</span></span>  
  
 `./aw:*`  
  
## <a name="example"></a><span data-ttu-id="a6e75-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6e75-108">Example</span></span>  
 <span data-ttu-id="a6e75-109">Nell'esempio seguente viene letto un albero XML contenente due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a6e75-109">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="a6e75-110">Per leggere il documento XML viene usato <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="a6e75-110">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="a6e75-111">Quindi si ottiene <xref:System.Xml.XmlNameTable> da <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlNamespaceManager> da <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="a6e75-111">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="a6e75-112">Viene usato <xref:System.Xml.XmlNamespaceManager> quando si selezionano gli elementi.</span><span class="sxs-lookup"><span data-stu-id="a6e75-112">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>  
  
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
  
 <span data-ttu-id="a6e75-113">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="a6e75-113">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="a6e75-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6e75-114">See Also</span></span>

- [<span data-ttu-id="a6e75-115">LINQ to XML per gli utenti di XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="a6e75-115">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
