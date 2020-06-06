---
title: Come qualificare i nomi di elementi XML e di attributi XML
description: In questo articolo viene illustrato come qualificare i nomi degli elementi XML e degli attributi XML nei documenti XML.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: 6c29e03d9ce28e5b0abc68a5d7e8d82f4485ac93
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "83378407"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="b024f-103">Come qualificare i nomi di elementi XML e di attributi XML</span><span class="sxs-lookup"><span data-stu-id="b024f-103">How to qualify XML element and XML attribute names</span></span>

<span data-ttu-id="b024f-104">Gli spazi dei nomi XML contenuti nelle istanze della <xref:System.Xml.Serialization.XmlSerializerNamespaces> classe devono essere conformi alla specifica World Wide Web Consortium (W3C) denominata [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span><span class="sxs-lookup"><span data-stu-id="b024f-104">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (W3C) specification called [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span></span>

<span data-ttu-id="b024f-105">Gli spazi dei nomi XML forniscono un metodo che consente di qualificare i nomi di elementi XML e attributi XML nei documenti XML.</span><span class="sxs-lookup"><span data-stu-id="b024f-105">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="b024f-106">Un nome completo è composto da un prefisso e da un nome locale, separati dal carattere di due punti.</span><span class="sxs-lookup"><span data-stu-id="b024f-106">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="b024f-107">Il prefisso funge soltanto da segnaposto ed è mappato a un URI che specifica uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b024f-107">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="b024f-108">La combinazione dello spazio dei nomi URI gestito a livello universale e del nome locale genera un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="b024f-108">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>

<span data-ttu-id="b024f-109">Tramite la creazione di un'istanza di `XmlSerializerNamespaces` e l'aggiunta delle coppie dello spazio dei nomi all'oggetto, è possibile specificare i prefissi utilizzati in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="b024f-109">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>

## <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="b024f-110">Per creare nomi completi in un documento XML</span><span class="sxs-lookup"><span data-stu-id="b024f-110">To create qualified names in an XML document</span></span>

1. <span data-ttu-id="b024f-111">Creare un'istanza della classe `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="b024f-111">Create an instance of the `XmlSerializerNamespaces` class.</span></span>

2. <span data-ttu-id="b024f-112">Aggiungere tutte le coppie di prefissi e spazi dei nomi a `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="b024f-112">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>

3. <span data-ttu-id="b024f-113">Applicare l'attributo `System.Xml.Serialization` appropriato a ciascun membro o classe che <xref:System.Xml.Serialization.XmlSerializer> deve serializzare in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="b024f-113">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>

    <span data-ttu-id="b024f-114">Gli attributi disponibili sono: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> e <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b024f-114">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>

4. <span data-ttu-id="b024f-115">Impostare la proprietà `Namespace` di ciascun attributo su uno dei valori dello spazio dei nomi da `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="b024f-115">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>

5. <span data-ttu-id="b024f-116">Passare `XmlSerializerNamespaces` al metodo `Serialize` di `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="b024f-116">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>

## <a name="example"></a><span data-ttu-id="b024f-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="b024f-117">Example</span></span>

<span data-ttu-id="b024f-118">Nell'esempio riportato di seguito viene creato un oggetto `XmlSerializerNamespaces`, a cui vengono aggiunte due coppie di prefisso e spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b024f-118">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="b024f-119">Il codice crea un `XmlSerializer` utilizzato per serializzare un'istanza della classe `Books`.</span><span class="sxs-lookup"><span data-stu-id="b024f-119">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="b024f-120">Il codice chiama il metodo `Serialize` con `XmlSerializerNamespaces`, consentendo all'XML di contenere spazi dei nomi con prefissi.</span><span class="sxs-lookup"><span data-stu-id="b024f-120">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.Serialization

Public Module Program

    Public Sub Main()
        SerializeObject("XmlNamespaces.xml")
    End Sub

    Public Sub SerializeObject(filename As String)
        Dim mySerializer As New XmlSerializer(GetType(Books))
        ' Writing a file requires a TextWriter.
        Dim myWriter As New StreamWriter(filename)

        ' Creates an XmlSerializerNamespaces and adds two
        ' prefix-namespace pairs.
        Dim myNamespaces As New XmlSerializerNamespaces()
        myNamespaces.Add("books", "http://www.cpandl.com")
        myNamespaces.Add("money", "http://www.cohowinery.com")

        ' Creates a Book.
        Dim myBook As New Book()
        myBook.TITLE = "A Book Title"
        Dim myPrice As New Price()
        myPrice.price = CDec(9.95)
        myPrice.currency = "US Dollar"
        myBook.PRICE = myPrice
        Dim myBooks As New Books()
        myBooks.Book = myBook
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)
        myWriter.Close()
    End Sub
End Module

Public Class Books
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public Book As Book
End Class

<XmlType([Namespace] := "http://www.cpandl.com")> _
Public Class Book
    <XmlElement([Namespace] := "http://www.cpandl.com")> _
    Public TITLE As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public PRICE As Price
End Class

Public Class Price
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _
    Public currency As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public price As Decimal
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;

public class Program
{
    public static void Main()
    {
        SerializeObject("XmlNamespaces.xml");
    }

    public static void SerializeObject(string filename)
    {
        var mySerializer = new XmlSerializer(typeof(Books));
        // Writing a file requires a TextWriter.
        TextWriter myWriter = new StreamWriter(filename);

        // Creates an XmlSerializerNamespaces and adds two
        // prefix-namespace pairs.
        var myNamespaces = new XmlSerializerNamespaces();
        myNamespaces.Add("books", "http://www.cpandl.com");
        myNamespaces.Add("money", "http://www.cohowinery.com");

        // Creates a Book.
        var myBook = new Book();
        myBook.TITLE = "A Book Title";
        var myPrice = new Price();
        myPrice.price = (decimal) 9.95;
        myPrice.currency = "US Dollar";
        myBook.PRICE = myPrice;
        var myBooks = new Books();
        myBooks.Book = myBook;
        mySerializer.Serialize(myWriter, myBooks, myNamespaces);
        myWriter.Close();
    }
}

public class Books
{
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public Book Book;
}

[XmlType(Namespace ="http://www.cpandl.com")]
public class Book
{
    [XmlElement(Namespace = "http://www.cpandl.com")]
    public string TITLE;
    [XmlElement(Namespace ="http://www.cohowinery.com")]
    public Price PRICE;
}

public class Price
{
    [XmlAttribute(Namespace = "http://www.cpandl.com")]
    public string currency;
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public decimal price;
}
```

## <a name="see-also"></a><span data-ttu-id="b024f-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b024f-121">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="b024f-122">Strumento XML Schema Definition e serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="b024f-122">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="b024f-123">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="b024f-123">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="b024f-124">Classe XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="b024f-124">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)
- [<span data-ttu-id="b024f-125">Attributi che controllano la serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="b024f-125">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="b024f-126">Procedura: specificare un nome di elemento alternativo per un flusso XML</span><span class="sxs-lookup"><span data-stu-id="b024f-126">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [<span data-ttu-id="b024f-127">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="b024f-127">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="b024f-128">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="b024f-128">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
