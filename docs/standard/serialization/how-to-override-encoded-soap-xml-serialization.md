---
title: "Procedura: eseguire l'override della serializzazione XML con codifica SOAP"
ms.date: 03/30/2017
helpviewer_keywords:
- overriding XML serialization
- SOAP, overriding encoded XML serialization
ms.assetid: d0791df8-04e3-46b4-a6be-fe0ed09267e8
ms.openlocfilehash: 1bc9b228e61ccb0852ae489d44c5b692c54b642d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922590"
---
# <a name="how-to-override-encoded-soap-xml-serialization"></a><span data-ttu-id="c9bfd-102">Procedura: eseguire l'override della serializzazione XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="c9bfd-102">How to: Override Encoded SOAP XML Serialization</span></span>

<span data-ttu-id="c9bfd-103">Il processo per l'esecuzione dell'override della serializzazione XML di oggetti come messaggi SOAP è simile al processo per l'esecuzione dell'override della serializzazione XML standard.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-103">The process for overriding XML serialization of objects as SOAP messages is similar to the process for overriding standard XML serialization.</span></span> <span data-ttu-id="c9bfd-104">Per informazioni sull'override della serializzazione XML standard, vedere [Procedura: Specificare un nome di elemento alternativo per un flusso XML](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span><span class="sxs-lookup"><span data-stu-id="c9bfd-104">For information about overriding standard XML serialization, see [How to: Specify an Alternate Element Name for an XML Stream](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span></span>

## <a name="to-override-serialization-of-objects-as-soap-messages"></a><span data-ttu-id="c9bfd-105">Per eseguire l'override della serializzazione di oggetti come messaggi SOAP</span><span class="sxs-lookup"><span data-stu-id="c9bfd-105">To override serialization of objects as SOAP messages</span></span>

1. <span data-ttu-id="c9bfd-106">Creare un'istanza della classe <xref:System.Xml.Serialization.SoapAttributeOverrides>.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-106">Create an instance of the <xref:System.Xml.Serialization.SoapAttributeOverrides> class.</span></span>

2. <span data-ttu-id="c9bfd-107">Creare un `SoapAttributes` per ogni membro della classe in fase di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-107">Create a `SoapAttributes` for each class member that is being serialized.</span></span>

3. <span data-ttu-id="c9bfd-108">Creare un'istanza di uno o più degli attributi che influiscono sulla serializzazione XML, in base alle proprie esigenze, sul membro in fase di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-108">Create an instance of one or more of the attributes that affect XML serialization, as appropriate, to the member being serialized.</span></span> <span data-ttu-id="c9bfd-109">Per ulteriori informazioni, vedere "Attributi per il controllo della serializzazione SOAP codificata".</span><span class="sxs-lookup"><span data-stu-id="c9bfd-109">For more information, see "Attributes That Control Encoded SOAP Serialization".</span></span>

4. <span data-ttu-id="c9bfd-110">Impostare la proprietà appropriata di `SoapAttributes` sull'attributo creato al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-110">Set the appropriate property of `SoapAttributes` to the attribute created in step 3.</span></span>

5. <span data-ttu-id="c9bfd-111">Aggiunta di `SoapAttributes` a `SoapAttributeOverrides`.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-111">Add `SoapAttributes` to `SoapAttributeOverrides`.</span></span>

6. <span data-ttu-id="c9bfd-112">Creare un `XmlTypeMapping` utilizzando la classe `SoapAttributeOverrides`.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-112">Create an `XmlTypeMapping` using the `SoapAttributeOverrides`.</span></span> <span data-ttu-id="c9bfd-113">Usare il metodo `SoapReflectionImporter.ImportTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-113">Use the `SoapReflectionImporter.ImportTypeMapping` method.</span></span>

