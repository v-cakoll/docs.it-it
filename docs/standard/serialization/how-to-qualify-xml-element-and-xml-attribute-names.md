---
title: 'Procedura: qualificare nomi di attributi ed elementi XML'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: 6b4d58f6b5bf23cbce2ace8fb40730d7b73994de
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2018
ms.locfileid: "42908044"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="accbc-102">Procedura: qualificare nomi di attributi ed elementi XML</span><span class="sxs-lookup"><span data-stu-id="accbc-102">How to: Qualify XML Element and XML Attribute Names</span></span>

<span data-ttu-id="accbc-103">Spazi dei nomi XML contenuti nelle istanze del <xref:System.Xml.Serialization.XmlSerializerNamespaces> classe deve essere conforme alla specifica del World Wide Web Consortium (W3C) denominata [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span><span class="sxs-lookup"><span data-stu-id="accbc-103">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (W3C) specification called [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span></span>

<span data-ttu-id="accbc-104">Gli spazi dei nomi XML forniscono un metodo che consente di qualificare i nomi di elementi XML e attributi XML nei documenti XML.</span><span class="sxs-lookup"><span data-stu-id="accbc-104">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="accbc-105">Un nome completo è composto da un prefisso e da un nome locale, separati dal carattere di due punti.</span><span class="sxs-lookup"><span data-stu-id="accbc-105">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="accbc-106">Il prefisso funge soltanto da segnaposto ed è mappato a un URI che specifica uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="accbc-106">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="accbc-107">La combinazione dello spazio dei nomi URI gestito a livello universale e del nome locale genera un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="accbc-107">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>

<span data-ttu-id="accbc-108">Tramite la creazione di un'istanza di `XmlSerializerNamespaces` e l'aggiunta delle coppie dello spazio dei nomi all'oggetto, è possibile specificare i prefissi utilizzati in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="accbc-108">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>

## <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="accbc-109">Per creare nomi completi in un documento XML</span><span class="sxs-lookup"><span data-stu-id="accbc-109">To create qualified names in an XML document</span></span>

1. <span data-ttu-id="accbc-110">Creare un'istanza della classe `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="accbc-110">Create an instance of the `XmlSerializerNamespaces` class.</span></span>

2. <span data-ttu-id="accbc-111">Aggiungere tutte le coppie di prefissi e spazi dei nomi a `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="accbc-111">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>

3. <span data-ttu-id="accbc-112">Applicare l'attributo `System.Xml.Serialization` appropriato a ciascun membro o classe che <xref:System.Xml.Serialization.XmlSerializer> deve serializzare in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="accbc-112">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>

  <span data-ttu-id="accbc-113">Gli attributi disponibili sono: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> e <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="accbc-113">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>

4. <span data-ttu-id="accbc-114">Impostare la proprietà `Namespace` di ciascun attributo su uno dei valori dello spazio dei nomi da `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="accbc-114">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>

5. <span data-ttu-id="accbc-115">Passare `XmlSerializerNamespaces` al metodo `Serialize` di `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="accbc-115">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>

## <a name="example"></a><span data-ttu-id="accbc-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="accbc-116">Example</span></span>

<span data-ttu-id="accbc-117">Nell'esempio riportato di seguito viene creato un oggetto `XmlSerializerNamespaces`, a cui vengono aggiunte due coppie di prefisso e spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="accbc-117">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="accbc-118">Il codice crea un `XmlSerializer` utilizzato per serializzare un'istanza della classe `Books`.</span><span class="sxs-lookup"><span data-stu-id="accbc-118">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="accbc-119">Il codice chiama il metodo `Serialize` con `XmlSerializerNamespaces`, consentendo all'XML di contenere spazi dei nomi con prefissi.</span><span class="sxs-lookup"><span data-stu-id="accbc-119">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>

```vb
Option Explicit
public class Price
{
    [XmlAttribute(Namespace = "http://www.cpandl.com")]
    public string currency;
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public decimal price;
}

Option Strict

Imports System
Imports System.IO
Imports System.Xml
Imports System.Xml.Serialization

Public Class Run

    Public Shared Sub Main()
        Dim test As New Run()
        test.SerializeObject("XmlNamespaces.xml")
    End Sub 'Main

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
End Class

Public Class Books
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public Book As Book
End Class 'Books

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
    Public <XmlElement([Namespace] := "http://www.cohowinery.com")> _
        price As Decimal
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;

public class Run
{
    public static void Main()
    {
        Run test = new Run();
        test.SerializeObject("XmlNamespaces.xml");
    }
    public void SerializeObject(string filename)
    {
        XmlSerializer mySerializer = new XmlSerializer(typeof(Books));
        // Writing a file requires a TextWriter.
        TextWriter myWriter = new StreamWriter(filename);

        // Creates an XmlSerializerNamespaces and adds two
        // prefix-namespace pairs.
        XmlSerializerNamespaces myNamespaces =
        new XmlSerializerNamespaces();
        myNamespaces.Add("books", "http://www.cpandl.com");
        myNamespaces.Add("money", "http://www.cohowinery.com");

        // Creates a Book.
        Book myBook = new Book();
        myBook.TITLE = "A Book Title";
        Price myPrice = new Price();
        myPrice.price = (decimal) 9.95;
        myPrice.currency = "US Dollar";
        myBook.PRICE = myPrice;
        Books myBooks = new Books();
        myBooks.Book = myBook;
        mySerializer.Serialize(myWriter,myBooks,myNamespaces);
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
```

## <a name="see-also"></a><span data-ttu-id="accbc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="accbc-120">See Also</span></span>

<span data-ttu-id="accbc-121"><xref:System.Xml.Serialization.XmlSerializer>
[La strumento XML Schema Definition e serializzazione XML](the-xml-schema-definition-tool-and-xml-serialization.md)
[Introduzione alla serializzazione XML](introducing-xml-serialization.md)
[classe XmlSerializer](xref:System.Xml.Serialization.XmlSerializer) 
 [Gli attributi che controllano la serializzazione XML](attributes-that-control-xml-serialization.md)
[procedura: specificare un nome di elemento alternativo per un Stream XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
[procedura: serializzare un oggetto](how-to-serialize-an-object.md) 
 [Procedura: deserializzare un oggetto](how-to-deserialize-an-object.md)</span><span class="sxs-lookup"><span data-stu-id="accbc-121"><xref:System.Xml.Serialization.XmlSerializer>
[The XML Schema Definition Tool and XML Serialization](the-xml-schema-definition-tool-and-xml-serialization.md)
[Introducing XML Serialization](introducing-xml-serialization.md)
[XmlSerializer Class](xref:System.Xml.Serialization.XmlSerializer)
[Attributes That Control XML Serialization](attributes-that-control-xml-serialization.md)
[How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
[How to: Serialize an Object](how-to-serialize-an-object.md)
[How to: Deserialize an Object](how-to-deserialize-an-object.md)</span></span>