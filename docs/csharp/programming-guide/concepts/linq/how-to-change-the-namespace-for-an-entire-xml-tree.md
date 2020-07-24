---
title: Come modificare lo spazio dei nomi per un intero albero XML (C#)
description: Informazioni su come modificare a livello di codice lo spazio dei nomi per un elemento o un attributo in LINQ to XML in C#.
ms.date: 07/20/2015
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
ms.openlocfilehash: 0bf4c9d8f3cf569f14b654dfd0c4291a7eb647df
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105376"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a><span data-ttu-id="a7871-103">Come modificare lo spazio dei nomi per un intero albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="a7871-103">How to change the namespace for an entire XML tree (C#)</span></span>
<span data-ttu-id="a7871-104">È talvolta necessario cambiare a livello di codice lo spazio dei nomi per un elemento o un attributo.</span><span class="sxs-lookup"><span data-stu-id="a7871-104">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="a7871-105">Questa operazione è particolarmente agevole con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="a7871-105">LINQ to XML makes this easy.</span></span> <span data-ttu-id="a7871-106">È possibile impostare la proprietà <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a7871-106">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="a7871-107">Non è possibile impostare la proprietà <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType>, tuttavia è possibile copiare gli attributi in un nuovo oggetto <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, rimuovere gli attributi esistenti e quindi aggiungere quelli nuovi inclusi nello spazio dei nomi desiderato.</span><span class="sxs-lookup"><span data-stu-id="a7871-107">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="a7871-108">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a7871-108">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7871-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7871-109">Example</span></span>  
 <span data-ttu-id="a7871-110">Nel codice seguente vengono create due alberi XML in nessuno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a7871-110">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="a7871-111">Viene quindi cambiato lo spazio dei nomi di ognuna degli alberi in modo da combinarle in un unico albero.</span><span class="sxs-lookup"><span data-stu-id="a7871-111">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```csharp  
XElement tree1 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XElement tree2 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace ad = "http://www.adatum.com";  
// change the namespace of every element and attribute in the first tree  
foreach (XElement el in tree1.DescendantsAndSelf())  
{  
    el.Name = aw.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(aw.GetName(at.Name.LocalName), at.Value));  
}  
// change the namespace of every element and attribute in the second tree  
foreach (XElement el in tree2.DescendantsAndSelf())  
{  
    el.Name = ad.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(ad.GetName(at.Name.LocalName), at.Value));  
}  
// add attribute namespaces so that the tree will be serialized with  
// the aw and ad namespace prefixes  
tree1.Add(  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com")  
);  
tree2.Add(  
    new XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com")  
);  
// create a new composite tree  
XElement root = new XElement("Root",  
    tree1,  
    tree2  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="a7871-112">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="a7871-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