7. <span data-ttu-id="c9bfd-114">Creare un `XmlSerializer` utilizzando `XmlTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-114">Create an `XmlSerializer` using `XmlTypeMapping`.</span></span>

8. <span data-ttu-id="c9bfd-115">Serializzare o deserializzare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-115">Serialize or deserialize the object.</span></span>

## <a name="example"></a><span data-ttu-id="c9bfd-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9bfd-116">Example</span></span>

<span data-ttu-id="c9bfd-117">Nell'esempio di codice riportato di seguito viene serializzato un file in due modi: nel primo, senza eseguire l'override del comportamento della classe `XmlSerializer` e nel secondo, eseguendo l'override del comportamento.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-117">The following code example serializes a file in two ways: first, without overriding the `XmlSerializer` class's behavior, and second, by overriding the behavior.</span></span> <span data-ttu-id="c9bfd-118">L'esempio contiene una classe denominata `Group` con più membri.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-118">The example contains a class named `Group` with several members.</span></span> <span data-ttu-id="c9bfd-119">I vari attributi, ad esempio `SoapElementAttribute`, sono stati applicati ai membri della classe.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-119">Various attributes, such as the `SoapElementAttribute`, have been applied to class members.</span></span> <span data-ttu-id="c9bfd-120">Quando la classe viene serializzata con il metodo `SerializeOriginal`, gli attributi controllano il contenuto del messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="c9bfd-120">When the class is serialized with the `SerializeOriginal` method, the attributes control the SOAP message content.</span></span> <span data-ttu-id="c9bfd-121">Quando viene chiamato il metodo `SerializeOverride`, il comportamento di `XmlSerializer` viene sottoposto a override tramite la creazione di vari attributi e l'impostazione delle proprietà di un `SoapAttributes` su tali attributi (in base alle proprie esigenze).</span><span class="sxs-lookup"><span data-stu-id="c9bfd-121">When the `SerializeOverride` method is called, the behavior of the `XmlSerializer` is overridden by creating various attributes and setting the properties of a `SoapAttributes` to those attributes (as appropriate).</span></span>

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;
using System.Xml.Schema;

public class Group
{
    [SoapAttribute (Namespace = "http://www.cpandl.com")]
    public string GroupName;

    [SoapAttribute(DataType = "base64Binary")]
    public Byte [] GroupNumber;

    [SoapAttribute(DataType = "date", AttributeName = "CreationDate")]
    public DateTime Today;
    [SoapElement(DataType = "nonNegativeInteger", ElementName = "PosInt")]
    public string PositiveInt;
    // This is ignored when serialized unless it is overridden.
    [SoapIgnore]
    public bool IgnoreThis;

    public GroupType Grouptype;

    [SoapInclude(typeof(Car))]
    public Vehicle myCar(string licNumber)
    {
        Vehicle v;
        if(licNumber == "")
            {
                v = new Car();
            v.licenseNumber = "!!!!!!";
        }
        else
        {
            v = new Car();
            v.licenseNumber = licNumber;
        }
        return v;
    }
}

public abstract class Vehicle
{
    public string licenseNumber;
    public DateTime makeDate;
}

public class Car: Vehicle
{
}

public enum GroupType
{
    // These enums can be overridden.
    small,
    large
}

public class Run
{
    public static void Main()
    {
        Run test = new Run();
        test.SerializeOriginal("SoapOriginal.xml");
        test.SerializeOverride("SoapOverrides.xml");
        test.DeserializeOriginal("SoapOriginal.xml");
        test.DeserializeOverride("SoapOverrides.xml");

    }
    public void SerializeOriginal(string filename)
    {
        // Creates an instance of the XmlSerializer class.
        XmlTypeMapping myMapping =
        (new SoapReflectionImporter().ImportTypeMapping(
        typeof(Group)));
        XmlSerializer mySerializer =
        new XmlSerializer(myMapping);

        // Writing the file requires a TextWriter.
        TextWriter writer = new StreamWriter(filename);

        // Creates an instance of the class that will be serialized.
        Group myGroup = new Group();

        // Sets the object properties.
        myGroup.GroupName = ".NET";

        Byte [] hexByte = new Byte[2]{Convert.ToByte(100),
        Convert.ToByte(50)};
        myGroup.GroupNumber = hexByte;

        DateTime myDate = new DateTime(2002,5,2);
        myGroup.Today = myDate;

        myGroup.PositiveInt= "10000";
        myGroup.IgnoreThis=true;
        myGroup.Grouptype= GroupType.small;
        Car thisCar =(Car)  myGroup.myCar("1234566");

        // Prints the license number just to prove the car was created.
        Console.WriteLine("License#: " + thisCar.licenseNumber + "\n");

        // Serializes the class and closes the TextWriter.
        mySerializer.Serialize(writer, myGroup);
        writer.Close();
    }

    public void SerializeOverride(string filename)
    {
        // Creates an instance of the XmlSerializer class
        // that overrides the serialization.
        XmlSerializer overRideSerializer = CreateOverrideSerializer();

        // Writing the file requires a TextWriter.
        TextWriter writer = new StreamWriter(filename);

        // Creates an instance of the class that will be serialized.
        Group myGroup = new Group();

        // Sets the object properties.
        myGroup.GroupName = ".NET";

        Byte [] hexByte = new Byte[2]{Convert.ToByte(100),
        Convert.ToByte(50)};
        myGroup.GroupNumber = hexByte;

        DateTime myDate = new DateTime(2002,5,2);
        myGroup.Today = myDate;

        myGroup.PositiveInt= "10000";
        myGroup.IgnoreThis=true;
        myGroup.Grouptype= GroupType.small;
        Car thisCar =(Car)  myGroup.myCar("1234566");

        // Serializes the class and closes the TextWriter.
        overRideSerializer.Serialize(writer, myGroup);
         writer.Close();
    }

    public void DeserializeOriginal(string filename)
    {
        // Creates an instance of the XmlSerializer class.
        XmlTypeMapping myMapping =
        (new SoapReflectionImporter().ImportTypeMapping(
        typeof(Group)));
        XmlSerializer mySerializer =
        new XmlSerializer(myMapping);

        TextReader reader = new StreamReader(filename);

        // Deserializes and casts the object.
        Group myGroup;
        myGroup = (Group) mySerializer.Deserialize(reader);

        Console.WriteLine(myGroup.GroupName);
        Console.WriteLine(myGroup.GroupNumber[0]);
        Console.WriteLine(myGroup.GroupNumber[1]);
        Console.WriteLine(myGroup.Today);
        Console.WriteLine(myGroup.PositiveInt);
        Console.WriteLine(myGroup.IgnoreThis);
        Console.WriteLine();
    }

    public void DeserializeOverride(string filename)
    {
        // Creates an instance of the XmlSerializer class.
        XmlSerializer overRideSerializer = CreateOverrideSerializer();
        // Reading the file requires a TextReader.
        TextReader reader = new StreamReader(filename);

        // Deserializes and casts the object.
        Group myGroup;
        myGroup = (Group) overRideSerializer.Deserialize(reader);

        Console.WriteLine(myGroup.GroupName);
        Console.WriteLine(myGroup.GroupNumber[0]);
        Console.WriteLine(myGroup.GroupNumber[1]);
        Console.WriteLine(myGroup.Today);
        Console.WriteLine(myGroup.PositiveInt);
        Console.WriteLine(myGroup.IgnoreThis);
    }

    private XmlSerializer CreateOverrideSerializer()
    {
        SoapAttributeOverrides mySoapAttributeOverrides =
        new SoapAttributeOverrides();
        SoapAttributes soapAtts = new SoapAttributes();

        SoapElementAttribute mySoapElement = new SoapElementAttribute();
        mySoapElement.ElementName = "xxxx";
        soapAtts.SoapElement = mySoapElement;
        mySoapAttributeOverrides.Add(typeof(Group), "PositiveInt",
        soapAtts);

        // Overrides the IgnoreThis property.
        SoapIgnoreAttribute myIgnore = new SoapIgnoreAttribute();
        soapAtts = new SoapAttributes();
        soapAtts.SoapIgnore = false;
        mySoapAttributeOverrides.Add(typeof(Group), "IgnoreThis",
        soapAtts);

        // Overrides the GroupType enumeration.
        soapAtts = new SoapAttributes();
        SoapEnumAttribute xSoapEnum = new SoapEnumAttribute();
        xSoapEnum.Name = "Over1000";
        soapAtts.SoapEnum = xSoapEnum;

        // Adds the SoapAttributes to the
        // mySoapAttributeOverrides.
        mySoapAttributeOverrides.Add(typeof(GroupType), "large",
        soapAtts);

        // Creates a second enumeration and adds it.
        soapAtts = new SoapAttributes();
        xSoapEnum = new SoapEnumAttribute();
        xSoapEnum.Name = "ZeroTo1000";
        soapAtts.SoapEnum = xSoapEnum;
        mySoapAttributeOverrides.Add(typeof(GroupType), "small",
        soapAtts);

        // Overrides the Group type.
        soapAtts = new SoapAttributes();
        SoapTypeAttribute soapType = new SoapTypeAttribute();
        soapType.TypeName = "Team";
        soapAtts.SoapType = soapType;
        mySoapAttributeOverrides.Add(typeof(Group),soapAtts);

        // Creates an XmlTypeMapping that is used to create an instance
        // of the XmlSerializer class. Then returns the XmlSerializer.
        XmlTypeMapping myMapping = (new SoapReflectionImporter(
        mySoapAttributeOverrides)).ImportTypeMapping(typeof(Group));

        XmlSerializer ser = new XmlSerializer(myMapping);
        return ser;
    }
}
```

## <a name="see-also"></a><span data-ttu-id="c9bfd-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c9bfd-122">See also</span></span>

- [<span data-ttu-id="c9bfd-123">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="c9bfd-123">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- [<span data-ttu-id="c9bfd-124">Attributi che controllano la serializzazione SOAP codificata</span><span class="sxs-lookup"><span data-stu-id="c9bfd-124">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="c9bfd-125">Serializzazione XML con servizi Web XML</span><span class="sxs-lookup"><span data-stu-id="c9bfd-125">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)
- [<span data-ttu-id="c9bfd-126">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bfd-126">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="c9bfd-127">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bfd-127">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [<span data-ttu-id="c9bfd-128">Procedura: Serializzare un oggetto come flusso XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="c9bfd-128">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
