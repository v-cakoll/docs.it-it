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
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a><span data-ttu-id="b2ae2-103">Procedura: specificare un nome di elemento alternativo per un flusso XML</span><span class="sxs-lookup"><span data-stu-id="b2ae2-103">How to: Specify an Alternate Element Name for an XML Stream</span></span>
  
<span data-ttu-id="b2ae2-104">Tramite l'utilizzo di <xref:System.Xml.Serialization.XmlSerializer>, è possibile generare più di un flusso XML con lo stesso set di classi.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-104">Using the <xref:System.Xml.Serialization.XmlSerializer>, you can generate more than one XML stream with the same set of classes.</span></span> <span data-ttu-id="b2ae2-105">È consigliabile eseguire questa operazione poiché due diversi servizi Web XML richiedono le stesse informazioni di base, con solo piccole differenze.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-105">You might want to do this because two different XML Web services require the same basic information, with only slight differences.</span></span> <span data-ttu-id="b2ae2-106">Si immagini ad esempio due servizi Web XML che elaborano ordini per libri e che pertanto richiedono i numeri ISBN.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-106">For example, imagine two XML Web services that process orders for books, and thus both require ISBN numbers.</span></span> <span data-ttu-id="b2ae2-107">Un servizio usa il tag \<ISBN> mentre il secondo usa il tag \<BookID> .</span><span class="sxs-lookup"><span data-stu-id="b2ae2-107">One service uses the tag \<ISBN> while the second uses the tag \<BookID>.</span></span> <span data-ttu-id="b2ae2-108">Si dispone di una classe denominata `Book` che contiene un campo denominato `ISBN`.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-108">You have a class named `Book` that contains a field named `ISBN`.</span></span> <span data-ttu-id="b2ae2-109">Quando viene serializzata un'istanza della classe `Book`, per impostazione predefinita verrà utilizzato il nome del membro (ISBN) come nome dell'elemento del tag.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-109">When an instance of the `Book` class is serialized, it will, by default, use the member name (ISBN) as the tag element name.</span></span> <span data-ttu-id="b2ae2-110">Per il primo servizio Web XML, tale comportamento è quello previsto.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-110">For the first XML Web service, this is as expected.</span></span> <span data-ttu-id="b2ae2-111">Per inviare invece il flusso XML al secondo servizio Web XML, è necessario eseguire l'override della serializzazione in modo che il nome dell'elemento del tag sia `BookID`.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-111">But to send the XML stream to the second XML Web service, you must override the serialization so that the tag's element name is `BookID`.</span></span>  
  
## <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a><span data-ttu-id="b2ae2-112">Per creare un flusso XML con un nome dell'elemento alternativo</span><span class="sxs-lookup"><span data-stu-id="b2ae2-112">To create an XML stream with an alternate element name</span></span>  
  
1. <span data-ttu-id="b2ae2-113">Creare un'istanza della classe <xref:System.Xml.Serialization.XmlElementAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-113">Create an instance of the <xref:System.Xml.Serialization.XmlElementAttribute> class.</span></span>  
  
2. <span data-ttu-id="b2ae2-114">Impostare <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> di <xref:System.Xml.Serialization.XmlElementAttribute> su "BookID".</span><span class="sxs-lookup"><span data-stu-id="b2ae2-114">Set the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> of the <xref:System.Xml.Serialization.XmlElementAttribute> to "BookID".</span></span>  
  
3. <span data-ttu-id="b2ae2-115">Creare un'istanza della classe <xref:System.Xml.Serialization.XmlAttributes>.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-115">Create an instance of the <xref:System.Xml.Serialization.XmlAttributes> class.</span></span>  
  
4. <span data-ttu-id="b2ae2-116">Aggiungere l'oggetto `XmlElementAttribute` alla raccolta a cui si accede tramite la proprietà <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> di <xref:System.Xml.Serialization.XmlAttributes>.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-116">Add the `XmlElementAttribute` object to the collection accessed through the <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> property of <xref:System.Xml.Serialization.XmlAttributes> .</span></span>  
  
5. <span data-ttu-id="b2ae2-117">Creare un'istanza della classe <xref:System.Xml.Serialization.XmlAttributeOverrides>.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-117">Create an instance of the <xref:System.Xml.Serialization.XmlAttributeOverrides> class.</span></span>  
  
6. <span data-ttu-id="b2ae2-118">Aggiungere `XmlAttributes` a <xref:System.Xml.Serialization.XmlAttributeOverrides> e passare il tipo dell'oggetto da sottoporre a override e il nome del membro da sottoporre a override.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-118">Add the `XmlAttributes` to the <xref:System.Xml.Serialization.XmlAttributeOverrides>, passing the type of the object to override and the name of the member being overridden.</span></span>  
  
7. <span data-ttu-id="b2ae2-119">Creare un'istanza della classe `XmlSerializer` con `XmlAttributeOverrides`.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-119">Create an instance of the `XmlSerializer` class with `XmlAttributeOverrides`.</span></span>  
  
8. <span data-ttu-id="b2ae2-120">Creare un'istanza della classe `Book` e serializzarla o deserializzarla.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-120">Create an instance of the `Book` class, and serialize or deserialize it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2ae2-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2ae2-121">Example</span></span>  
  
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
  
 <span data-ttu-id="b2ae2-122">Il flusso XML potrebbe assomigliare agli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="b2ae2-122">The XML stream might resemble the following.</span></span>  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2ae2-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b2ae2-123">See also</span></span>

- <xref:System.Xml.Serialization.XmlElementAttribute>
- <xref:System.Xml.Serialization.XmlAttributes>
- <xref:System.Xml.Serialization.XmlAttributeOverrides>
- [<span data-ttu-id="b2ae2-124">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="b2ae2-124">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="b2ae2-125">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="b2ae2-125">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="b2ae2-126">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="b2ae2-126">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
