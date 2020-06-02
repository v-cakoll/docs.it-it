---
title: 'Procedura: serializzare un oggetto come flusso XML con codifica SOAP'
description: Informazioni su come serializzare un oggetto come flusso XML con codifica SOAP. La classe XmlSerializer può essere utilizzata per serializzare classi e generare messaggi SOAP codificati.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
ms.openlocfilehash: 1d38c4e334439ef41b4d4429e52cff04c6463573
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291565"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="22d55-104">Procedura: serializzare un oggetto come flusso XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="22d55-104">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="22d55-105">Dato che un messaggio SOAP viene creato con XML, è possibile usare <xref:System.Xml.Serialization.XmlSerializer> per serializzare le classi e generare messaggi SOAP codificati.</span><span class="sxs-lookup"><span data-stu-id="22d55-105">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="22d55-106">L'elemento XML ottenuto risulta conforme alla [sezione 5 del documento "Simple Object Access Protocol (SOAP) 1.1" del World Wide Web Consortium](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span><span class="sxs-lookup"><span data-stu-id="22d55-106">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="22d55-107">Quando si crea un servizio Web XML che comunica tramite messaggi SOAP, è possibile personalizzare il flusso XML applicando un set di attributi SOAP speciali a classi e membri di classi.</span><span class="sxs-lookup"><span data-stu-id="22d55-107">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="22d55-108">Per un elenco di attributi, vedere [Attributi per il controllo della serializzazione SOAP codificata](attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="22d55-108">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="22d55-109">Per serializzare un oggetto come flusso XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="22d55-109">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1. <span data-ttu-id="22d55-110">Creare la classe con lo [strumento XML Schema Definition (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="22d55-110">Create the class using the [XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2. <span data-ttu-id="22d55-111">Applicare uno o più degli attributi speciali disponibili in `System.Xml.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="22d55-111">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="22d55-112">Consultare l'elenco "Attributi per il controllo della serializzazione SOAP codificata".</span><span class="sxs-lookup"><span data-stu-id="22d55-112">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3. <span data-ttu-id="22d55-113">Creare un `XmlTypeMapping` creando un nuovo `SoapReflectionImporter` e richiamando il metodo `ImportTypeMapping` con il tipo della classe serializzata.</span><span class="sxs-lookup"><span data-stu-id="22d55-113">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="22d55-114">L'esempio di codice seguente chiama il metodo `ImportTypeMapping` della classe `SoapReflectionImporter` per creare un `XmlTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="22d55-114">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping =
        New SoapReflectionImporter().ImportTypeMapping(GetType(Group))  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping =
        new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
    ```  
  
4. <span data-ttu-id="22d55-115">Creare un'istanza della classe `XmlSerializer` passando `XmlTypeMapping` al costruttore <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.</span><span class="sxs-lookup"><span data-stu-id="22d55-115">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. <span data-ttu-id="22d55-116">Chiamare il metodo `Serialize` o `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="22d55-116">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22d55-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="22d55-117">Example</span></span>  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping =
    New SoapReflectionImporter().ImportTypeMapping(GetType(Group))
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping =
    new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## <a name="see-also"></a><span data-ttu-id="22d55-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22d55-118">See also</span></span>

- [<span data-ttu-id="22d55-119">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="22d55-119">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="22d55-120">Attributi che controllano la serializzazione SOAP codificata</span><span class="sxs-lookup"><span data-stu-id="22d55-120">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="22d55-121">Serializzazione XML con servizi Web XML</span><span class="sxs-lookup"><span data-stu-id="22d55-121">XML Serialization with XML Web Services</span></span>](xml-serialization-with-xml-web-services.md)
- [<span data-ttu-id="22d55-122">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="22d55-122">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="22d55-123">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="22d55-123">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
- [<span data-ttu-id="22d55-124">Procedura: eseguire l'override della serializzazione XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="22d55-124">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)
