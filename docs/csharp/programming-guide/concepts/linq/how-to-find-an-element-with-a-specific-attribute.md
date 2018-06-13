---
title: 'Procedura: Trovare un elemento con un attributo specifico (C#)'
ms.date: 07/20/2015
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
ms.openlocfilehash: 53296b2ace23bbc57deb0f5e7c0b23ebfc9613d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325695"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-c"></a><span data-ttu-id="d334b-102">Procedura: Trovare un elemento con un attributo specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="d334b-102">How to: Find an Element with a Specific Attribute (C#)</span></span>
<span data-ttu-id="d334b-103">In questo argomento viene illustrato come trovare un elemento che include un attributo con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="d334b-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d334b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d334b-104">Example</span></span>  
 <span data-ttu-id="d334b-105">Nell'esempio viene illustrato come trovare l'elemento `Address` contenente un attributo `Type` con valore "Billing".</span><span class="sxs-lookup"><span data-stu-id="d334b-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="d334b-106">Questo esempio usa il documento XML seguente: [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="d334b-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> address =  
    from el in root.Elements("Address")  
    where (string)el.Attribute("Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="d334b-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="d334b-107">This code produces the following output:</span></span>  
  
```xml  
<Address Type="Billing">  
  <Name>Tai Yee</Name>  
  <Street>8 Oak Avenue</Street>  
  <City>Old Town</City>  
  <State>PA</State>  
  <Zip>95819</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
## <a name="example"></a><span data-ttu-id="d334b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="d334b-108">Example</span></span>  
 <span data-ttu-id="d334b-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d334b-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="d334b-110">Per altre informazioni, vedere [Utilizzo degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="d334b-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="d334b-111">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d334b-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> address =  
    from el in root.Elements(aw + "Address")  
    where (string)el.Attribute(aw + "Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="d334b-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="d334b-112">This code produces the following output:</span></span>  
  
```xml  
<aw:Address aw:Type="Billing" xmlns:aw="http://www.adventure-works.com">  
  <aw:Name>Tai Yee</aw:Name>  
  <aw:Street>8 Oak Avenue</aw:Street>  
  <aw:City>Old Town</aw:City>  
  <aw:State>PA</aw:State>  
  <aw:Zip>95819</aw:Zip>  
  <aw:Country>USA</aw:Country>  
</aw:Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d334b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d334b-113">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="d334b-114">Query di base (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d334b-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="d334b-115">Cenni preliminari sugli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="d334b-115">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="d334b-116">Operazioni di proiezione (C#)</span><span class="sxs-lookup"><span data-stu-id="d334b-116">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
