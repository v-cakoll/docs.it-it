---
title: 'Procedura: specificare un nome di elemento alternativo per un flusso XML'
description: Viene illustrato come creare un flusso XML con un nome di elemento alternativo, ad esempio, per i servizi Web XML che richiedono le stesse informazioni con piccole differenze.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, overriding
- serialization, overriding
- XML stream, specifying alternate element name for
- overriding XML serialization
- classes, overriding
- overriding classes
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
ms.openlocfilehash: d7e482ee6e1e1a7318ab05766508537d4b87789e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289590"
---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a>Procedura: specificare un nome di elemento alternativo per un flusso XML
  
Tramite l'utilizzo di <xref:System.Xml.Serialization.XmlSerializer>, è possibile generare più di un flusso XML con lo stesso set di classi. È consigliabile eseguire questa operazione poiché due diversi servizi Web XML richiedono le stesse informazioni di base, con solo piccole differenze. Si immagini ad esempio due servizi Web XML che elaborano ordini per libri e che pertanto richiedono i numeri ISBN. Un servizio usa il tag \<ISBN> mentre il secondo usa il tag \<BookID> . Si dispone di una classe denominata `Book` che contiene un campo denominato `ISBN`. Quando viene serializzata un'istanza della classe `Book`, per impostazione predefinita verrà utilizzato il nome del membro (ISBN) come nome dell'elemento del tag. Per il primo servizio Web XML, tale comportamento è quello previsto. Per inviare invece il flusso XML al secondo servizio Web XML, è necessario eseguire l'override della serializzazione in modo che il nome dell'elemento del tag sia `BookID`.  
  
## <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a>Per creare un flusso XML con un nome dell'elemento alternativo  
  
1. Creare un'istanza della classe <xref:System.Xml.Serialization.XmlElementAttribute>.  
  
2. Impostare <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> di <xref:System.Xml.Serialization.XmlElementAttribute> su "BookID".  
  
3. Creare un'istanza della classe <xref:System.Xml.Serialization.XmlAttributes>.  
  
4. Aggiungere l'oggetto `XmlElementAttribute` alla raccolta a cui si accede tramite la proprietà <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> di <xref:System.Xml.Serialization.XmlAttributes>.  
  
5. Creare un'istanza della classe <xref:System.Xml.Serialization.XmlAttributeOverrides>.  
  
6. Aggiungere `XmlAttributes` a <xref:System.Xml.Serialization.XmlAttributeOverrides> e passare il tipo dell'oggetto da sottoporre a override e il nome del membro da sottoporre a override.  
  
7. Creare un'istanza della classe `XmlSerializer` con `XmlAttributeOverrides`.  
  
8. Creare un'istanza della classe `Book` e serializzarla o deserializzarla.  
  
## <a name="example"></a>Esempio  
  
```vb  
Public Function SerializeOverride()  
    ' Creates an XmlElementAttribute with the alternate name.  
    Dim myElementAttribute As XmlElementAttribute = _  
    New XmlElementAttribute()  
    myElementAttribute.ElementName = "BookID"  
    Dim myAttributes As XmlAttributes = New XmlAttributes()  
    myAttributes.XmlElements.Add(myElementAttribute)  
    Dim myOverrides As XmlAttributeOverrides = New XmlAttributeOverrides()  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes)  
    Dim mySerializer As XmlSerializer = _  
    New XmlSerializer(GetType(Book), myOverrides)  
    Dim b As Book = New Book()  
    b.ISBN = "123456789"  
    ' Creates a StreamWriter to write the XML stream to.  
    Dim writer As StreamWriter = New StreamWriter("Book.xml")  
    mySerializer.Serialize(writer, b);  
End Class  
```  
  
```csharp  
public void SerializeOverride()  
{  
    // Creates an XmlElementAttribute with the alternate name.  
    XmlElementAttribute myElementAttribute = new XmlElementAttribute();  
    myElementAttribute.ElementName = "BookID";  
    XmlAttributes myAttributes = new XmlAttributes();  
    myAttributes.XmlElements.Add(myElementAttribute);  
    XmlAttributeOverrides myOverrides = new XmlAttributeOverrides();  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes);  
    XmlSerializer mySerializer =
    new XmlSerializer(typeof(Book), myOverrides)  
    Book b = new Book();  
    b.ISBN = "123456789"  
    // Creates a StreamWriter to write the XML stream to.  
    StreamWriter writer = new StreamWriter("Book.xml");  
    mySerializer.Serialize(writer, b);  
}  
```  
  
 Il flusso XML potrebbe assomigliare agli elementi seguenti.  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Xml.Serialization.XmlElementAttribute>
- <xref:System.Xml.Serialization.XmlAttributes>
- <xref:System.Xml.Serialization.XmlAttributeOverrides>
- [Serializzazione SOAP e XML](xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Procedura: serializzare un oggetto](how-to-serialize-an-object.md)
- [Procedura: Deserializzare un oggetto](how-to-deserialize-an-object.md)
