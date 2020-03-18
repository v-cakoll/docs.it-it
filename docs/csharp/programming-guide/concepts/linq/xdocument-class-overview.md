---
title: Panoramica della classe XDocument (C#)
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: de49dc071d22dd77dddea29ca114663261e3edda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69590851"
---
# <a name="xdocument-class-overview-c"></a>Panoramica della classe XDocument (C#)
In questo argomento viene descritta la classe <xref:System.Xml.Linq.XDocument>.  
  
## <a name="overview-of-the-xdocument-class"></a>Cenni preliminari sulla classe XDocument  
 La classe <xref:System.Xml.Linq.XDocument> include le informazioni necessarie per un documento XML valido, ovvero una dichiarazione XML, istruzioni di elaborazione e commenti.  
  
 Notare che è necessario creare oggetti <xref:System.Xml.Linq.XDocument> solo se è richiesta la funzionalità specifica fornita dalla classe <xref:System.Xml.Linq.XDocument>. In molte circostanze è possibile usare direttamente <xref:System.Xml.Linq.XElement>. L'utilizzo diretto di <xref:System.Xml.Linq.XElement> corrisponde a un modello di programmazione più semplice.  
  
 <xref:System.Xml.Linq.XDocument> deriva da <xref:System.Xml.Linq.XContainer>. pertanto può contenere nodi figlio. Gli oggetti <xref:System.Xml.Linq.XDocument> possono contenere un solo nodo <xref:System.Xml.Linq.XElement> figlio, in conformità allo standard XML, secondo il quale un documento XML può contenere un unico elemento radice.  
  
## <a name="components-of-xdocument"></a>Componenti di XDocument  
 Un oggetto <xref:System.Xml.Linq.XDocument> può contenere i seguenti elementi:  
  
- Un unico oggetto <xref:System.Xml.Linq.XDeclaration>. <xref:System.Xml.Linq.XDeclaration> consente di specificare le parti pertinenti di una dichiarazione XML, ovvero la versione del codice XML, la codifica del documento e se il documento XML è autonomo.  
  
- Un unico oggetto <xref:System.Xml.Linq.XElement>. Si tratta del nodo radice del documento XML.  
  
- Un qualsiasi numero di oggetti <xref:System.Xml.Linq.XProcessingInstruction>. Un'istruzione di elaborazione comunica informazioni a un'applicazione che elabora l'XML.  
  
- Un qualsiasi numero di oggetti <xref:System.Xml.Linq.XComment>. I commenti saranno elementi di pari livello dell'elemento radice. L'oggetto <xref:System.Xml.Linq.XComment> non può essere il primo argomento dell'elenco perché un documento XML non può iniziare con un commento.  
  
- Un unico oggetto <xref:System.Xml.Linq.XDocumentType> per DTD.  
  
 Quando si serializza un oggetto <xref:System.Xml.Linq.XDocument>, anche se `XDocument.Declaration` è `null`, l'output includerà una dichiarazione XML se per il writer `Writer.Settings.OmitXmlDeclaration` è impostato su `false` (impostazione predefinita).  
  
 Per impostazione predefinita, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] imposta la versione su "1.0" e la codifica su "utf-8".  
  
## <a name="using-xelement-without-xdocument"></a>Uso di XElement senza XDocument  
 Come menzionato in precedenza, la classe <xref:System.Xml.Linq.XElement> è la classe principale dell'interfaccia di programmazione di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. In molti casi l'applicazione non richiederà la creazione di un documento. Se si usa la classe <xref:System.Xml.Linq.XElement>, è possibile creare un albero XML, aggiungervi altri alberi XML, modificare l'albero XML e salvarlo.  
  
## <a name="using-xdocument"></a>Uso di XDocument  
 Per costruire un oggetto <xref:System.Xml.Linq.XDocument>, usare la costruzione funzionale come se si trattasse di costruire oggetti <xref:System.Xml.Linq.XElement>.  
  
 Nel codice seguente vengono creati un oggetto <xref:System.Xml.Linq.XDocument> e i relativi oggetti contenuti associati.  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 Quando si esamina il file test.xml, si ottiene l'output seguente:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della programmazione con LINQ to XML (C#)](./linq-to-xml-overview.md)
