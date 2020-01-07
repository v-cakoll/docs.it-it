---
title: Come deserializzare un oggetto utilizzando XmlSerializer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: c24ba466a208fe5abdbf565169c41c4ee3f47482
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559898"
---
# <a name="how-to-deserialize-an-object-using-xmlserializer"></a>Come deserializzare un oggetto utilizzando XmlSerializer

Quando si deserializza un oggetto, il formato di trasporto determina se verrà creato un flusso o un oggetto file. Una volta determinato il formato di trasporto, è possibile chiamare i metodi <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> o <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, in base alle necessità.

## <a name="to-deserialize-an-object"></a>Per deserializzare un oggetto

1. Construire un <xref:System.Xml.Serialization.XmlSerializer> che utilizza il tipo dell'oggetto da deserializzare.

1. Chiamare il metodo <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> per produrre una replica dell'oggetto. Durante la deserializzazione, è necessario eseguire il cast dell'oggetto restituito al tipo dell'originale, come illustrato nell'esempio seguente, che deserializza l'oggetto da un file (sebbene possa anche essere deserializzato da un flusso).

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

## <a name="see-also"></a>Vedere anche

- [Introduzione alla serializzazione XML](introducing-xml-serialization.md)
- [Procedura: serializzare un oggetto](how-to-serialize-an-object.md)
