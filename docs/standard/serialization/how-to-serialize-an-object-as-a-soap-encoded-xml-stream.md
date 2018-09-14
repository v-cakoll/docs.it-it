---
title: 'Procedura: serializzare un oggetto come flusso XML con codifica SOAP'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
ms.openlocfilehash: cdfa2c8c7a27806873217495ac09f7f20e82b6bc
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615378"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="dd180-102">Procedura: serializzare un oggetto come flusso XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="dd180-102">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="dd180-103">Dato che un messaggio SOAP viene creato con XML, è possibile usare <xref:System.Xml.Serialization.XmlSerializer> per serializzare le classi e generare messaggi SOAP codificati.</span><span class="sxs-lookup"><span data-stu-id="dd180-103">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="dd180-104">L'elemento XML ottenuto risulta conforme alla [sezione 5 del documento "Simple Object Access Protocol (SOAP) 1.1" del World Wide Web Consortium](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span><span class="sxs-lookup"><span data-stu-id="dd180-104">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="dd180-105">Quando si crea un servizio Web XML che comunica tramite messaggi SOAP, è possibile personalizzare il flusso XML applicando un set di attributi SOAP speciali a classi e membri di classi.</span><span class="sxs-lookup"><span data-stu-id="dd180-105">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="dd180-106">Per un elenco di attributi, vedere [Attributi per il controllo della serializzazione SOAP codificata](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="dd180-106">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="dd180-107">Per serializzare un oggetto come flusso XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="dd180-107">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1.  <span data-ttu-id="dd180-108">Creare la classe con lo [strumento XML Schema Definition (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="dd180-108">Create the class using the [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2.  <span data-ttu-id="dd180-109">Applicare uno o più degli attributi speciali disponibili in `System.Xml.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="dd180-109">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="dd180-110">Consultare l'elenco "Attributi per il controllo della serializzazione SOAP codificata".</span><span class="sxs-lookup"><span data-stu-id="dd180-110">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3.  <span data-ttu-id="dd180-111">Creare un `XmlTypeMapping` creando un nuovo `SoapReflectionImporter` e richiamando il metodo `ImportTypeMapping` con il tipo della classe serializzata.</span><span class="sxs-lookup"><span data-stu-id="dd180-111">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="dd180-112">L'esempio di codice seguente chiama il metodo `ImportTypeMapping` della classe `SoapReflectionImporter` per creare un `XmlTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="dd180-112">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
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
  
4.  <span data-ttu-id="dd180-113">Creare un'istanza della classe `XmlSerializer` passando `XmlTypeMapping` al costruttore <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.</span><span class="sxs-lookup"><span data-stu-id="dd180-113">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  <span data-ttu-id="dd180-114">Chiamare il metodo `Serialize` o `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="dd180-114">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd180-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd180-115">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd180-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd180-116">See also</span></span>

- [<span data-ttu-id="dd180-117">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="dd180-117">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
- [<span data-ttu-id="dd180-118">Attributi per il controllo della serializzazione SOAP codificata</span><span class="sxs-lookup"><span data-stu-id="dd180-118">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
- [<span data-ttu-id="dd180-119">Serializzazione XML con Servizi Web XML</span><span class="sxs-lookup"><span data-stu-id="dd180-119">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
- [<span data-ttu-id="dd180-120">Procedura: Serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="dd180-120">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
- [<span data-ttu-id="dd180-121">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="dd180-121">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
- [<span data-ttu-id="dd180-122">Procedura: Eseguire l'override della serializzazione XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="dd180-122">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)
