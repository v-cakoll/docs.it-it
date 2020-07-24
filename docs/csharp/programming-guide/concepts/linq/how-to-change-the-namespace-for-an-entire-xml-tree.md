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
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a>Come modificare lo spazio dei nomi per un intero albero XML (C#)
È talvolta necessario cambiare a livello di codice lo spazio dei nomi per un elemento o un attributo. Questa operazione è particolarmente agevole con LINQ to XML. È possibile impostare la proprietà <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType>. Non è possibile impostare la proprietà <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType>, tuttavia è possibile copiare gli attributi in un nuovo oggetto <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, rimuovere gli attributi esistenti e quindi aggiungere quelli nuovi inclusi nello spazio dei nomi desiderato.  
  
 Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).  
  
## <a name="example"></a>Esempio  
 Nel codice seguente vengono create due alberi XML in nessuno spazio dei nomi. Viene quindi cambiato lo spazio dei nomi di ognuna degli alberi in modo da combinarle in un unico albero.  
  
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
  
 Nell'esempio viene prodotto l'output seguente:  
  
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
