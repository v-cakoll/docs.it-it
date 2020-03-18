---
title: Serializzazione in base a un XmlReader (richiamo di XSLT) (C#)
ms.date: 07/20/2015
ms.assetid: 4cc3ee03-ef4c-429b-a408-fedd10b728cd
ms.openlocfilehash: b079fe05fa8c230f644e011dcb62ec54f55cae60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "66487186"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-c"></a>Serializzazione in base a un XmlReader (richiamo di XSLT) (C#)
Quando si usano le funzionalità di interoperabilità <xref:System.Xml?displayProperty=nameWithType> di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], è possibile usare <xref:System.Xml.Linq.XNode.CreateReader%2A> per creare un oggetto <xref:System.Xml.XmlReader>. Il modulo che legge dall'oggetto <xref:System.Xml.XmlReader> creato legge i nodi dell'albero XML e li elabora di conseguenza.  
  
## <a name="invoking-an-xslt-transformation"></a>Richiamo di una trasformazione XSLT  
 Un possibile utilizzo di questo metodo è il richiamo di una trasformazione XSLT. È possibile creare un albero XML, creare un oggetto <xref:System.Xml.XmlReader> dall'albero XML, creare un nuovo documento e infine creare un oggetto <xref:System.Xml.XmlWriter> per scrivere nel documento. È quindi possibile richiamare la trasformazione XSLT passandovi <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlWriter>. Dopo il completamento della trasformazione, il nuovo albero XML viene popolato con i relativi risultati.  
  
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
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione di alberi XML (C#)](serializing-to-files-textwriters-and-xmlwriters.md)
