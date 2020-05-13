---
title: 'Procedura: serializzare un oggetto'
description: Questo articolo illustra come serializzare un oggetto. Consente di selezionare un formato di trasporto in cui è archiviato il flusso XML, come flusso o come file.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: 63446df3fa2c931c839eda91c648cee961715f93
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377549"
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="becc0-104">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="becc0-104">How to: Serialize an Object</span></span>
<span data-ttu-id="becc0-105">Per serializzare un oggetto, creare prima l'oggetto da serializzare e impostarne i campi e le proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="becc0-105">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="becc0-106">A tale scopo, è necessario determinare il formato di trasporto in cui deve essere archiviato il flusso XML, come flusso o come file.</span><span class="sxs-lookup"><span data-stu-id="becc0-106">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="becc0-107">Ad esempio, se il flusso XML deve essere salvato in forma permanente, creare un oggetto <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="becc0-107">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="becc0-108">Per altri esempi di serializzazione XML, vedere [Esempi di serializzazione XML](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="becc0-108">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="becc0-109">Per serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="becc0-109">To serialize an object</span></span>  
  
1. <span data-ttu-id="becc0-110">Creare l'oggetto e impostarne le proprietà e i campi pubblici.</span><span class="sxs-lookup"><span data-stu-id="becc0-110">Create the object and set its public fields and properties.</span></span>  
  
2. <span data-ttu-id="becc0-111">Construire un <xref:System.Xml.Serialization.XmlSerializer> che utilizza il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="becc0-111">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="becc0-112">Per ulteriori informazioni, vedere i costruttori della classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="becc0-112">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3. <span data-ttu-id="becc0-113">Chiamare il metodo <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> per generare un flusso XML o una rappresentazione del file dei campi e delle proprietà pubbliche dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="becc0-113">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="becc0-114">Nell'esempio riportato di seguito viene creato un file.</span><span class="sxs-lookup"><span data-stu-id="becc0-114">The following example creates a file.</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="becc0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="becc0-115">See also</span></span>

- [<span data-ttu-id="becc0-116">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="becc0-116">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="becc0-117">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="becc0-117">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
