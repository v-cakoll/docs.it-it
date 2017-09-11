---
title: Utilizzo di XSLT per trasformare un albero XML (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 3390ca68-c270-4e1d-b64b-6a063a77017c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 860f6b9debae37059bb15ad6bb5de2ed6f9292cb
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="using-xslt-to-transform-an-xml-tree-visual-basic"></a><span data-ttu-id="d8138-102">Utilizzo di XSLT per trasformare un albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8138-102">Using XSLT to Transform an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="d8138-103">È possibile creare una struttura ad albero XML, creare un <xref:System.Xml.XmlReader>dall'albero XML, creare un nuovo documento e creare un <xref:System.Xml.XmlWriter>che scriverà nel documento nuovo.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="d8138-103">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and create an <xref:System.Xml.XmlWriter> that will write into the new document.</span></span> <span data-ttu-id="d8138-104">Quindi, è possibile richiamare la trasformazione XSLT, passando il <xref:System.Xml.XmlReader>e <xref:System.Xml.XmlWriter>alla trasformazione.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="d8138-104">Then, you can invoke the XSLT transformation, passing the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to the transformation.</span></span> <span data-ttu-id="d8138-105">Dopo il completamento della trasformazione, il nuovo albero XML viene popolato con i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="d8138-105">After the transformation successfully completes, the new XML tree is populated with the results of the transform.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8138-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8138-106">Example</span></span>  
  
```vb  
Dim xslMarkup As XDocument = _   
    <?xml version='1.0'?>  
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
    </xsl:stylesheet>  
  
Dim xmlTree As XElement = _   
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = _  
        New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transform and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="d8138-107">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="d8138-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8138-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8138-108">See Also</span></span>  
 <span data-ttu-id="d8138-109"><xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d8138-109"><xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="d8138-110"><xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d8138-110"><xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="d8138-111"> [LINQ to XML (Visual Basic) di programmazione avanzata](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)</span><span class="sxs-lookup"><span data-stu-id="d8138-111"> [Advanced LINQ to XML Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)</span></span>
