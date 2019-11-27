---
title: Serializzazione in base a un XmlReader (richiamo di XSLT)
ms.date: 07/20/2015
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
ms.openlocfilehash: 39ecbc1851764d221ac99c3e47c26bcbe84c9e46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349359"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a><span data-ttu-id="8a1e0-102">Serializzazione in un XmlReader (richiamo di XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a1e0-102">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>
<span data-ttu-id="8a1e0-103">Quando si usano le funzionalità di interoperabilità <xref:System.Xml?displayProperty=nameWithType> di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], è possibile usare <xref:System.Xml.Linq.XNode.CreateReader%2A> per creare un oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-103">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="8a1e0-104">Il modulo che legge dall'oggetto <xref:System.Xml.XmlReader> creato legge i nodi dell'albero XML e li elabora di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="8a1e0-105">Richiamo di una trasformazione XSLT</span><span class="sxs-lookup"><span data-stu-id="8a1e0-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="8a1e0-106">Un possibile utilizzo di questo metodo è il richiamo di una trasformazione XSLT.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="8a1e0-107">È possibile creare un albero XML, creare un oggetto <xref:System.Xml.XmlReader> dall'albero XML, creare un nuovo documento e infine creare un oggetto <xref:System.Xml.XmlWriter> per scrivere nel documento.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="8a1e0-108">È quindi possibile richiamare la trasformazione XSLT passandovi <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="8a1e0-109">Dopo il completamento della trasformazione, il nuovo albero XML viene popolato con i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="8a1e0-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8a1e0-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a1e0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a1e0-111">See also</span></span>

- [<span data-ttu-id="8a1e0-112">Serializzazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a1e0-112">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
