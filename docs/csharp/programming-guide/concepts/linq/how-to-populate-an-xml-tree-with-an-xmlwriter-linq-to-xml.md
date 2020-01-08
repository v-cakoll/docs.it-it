---
title: Come popolare un albero XML con un oggetto XmlWriter (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
ms.openlocfilehash: f48843af403f2ee0e6d2850deab009a143f55dc7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345765"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a><span data-ttu-id="9386b-102">Come popolare un albero XML con un oggetto XmlWriter (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9386b-102">How to populate an XML tree with an XmlWriter (LINQ to XML) (C#)</span></span>
<span data-ttu-id="9386b-103">Per popolare un albero XML, è possibile usare <xref:System.Xml.Linq.XContainer.CreateWriter%2A> per creare <xref:System.Xml.XmlWriter>e quindi scrivere in <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="9386b-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="9386b-104">L'albero XML viene popolato con tutti i nodi scritti in <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="9386b-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="9386b-105">Questo metodo viene in genere impiegato quando si usa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con un'altra classe che prevede di scrivere in un oggetto <xref:System.Xml.XmlWriter>, ad esempio <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="9386b-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9386b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9386b-106">Example</span></span>  
 <span data-ttu-id="9386b-107">Un possibile utilizzo di <xref:System.Xml.Linq.XContainer.CreateWriter%2A> è il richiamo di una trasformazione XSLT.</span><span class="sxs-lookup"><span data-stu-id="9386b-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="9386b-108">In questo esempio viene creato un albero XML da cui viene creato un oggetto <xref:System.Xml.XmlReader>. Viene quindi creato un nuovo documento e infine viene creato un oggetto <xref:System.Xml.XmlWriter> per scrivere nel nuovo documento.</span><span class="sxs-lookup"><span data-stu-id="9386b-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="9386b-109">Viene quindi richiamata la trasformazione XSLT, passando <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="9386b-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="9386b-110">Dopo il completamento della trasformazione, il nuovo albero XML viene popolato con i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="9386b-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
using (XmlWriter writer = newTree.CreateWriter())  
{  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="9386b-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="9386b-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9386b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9386b-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="9386b-113">Creazione di alberi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="9386b-113">Creating XML Trees (C#)</span></span>](./linq-to-xml-overview.md)
