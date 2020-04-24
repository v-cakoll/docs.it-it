---
title: Estensione del DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: b5489c96-4afd-439a-a25d-fc82eb4a148d
ms.openlocfilehash: 11c7e8c8d2ea3b49fe73ab4dde4e2ccc8bc917ff
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159676"
---
# <a name="extending-the-dom"></a>Estensione del DOM

Microsoft .NET Framework comprende un set di classi di base che fornisce l'implementazione del modello DOM XML (Document Object Model). Tramite <xref:System.Xml.XmlNode> e le classi derivate vengono forniti metodi e proprietà che consentono di esplorare, eseguire query e modificare il contenuto e la struttura di un documento XML.

Quando il contenuto dell'XML è caricato in memoria tramite il DOM, i nodi creati contengono informazioni quali il nome del nodo, il tipo di nodo e così via. In alcuni casi è possibile che siano necessarie informazioni specifiche sul nodo che non vengono fornite dalle classi di base. È possibile, ad esempio, che si desideri conoscere il numero di riga e la posizione del nodo. In questo caso è possibile derivare nuove classi dalle classi esistenti del DOM e aggiungere ulteriori funzionalità.

La derivazione di nuove classi è soggetta a due linee guida generali:

- Si consiglia di non eseguire mai una derivazione dalla classe <xref:System.Xml.XmlNode>. Si consiglia invece di eseguire la derivazione delle classi dalla classe corrispondente al tipo di nodo a cui si è interessati. Se ad esempio si desidera restituire ulteriori informazioni sui nodi degli attributi, è possibile eseguire la derivazione dalla classe <xref:System.Xml.XmlAttribute>.

- Ad eccezione dei metodi per la creazione dei nodi, se si esegue l'override di una funzione si consiglia di chiamare sempre la versione di base della funzione e di aggiungervi un'eventuale elaborazione aggiuntiva.

## <a name="creating-your-own-node-instances"></a>Creazione di istanze dei nodi

La classe <xref:System.Xml.XmlDocument> contiene i metodi per la creazione di nodi. Quando viene caricato un file XML, questi metodi vengono chiamati per creare i nodi. È possibile eseguire l'override di questi metodi in modo che le istanze dei nodi vengano create quando viene caricato un documento. Se ad esempio è stata estesa la classe <xref:System.Xml.XmlElement>, viene ereditata la classe <xref:System.Xml.XmlDocument> e viene eseguito l'override del metodo <xref:System.Xml.XmlDocument.CreateElement%2A>.

Nell'esempio seguente viene illustrato come eseguire l'override del metodo <xref:System.Xml.XmlDocument.CreateElement%2A> per restituire l'implementazione della classe <xref:System.Xml.XmlElement>.

```vb
Class LineInfoDocument
    Inherits XmlDocument
        Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement
        Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)
        Return elem
    End Function 'CreateElement
End Class 'LineInfoDocument
```

```csharp
class LineInfoDocument : XmlDocument
{
    public override XmlElement CreateElement(string prefix, string localname, string nsURI)
    {
        LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this);
        return elem;
    }
}
```

## <a name="extending-a-class"></a>Estensione di una classe

Per estendere una classe, derivare la classe da una delle classi esistenti del DOM. È possibile quindi eseguire l'override dei metodi o delle proprietà virtuali nella classe di base oppure aggiungere quelli di propria creazione.

Nell'esempio seguente viene creata una nuova classe, che implementa la classe <xref:System.Xml.XmlElement> e l'interfaccia <xref:System.Xml.IXmlLineInfo>. Sono definiti metodi e proprietà aggiuntivi per consentire all'utente di raccogliere informazioni sulla riga.

```vb
Class LineInfoElement
   Inherits XmlElement
   Implements IXmlLineInfo
   Private lineNumber As Integer = 0
   Private linePosition As Integer = 0

   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)
      MyBase.New(prefix, localname, nsURI, doc)
      CType(doc, LineInfoDocument).IncrementElementCount()
   End Sub

   Public Sub SetLineInfo(linenum As Integer, linepos As Integer)
      lineNumber = linenum
      linePosition = linepos
   End Sub

   Public ReadOnly Property LineNumber() As Integer
      Get
         Return lineNumber
      End Get
   End Property

   Public ReadOnly Property LinePosition() As Integer
      Get
         Return linePosition
      End Get
   End Property

   Public Function HasLineInfo() As Boolean
      Return True
   End Function
End Class ' End LineInfoElement class.
```

