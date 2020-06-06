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
ms.openlocfilehash: e9c7ba250995db1c7a701de346b18661892e7e23
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84291552"
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="1ba9e-104">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="1ba9e-104">How to: Serialize an Object</span></span>
<span data-ttu-id="1ba9e-105">Per serializzare un oggetto, creare prima l'oggetto da serializzare e impostarne i campi e le proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-105">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="1ba9e-106">A tale scopo, è necessario determinare il formato di trasporto in cui deve essere archiviato il flusso XML, come flusso o come file.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-106">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="1ba9e-107">Ad esempio, se il flusso XML deve essere salvato in forma permanente, creare un oggetto <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-107">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ba9e-108">Per altri esempi di serializzazione XML, vedere [Esempi di serializzazione XML](examples-of-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="1ba9e-108">For more examples of XML serialization, see [Examples of XML Serialization](examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="1ba9e-109">Per serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="1ba9e-109">To serialize an object</span></span>  
  
1. <span data-ttu-id="1ba9e-110">Creare l'oggetto e impostarne le proprietà e i campi pubblici.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-110">Create the object and set its public fields and properties.</span></span>  
  
2. <span data-ttu-id="1ba9e-111">Construire un <xref:System.Xml.Serialization.XmlSerializer> che utilizza il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-111">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="1ba9e-112">Per ulteriori informazioni, vedere i costruttori della classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-112">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3. <span data-ttu-id="1ba9e-113">Chiamare il metodo <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> per generare un flusso XML o una rappresentazione del file dei campi e delle proprietà pubbliche dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-113">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="1ba9e-114">Nell'esempio riportato di seguito viene creato un file.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-114">The following example creates a file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ba9e-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1ba9e-115">See also</span></span>

- [<span data-ttu-id="1ba9e-116">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="1ba9e-116">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="1ba9e-117">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="1ba9e-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
