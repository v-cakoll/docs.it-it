---
title: 'Procedura: Trovare un elemento con un attributo specifico (C#)'
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
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0852db3d3e374b267321dfbf34dff0222d355d5b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-an-element-with-a-specific-attribute-c"></a><span data-ttu-id="7bb99-102">Procedura: Trovare un elemento con un attributo specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="7bb99-102">How to: Find an Element with a Specific Attribute (C#)</span></span>
<span data-ttu-id="7bb99-103">In questo argomento viene illustrato come trovare un elemento che include un attributo con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="7bb99-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bb99-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bb99-104">Example</span></span>  
 <span data-ttu-id="7bb99-105">Nell'esempio viene illustrato come trovare l'elemento `Address` contenente un attributo `Type` con valore "Billing".</span><span class="sxs-lookup"><span data-stu-id="7bb99-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="7bb99-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="7bb99-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> address =  
    from el in root.Elements("Address")  
    where (string)el.Attribute("Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="7bb99-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="7bb99-107">This code produces the following output:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="7bb99-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bb99-108">Example</span></span>  
 <span data-ttu-id="7bb99-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7bb99-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="7bb99-110">Per altre informazioni, vedere [Uso degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="7bb99-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="7bb99-111">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: ordine di acquisto tipico in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="7bb99-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="7bb99-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="7bb99-112">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7bb99-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bb99-113">See Also</span></span>  
 <span data-ttu-id="7bb99-114"><xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="7bb99-114"><xref:System.Xml.Linq.XElement.Attribute%2A></span></span>   
 <span data-ttu-id="7bb99-115"><xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="7bb99-115"><xref:System.Xml.Linq.XContainer.Elements%2A></span></span>   
 <span data-ttu-id="7bb99-116">[Query di base (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="7bb99-116">[Basic Queries (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span></span>  
 <span data-ttu-id="7bb99-117">[Panoramica degli operatori query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="7bb99-117">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="7bb99-118">Operazioni di proiezione (C#)</span><span class="sxs-lookup"><span data-stu-id="7bb99-118">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)

