---
title: 'Procedura: popolare una struttura ad albero XML con un XmlWriter (LINQ to XML) (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 5792a0eb-94ee-440d-b601-58cca8c0ee0b
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
ms.openlocfilehash: af870389e34dd480e3db9a09bdffd2d3998747a1
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-visual-basic"></a><span data-ttu-id="c40dc-102">Procedura: popolare una struttura ad albero XML con un XmlWriter (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c40dc-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c40dc-103">Per popolare una struttura ad albero XML è possibile utilizzare <xref:System.Xml.Linq.XContainer.CreateWriter%2A>per creare un <xref:System.Xml.XmlWriter>e quindi scrivere in <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A></span><span class="sxs-lookup"><span data-stu-id="c40dc-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="c40dc-104">La struttura ad albero XML viene popolato con tutti i nodi scritti in <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="c40dc-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="c40dc-105">In genere si utilizza questo metodo quando si utilizza [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] con un'altra classe che prevede di scrivere in un <xref:System.Xml.XmlWriter>, ad esempio <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="c40dc-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c40dc-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c40dc-106">Example</span></span>  
 <span data-ttu-id="c40dc-107">Un possibile utilizzo di <xref:System.Xml.Linq.XContainer.CreateWriter%2A>è il richiamo di una trasformazione XSLT.</xref:System.Xml.Linq.XContainer.CreateWriter%2A></span><span class="sxs-lookup"><span data-stu-id="c40dc-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="c40dc-108">In questo esempio viene creato un albero XML, un <xref:System.Xml.XmlReader>dall'albero XML, crea un nuovo documento e quindi crea un <xref:System.Xml.XmlWriter>da scrivere nel documento nuovo.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="c40dc-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="c40dc-109">Viene quindi richiamata la trasformazione XSLT, passando <xref:System.Xml.XmlReader>e <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="c40dc-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="c40dc-110">Dopo il completamento della trasformazione, il nuovo albero XML viene popolato con i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="c40dc-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
Dim xmlTree As XDocument = _  
    <?xml version='1.0'?>  
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="c40dc-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c40dc-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c40dc-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c40dc-112">See Also</span></span>  
 <span data-ttu-id="c40dc-113"><xref:System.Xml.Linq.XContainer.CreateWriter%2A></xref:System.Xml.Linq.XContainer.CreateWriter%2A></span><span class="sxs-lookup"><span data-stu-id="c40dc-113"><xref:System.Xml.Linq.XContainer.CreateWriter%2A></span></span>   
 <span data-ttu-id="c40dc-114"><xref:System.Xml.XmlWriter></xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="c40dc-114"><xref:System.Xml.XmlWriter></span></span>   
 <span data-ttu-id="c40dc-115"><xref:System.Xml.Xsl.XslCompiledTransform></xref:System.Xml.Xsl.XslCompiledTransform></span><span class="sxs-lookup"><span data-stu-id="c40dc-115"><xref:System.Xml.Xsl.XslCompiledTransform></span></span>   
<span data-ttu-id="c40dc-116"> [Creazione di strutture ad albero XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)</span><span class="sxs-lookup"><span data-stu-id="c40dc-116"> [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)</span></span>
