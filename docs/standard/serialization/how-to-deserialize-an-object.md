---
title: Come deserializzare un oggetto utilizzando XmlSerializer
description: Informazioni su come deserializzare un oggetto. Il formato di trasporto determina se creare un oggetto Stream o file.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: e08ae0d77539219223650fd3bcbd1bcee4df2739
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "83379108"
---
# <a name="how-to-deserialize-an-object-using-xmlserializer"></a><span data-ttu-id="64ba9-104">Come deserializzare un oggetto utilizzando XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="64ba9-104">How to deserialize an object using XmlSerializer</span></span>

<span data-ttu-id="64ba9-105">Quando si deserializza un oggetto, il formato di trasporto determina se verrà creato un flusso o un oggetto file.</span><span class="sxs-lookup"><span data-stu-id="64ba9-105">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="64ba9-106">Una volta determinato il formato di trasporto, è possibile chiamare i metodi <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> o <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="64ba9-106">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>

## <a name="to-deserialize-an-object"></a><span data-ttu-id="64ba9-107">Per deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="64ba9-107">To deserialize an object</span></span>

1. <span data-ttu-id="64ba9-108">Construire un <xref:System.Xml.Serialization.XmlSerializer> che utilizza il tipo dell'oggetto da deserializzare.</span><span class="sxs-lookup"><span data-stu-id="64ba9-108">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>

1. <span data-ttu-id="64ba9-109">Chiamare il metodo <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> per produrre una replica dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="64ba9-109">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="64ba9-110">Durante la deserializzazione, è necessario eseguire il cast dell'oggetto restituito al tipo dell'originale, come illustrato nell'esempio seguente, che deserializza l'oggetto da un file (sebbene possa anche essere deserializzato da un flusso).</span><span class="sxs-lookup"><span data-stu-id="64ba9-110">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object from a file (although it could also be deserialized from a stream).</span></span>

    ```vb
    ' Construct an instance of the XmlSerializer with the type
    ' of object that is being deserialized.
    Dim mySerializer As New XmlSerializer(GetType(MySerializableClass))
    ' To read the file, create a FileStream.
    Dim myFileStream As New FileStream("myFileName.xml", FileMode.Open)
    ' Call the Deserialize method and cast to the object type.
    Dim myObject = CType( _
    mySerializer.Deserialize(myFileStream), MySerializableClass)
    ```

    ```csharp
    // Construct an instance of the XmlSerializer with the type
    // of object that is being deserialized.
    var mySerializer = new XmlSerializer(typeof(MySerializableClass));
    // To read the file, create a FileStream.
    var myFileStream = new FileStream("myFileName.xml", FileMode.Open);
    // Call the Deserialize method and cast to the object type.
    var myObject = (MySerializableClass) mySerializer.Deserialize(myFileStream)
    ```

## <a name="see-also"></a><span data-ttu-id="64ba9-111">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="64ba9-111">See also</span></span>

- [<span data-ttu-id="64ba9-112">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="64ba9-112">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="64ba9-113">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="64ba9-113">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
