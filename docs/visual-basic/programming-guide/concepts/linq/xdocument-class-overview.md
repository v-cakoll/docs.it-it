---
title: Panoramica della classe XDocument
ms.date: 07/20/2015
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
ms.openlocfilehash: 90c97349006407b2eca861be31080ec17901fa5b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413232"
---
# <a name="xdocument-class-overview-visual-basic"></a>Cenni preliminari sulla classe XDocument (Visual Basic)
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
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
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
doc.Save("test.xml")  
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

- [Panoramica della programmazione LINQ to XML (Visual Basic)](linq-to-xml-programming-overview.md)