```csharp
class LineInfoElement : XmlElement, IXmlLineInfo {
   int lineNumber = 0;
   int linePosition = 0;
   internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ) : base( prefix, localname, nsURI, doc ) {
       ( (LineInfoDocument)doc ).IncrementElementCount();
  }
  public void SetLineInfo( int linenum, int linepos ) {
      lineNumber = linenum;
      linePosition = linepos;
  }
  public int LineNumber {
     get {
       return lineNumber;
     }
  }
  public int LinePosition {
      get {
        return linePosition;
      }
  }
  public bool HasLineInfo() {
    return true;
  }
} // End LineInfoElement class.
```

### <a name="example"></a>Esempio

Nell'esempio seguente viene contato il numero di elementi in un documento XML:

```vb
Imports System.Xml
Imports System.IO

Class LineInfoDocument
   Inherits XmlDocument

   Private elementCount As Integer

   Friend Sub New()
      elementCount = 0
   End Sub

   Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement
      Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)
      Return elem
   End Function

   Public Sub IncrementElementCount()
      elementCount += 1
   End Sub

   Public Function GetCount() As Integer
      Return elementCount
   End Function
End Class 'End LineInfoDocument class.

Class LineInfoElement
   Inherits XmlElement

   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)
      MyBase.New(prefix, localname, nsURI, doc)
      CType(doc, LineInfoDocument).IncrementElementCount()
   End Sub 'New
End Class 'LineInfoElement
 _ 'End LineInfoElement class.

Public Class Test

   Private filename As [String] = "book.xml"

   Public Shared Sub Main()

      Dim doc As New LineInfoDocument()
      doc.Load(filename)
      Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount())
   End Sub
End Class
```

```csharp
using System;
using System.Xml;
using System.IO;

class LineInfoDocument : XmlDocument {

  int elementCount;
  internal LineInfoDocument():base() {
    elementCount = 0;
  }

  public override XmlElement CreateElement( string prefix, string localname, string nsURI) {
    LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this );
    return elem;
  }

  public void IncrementElementCount() {
     elementCount++;
  }

  public int GetCount() {
     return elementCount;
  }
} // End LineInfoDocument class.

class LineInfoElement:XmlElement {

    internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ):base( prefix,localname,nsURI, doc ){
      ((LineInfoDocument)doc).IncrementElementCount();
    }
} // End LineInfoElement class.

public class Test {

  const String filename = "book.xml";
  public static void Main() {

     LineInfoDocument doc =new LineInfoDocument();
     doc.Load(filename);
     Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount());

  }
}
```

#### <a name="input"></a>Input

books.xml

```xml
<!--sample XML fragment-->
<book genre='novel' ISBN='1-861001-57-5' misc='sale-item'>
  <title>The Handmaid's Tale</title>
  <price>14.95</price>
</book>
```

#### <a name="output"></a>Output

```console
Number of elements in book.xml: 3
```

## <a name="node-event-handler"></a>Gestore degli eventi dei nodi

Nell'implementazione del DOM da parte di .NET Framework è compreso anche un sistema di eventi che consente di ricevere e gestire gli eventi quando i nodi di un documento XML vengono modificati. Usando le classi <xref:System.Xml.XmlNodeChangedEventHandler> e <xref:System.Xml.XmlNodeChangedEventArgs>, è possibile acquisire gli eventi`NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved` e `NodeRemoving`.

Il processo di gestione degli eventi nelle classi derivate è identico a quello nelle classi originali del DOM.

Per altre informazioni sulla gestione degli eventi del nodo, vedere [Eventi](../../../../docs/standard/events/index.md) e <xref:System.Xml.XmlNodeChangedEventHandler>.

## <a name="default-attributes-and-the-createelement-method"></a>Attributi predefiniti e metodo CreateElement

Se si esegue l'override del metodo <xref:System.Xml.XmlDocument.CreateElement%2A> in una classe derivata, gli attributi predefiniti non vengono aggiunti alla creazione di nuovi elementi durante la modifica del documento. Questo problema si verifica solo durante la modifica. Poiché il metodo <xref:System.Xml.XmlDocument.CreateElement%2A> è responsabile dell'aggiunta di attributi predefiniti a un <xref:System.Xml.XmlDocument>, è necessario codificare questa funzionalità nel metodo <xref:System.Xml.XmlDocument.CreateElement%2A>. Se si carica un <xref:System.Xml.XmlDocument> in cui sono compresi attributi predefiniti, questi verranno gestiti correttamente. Per altre informazioni sugli attributi predefiniti, vedere [Creazione di nuovi attributi per gli elementi nel DOM](creating-new-attributes-for-elements-in-the-dom.md).

## <a name="see-also"></a>Vedi anche

- [XML DOM (Document Object Model)](xml-document-object-model-dom.md)
