---
title: 'Procedura: deserializzare un oggetto'
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
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b28d80951cb2d71f8f8fb532710f738fecdf8508
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-deserialize-an-object"></a>Procedura: deserializzare un oggetto
Quando si deserializza un oggetto, il formato di trasporto determina se verrà creato un flusso o un oggetto file. Una volta determinato il formato di trasporto, è possibile chiamare i metodi <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> o <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, in base alle necessità.  
  
### <a name="to-deserialize-an-object"></a>Per deserializzare un oggetto  
  
1.  Construire un <xref:System.Xml.Serialization.XmlSerializer> che utilizza il tipo dell'oggetto da deserializzare.  
  
2.  Chiamare il metodo <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> per produrre una replica dell'oggetto. Durante la deserializzazione, è necessario eseguire il cast dell'oggetto restituito al tipo dell'originale, come illustrato nell'esempio riportato di seguito, in cui viene deserializzato l'oggetto in un file (sebbene possa anche essere deserializzato in un flusso).  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alla serializzazione XML](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [Procedura: Serializzare un oggetto](../../../docs/standard/serialization/how-to-serialize-an-object.md)
