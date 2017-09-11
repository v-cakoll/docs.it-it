---
title: Uso di XSLT per trasformare un albero XML (C#)
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
ms.assetid: 373a2699-d4c5-471b-9bda-c1f0ab73b477
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b6ec4a04bebd39ecb6a90dfc48729fa8696a2ab5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="using-xslt-to-transform-an-xml-tree-c"></a><span data-ttu-id="28eba-102">Uso di XSLT per trasformare un albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="28eba-102">Using XSLT to Transform an XML Tree (C#)</span></span>
<span data-ttu-id="28eba-103">È possibile creare un albero XML, creare un oggetto <xref:System.Xml.XmlReader> dall'albero XML, creare un nuovo documento e infine creare un oggetto <xref:System.Xml.XmlWriter> che scriverà nel documento nuovo.</span><span class="sxs-lookup"><span data-stu-id="28eba-103">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and create an <xref:System.Xml.XmlWriter> that will write into the new document.</span></span> <span data-ttu-id="28eba-104">Quindi, è possibile richiamare la trasformazione XSLT, passando <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlWriter> alla trasformazione.</span><span class="sxs-lookup"><span data-stu-id="28eba-104">Then, you can invoke the XSLT transformation, passing the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to the transformation.</span></span> <span data-ttu-id="28eba-105">Dopo il completamento della trasformazione, il nuovo albero XML viene popolato con i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="28eba-105">After the transformation successfully completes, the new XML tree is populated with the results of the transform.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28eba-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="28eba-106">Example</span></span>  
  
```csharp  
string xslMarkup = @"<?xml version='1.0'?>  
<xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
    <xsl:template match='/Parent'>  
        <Root>  
            <C1>  
            <xsl:value-of select='Child1'/>  
            </C1>  
            <C2>  
            <xsl:value-of select='Child2'/>  
            </C2>  
        </Root>  
    </xsl:template>  
</xsl:stylesheet>";  
  
XDocument xmlTree = new XDocument(  
    new XElement("Parent",  
        new XElement("Child1", "Child1 data"),  
        new XElement("Child2", "Child2 data")  
    )  
);  
  
XDocument newTree = new XDocument();  
using (XmlWriter writer = newTree.CreateWriter()) {  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transform and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="28eba-107">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="28eba-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="28eba-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28eba-108">See Also</span></span>  
 <span data-ttu-id="28eba-109"><xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="28eba-109"><xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="28eba-110"><xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="28eba-110"><xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=fullName></span></span>   
 [<span data-ttu-id="28eba-111">Programmazione LINQ to XML avanzata (C#)</span><span class="sxs-lookup"><span data-stu-id="28eba-111">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

