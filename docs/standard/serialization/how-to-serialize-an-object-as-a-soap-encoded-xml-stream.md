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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84291565"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Procedura: serializzare un oggetto come flusso XML con codifica SOAP
  
 Dato che un messaggio SOAP viene creato con XML, è possibile usare <xref:System.Xml.Serialization.XmlSerializer> per serializzare le classi e generare messaggi SOAP codificati. L'elemento XML ottenuto risulta conforme alla [sezione 5 del documento "Simple Object Access Protocol (SOAP) 1.1" del World Wide Web Consortium](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512). Quando si crea un servizio Web XML che comunica tramite messaggi SOAP, è possibile personalizzare il flusso XML applicando un set di attributi SOAP speciali a classi e membri di classi. Per un elenco di attributi, vedere [Attributi per il controllo della serializzazione SOAP codificata](attributes-that-control-encoded-soap-serialization.md).  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Per serializzare un oggetto come flusso XML con codifica SOAP  
  
1. Creare la classe con lo [strumento XML Schema Definition (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).  
  
2. Applicare uno o più degli attributi speciali disponibili in `System.Xml.Serialization`. Consultare l'elenco "Attributi per il controllo della serializzazione SOAP codificata".  
  
3. Creare un `XmlTypeMapping` creando un nuovo `SoapReflectionImporter` e richiamando il metodo `ImportTypeMapping` con il tipo della classe serializzata.  
  
     L'esempio di codice seguente chiama il metodo `ImportTypeMapping` della classe `SoapReflectionImporter` per creare un `XmlTypeMapping`.  
  
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
  
4. Creare un'istanza della classe `XmlSerializer` passando `XmlTypeMapping` al costruttore <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. Chiamare il metodo `Serialize` o `Deserialize`.  
  
## <a name="example"></a>Esempio  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione SOAP e XML](xml-and-soap-serialization.md)
- [Attributi che controllano la serializzazione SOAP codificata](attributes-that-control-encoded-soap-serialization.md)
- [Serializzazione XML con servizi Web XML](xml-serialization-with-xml-web-services.md)
- [Procedura: serializzare un oggetto](how-to-serialize-an-object.md)
- [Procedura: Deserializzare un oggetto](how-to-deserialize-an-object.md)
- [Procedura: eseguire l'override della serializzazione XML con codifica SOAP](how-to-override-encoded-soap-xml-serialization.md)
