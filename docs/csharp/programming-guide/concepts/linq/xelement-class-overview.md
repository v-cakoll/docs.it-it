---
title: Panoramica della classe XElement (C#)
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: d77c725b3c786b8a8fa2b0eeab4bc4b30f298218
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635470"
---
# <a name="xelement-class-overview-c"></a>Panoramica della classe XElement (C#)
<xref:System.Xml.Linq.XElement> è una delle classi fondamentali di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Rappresenta un elemento XML. Può essere usata per creare elementi, modificare il contenuto dell'elemento, aggiungere, modificare o eliminare elementi figlio, aggiungere attributi a un elemento oppure serializzare il contenuto di un elemento in formato testo. È inoltre possibile definire l'interoperabilità con altre classi di <xref:System.Xml?displayProperty=nameWithType>, ad esempio <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
In questo argomento viene descritta la funzionalità fornita dalla classe <xref:System.Xml.Linq.XElement>.  
  
## <a name="constructing-xml-trees"></a>Costruzione di alberi XML  
 È possibile costruire alberi XML in diversi modi:  
  
- È possibile costruire un albero XML nel codice. Per altre informazioni, vedere [Creazione di alberi XML (C#)](./linq-to-xml-overview.md).  
  
- È possibile analizzare codice XML di origini diverse, incluso un oggetto <xref:System.IO.TextReader>, file di testo o un indirizzo Web (URL). Per altre informazioni, vedere [Analisi di codice XML (C#)](./how-to-parse-a-string.md).  
  
- È possibile usare un oggetto <xref:System.Xml.XmlReader> per popolare l'albero. Per ulteriori informazioni, vedere <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
- Se si dispone di un modulo in grado di scrivere contenuto in un oggetto <xref:System.Xml.XmlWriter>, è possibile usare il metodo <xref:System.Xml.Linq.XContainer.CreateWriter%2A> per creare un writer, passare il writer al modulo e quindi usare il contenuto scritto in <xref:System.Xml.XmlWriter> per popolare l'albero XML.  
  
 Tuttavia, il modo più comune per creare un albero XML è il seguente:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Un'altra tecnica molto comune per la creazione di un albero XML prevede l'uso dei risultati di una query LINQ per popolare un albero XML, come illustrato nell'esempio seguente:  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="serializing-xml-trees"></a>Serializzazione di strutture ad albero XML  
 È possibile serializzare l'albero XML in un oggetto <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.  
  
 Per altre informazioni, vedere l'articolo sulla [serializzazione delle strutture ad albero XML in C#](./preserving-white-space-while-serializing.md).  
  
## <a name="retrieving-xml-data-via-axis-methods"></a>Recupero di dati XML tramite metodi dell'asse  
 È possibile usare metodi dell'asse per recuperare attributi, elementi figlio, elementi discendenti ed elementi predecessori. Le query LINQ operano sui metodi dell'asse e forniscono diversi modi flessibili e potenti per spostarsi ed elaborare un albero XML.  
  
 Per altre informazioni, vedere [Assi LINQ to XML (C#)](./linq-to-xml-axes-overview.md).  
  
## <a name="querying-xml-trees"></a>Esecuzione di query su strutture ad albero XML  
 È possibile scrivere query LINQ che consentono di estrarre dati da un albero XML.  
  
 Per altre informazioni, vedere [Esecuzione di query su strutture ad albero XML (C#)](./how-to-find-an-element-with-a-specific-attribute.md).  
  
## <a name="modifying-xml-trees"></a>Modifica di strutture ad albero XML  
 È possibile modificare un elemento in modi diversi, ad esempio modificandone il contenuto o gli attributi. È inoltre possibile rimuovere un elemento dal relativo elemento padre.  
  
 Per altre informazioni, vedere [Modifica degli alberi XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della programmazione con LINQ to XML (C#)](serializing-to-files-textwriters-and-xmlwriters.md)
