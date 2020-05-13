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
# <a name="how-to-serialize-an-object"></a>Procedura: serializzare un oggetto
Per serializzare un oggetto, creare prima l'oggetto da serializzare e impostarne i campi e le proprietà pubbliche. A tale scopo, è necessario determinare il formato di trasporto in cui deve essere archiviato il flusso XML, come flusso o come file. Ad esempio, se il flusso XML deve essere salvato in forma permanente, creare un oggetto <xref:System.IO.FileStream>.  
  
> [!NOTE]
> Per altri esempi di serializzazione XML, vedere [Esempi di serializzazione XML](../../../docs/standard/serialization/examples-of-xml-serialization.md).  
  
### <a name="to-serialize-an-object"></a>Per serializzare un oggetto  
  
1. Creare l'oggetto e impostarne le proprietà e i campi pubblici.  
  
2. Construire un <xref:System.Xml.Serialization.XmlSerializer> che utilizza il tipo dell'oggetto. Per ulteriori informazioni, vedere i costruttori della classe <xref:System.Xml.Serialization.XmlSerializer>.  
  
3. Chiamare il metodo <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> per generare un flusso XML o una rappresentazione del file dei campi e delle proprietà pubbliche dell'oggetto. Nell'esempio riportato di seguito viene creato un file.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alla serializzazione XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Procedura: Deserializzare un oggetto](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
