---
title: 'Procedura: Cambiare lo spazio dei nomi per un intero albero XML (C#)'
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
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffebf1bda275eb815ff3e15538fd69de6d3b0c1a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a><span data-ttu-id="2647c-102">Procedura: Cambiare lo spazio dei nomi per un intero albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2647c-102">How to: Change the Namespace for an Entire XML Tree (C#)</span></span>
<span data-ttu-id="2647c-103">È talvolta necessario cambiare a livello di codice lo spazio dei nomi per un elemento o un attributo.</span><span class="sxs-lookup"><span data-stu-id="2647c-103">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="2647c-104">Questa operazione è particolarmente agevole con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="2647c-104">LINQ to XML makes this easy.</span></span> <span data-ttu-id="2647c-105">È possibile impostare la proprietà <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2647c-105">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=fullName> property can be set.</span></span> <span data-ttu-id="2647c-106">Non è possibile impostare la proprietà <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=fullName>, tuttavia è possibile copiare gli attributi in un nuovo oggetto <xref:System.Collections.Generic.List%601?displayProperty=fullName>, rimuovere gli attributi esistenti e quindi aggiungere quelli nuovi inclusi nello spazio dei nomi desiderato.</span><span class="sxs-lookup"><span data-stu-id="2647c-106">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=fullName> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=fullName>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="2647c-107">Per altre informazioni, vedere [Uso degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="2647c-107">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2647c-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="2647c-108">Example</span></span>  
 <span data-ttu-id="2647c-109">Nel codice seguente vengono create due alberi XML in nessuno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2647c-109">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="2647c-110">Viene quindi cambiato lo spazio dei nomi di ognuna degli alberi in modo da combinarle in un unico albero.</span><span class="sxs-lookup"><span data-stu-id="2647c-110">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
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
  
 <span data-ttu-id="2647c-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="2647c-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2647c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2647c-112">See Also</span></span>  
 [<span data-ttu-id="2647c-113">Modifica degli alberi XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2647c-113">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)

