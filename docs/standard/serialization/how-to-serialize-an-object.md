---
title: 'Procedura: serializzare un oggetto'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 76b6006c34b29e17ea725a5f7d104c1b085b5edc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="3c998-102">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="3c998-102">How to: Serialize an Object</span></span>
<span data-ttu-id="3c998-103">Per serializzare un oggetto, creare prima l'oggetto da serializzare e impostarne i campi e le proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="3c998-103">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="3c998-104">A tale scopo, è necessario determinare il formato di trasporto in cui deve essere archiviato il flusso XML, come flusso o come file.</span><span class="sxs-lookup"><span data-stu-id="3c998-104">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="3c998-105">Ad esempio, se il flusso XML deve essere salvato in forma permanente, creare un oggetto <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="3c998-105">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c998-106">Per altri esempi di serializzazione XML, vedere [Esempi di serializzazione XML](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="3c998-106">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="3c998-107">Per serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="3c998-107">To serialize an object</span></span>  
  
1.  <span data-ttu-id="3c998-108">Creare l'oggetto e impostarne le proprietà e i campi pubblici.</span><span class="sxs-lookup"><span data-stu-id="3c998-108">Create the object and set its public fields and properties.</span></span>  
  
2.  <span data-ttu-id="3c998-109">Construire un <xref:System.Xml.Serialization.XmlSerializer> che utilizza il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c998-109">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="3c998-110">Per ulteriori informazioni, vedere i costruttori della classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3c998-110">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3.  <span data-ttu-id="3c998-111">Chiamare il metodo <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> per generare un flusso XML o una rappresentazione del file dei campi e delle proprietà pubbliche dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c998-111">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="3c998-112">Nell'esempio riportato di seguito viene creato un file.</span><span class="sxs-lookup"><span data-stu-id="3c998-112">The following example creates a file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3c998-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c998-113">See Also</span></span>  
 [<span data-ttu-id="3c998-114">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="3c998-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="3c998-115">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="3c998-115">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
