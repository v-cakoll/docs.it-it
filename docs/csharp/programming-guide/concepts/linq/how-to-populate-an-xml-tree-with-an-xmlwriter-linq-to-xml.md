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
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a>Come popolare un albero XML con un oggetto XmlWriter (LINQ to XML) (C#)
Per popolare un albero XML, è possibile usare <xref:System.Xml.Linq.XContainer.CreateWriter%2A> per creare <xref:System.Xml.XmlWriter>e quindi scrivere in <xref:System.Xml.XmlWriter>. L'albero XML viene popolato con tutti i nodi scritti in <xref:System.Xml.XmlWriter>.  
  
 Questo metodo viene in genere impiegato quando si usa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con un'altra classe che prevede di scrivere in un oggetto <xref:System.Xml.XmlWriter>, ad esempio <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="example"></a>Esempio  
 Un possibile utilizzo di <xref:System.Xml.Linq.XContainer.CreateWriter%2A> è il richiamo di una trasformazione XSLT. In questo esempio viene creato un albero XML da cui viene creato un oggetto <xref:System.Xml.XmlReader>. Viene quindi creato un nuovo documento e infine viene creato un oggetto <xref:System.Xml.XmlWriter> per scrivere nel nuovo documento. Viene quindi richiamata la trasformazione XSLT, passando <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlWriter>. Dopo il completamento della trasformazione, il nuovo albero XML viene popolato con i relativi risultati.  
  
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
  
 Questo esempio produce il seguente output:  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [Creazione di alberi XML (C#)](./linq-to-xml-overview.md)
