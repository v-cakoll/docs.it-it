---
title: 'Procedura: Filtrare in base a nomi di elementi (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
ms.openlocfilehash: 9febe3b834261326bab3e82d87c476f99d4e6b1f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593814"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-c"></a><span data-ttu-id="2e663-102">Procedura: Filtrare in base a nomi di elementi (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2e663-102">How to: Filter on Element Names (LINQ to XML) (C#)</span></span>
<span data-ttu-id="2e663-103">Quando si chiama uno dei metodi che restituisce l'oggetto <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, è possibile filtrare in base al nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="2e663-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e663-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e663-104">Example</span></span>  
 <span data-ttu-id="2e663-105">In questo esempio viene recuperata una raccolta di discendenti filtrata in maniera tale da includere solo i discendenti con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="2e663-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="2e663-106">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="2e663-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants("ProductName")  
    select el;  
foreach(XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string) prdName);  
```  
  
 <span data-ttu-id="2e663-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2e663-107">This code produces the following output:</span></span>  
  
```  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="2e663-108">Gli altri metodi che restituiscono l'oggetto <xref:System.Collections.Generic.IEnumerable%601> delle raccolte <xref:System.Xml.Linq.XElement> sono caratterizzati dallo stesso schema.</span><span class="sxs-lookup"><span data-stu-id="2e663-108">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="2e663-109">Le relative firme sono simili a <xref:System.Xml.Linq.XContainer.Elements%2A> e <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e663-109">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="2e663-110">Di seguito è riportato l'elenco completo dei metodi con firme simili:</span><span class="sxs-lookup"><span data-stu-id="2e663-110">The following is the complete list of methods that have similar method signatures:</span></span>  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="2e663-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e663-111">Example</span></span>  
 <span data-ttu-id="2e663-112">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2e663-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="2e663-113">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2e663-113">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="2e663-114">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto in uno spazio dei nomi](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="2e663-114">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants(aw + "ProductName")  
    select el;  
foreach (XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string)prdName);  
```  
  
 <span data-ttu-id="2e663-115">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2e663-115">This code produces the following output:</span></span>  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e663-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e663-116">See also</span></span>

- [<span data-ttu-id="2e663-117">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2e663-117">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
