---
title: 'Procedura: Suddividere in blocchi i dati serializzati'
description: È possibile suddividere i dati per evitare problemi con set di dati di grandi dimensioni. Implementare l'interfaccia IXmlSerializable per controllare la serializzazione e la deserializzazione.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- chunking serialized data
- data chunking
- binary serialization, chunking data
- large data set chunking
- serialization, chunking data
- serialization, examples
- binary serialization, examples
ms.assetid: 22f1b818-7e0d-428a-8680-f17d6ebdd185
ms.openlocfilehash: 860fdcae0d1937f53ee964d9d4631ec812b3d379
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379134"
---
# <a name="how-to-chunk-serialized-data"></a>Procedura: Suddividere in blocchi i dati serializzati

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Due problemi che si verificano durante l'invio di set di dati di grandi dimensioni nei messaggi del servizio Web sono:  
  
1. Un working set (memoria) di grandi dimensioni, dovuti alla memorizzazione dei dati nel buffer da parte del motore di serializzazione.  
  
2. Consumo di larghezza di banda non controllato, dovuto all'ingrandimento del 33 percento successivo alla codifica Base64.  
  
 Per risolvere questi problemi, implementare l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable> per controllare la serializzazione e la deserializzazione. In particolare, implementare i metodi <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> e <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> per suddividere i dati.  
  
### <a name="to-implement-server-side-chunking"></a>Per implementare il chunking lato server  
  
1. Sul server, il metodo Web deve disattivare la memorizzazione nel buffer ASP.NET e restituire un tipo che implementi <xref:System.Xml.Serialization.IXmlSerializable>.  
  
2. Il tipo che implementa <xref:System.Xml.Serialization.IXmlSerializable>, suddivide i dati nel metodo <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.  
  
### <a name="to-implement-client-side-processing"></a>Per implementare l'elaborazione lato client  
  
1. Modificare il metodo Web sul proxy client in modo che restituisca il tipo che implementa <xref:System.Xml.Serialization.IXmlSerializable>. È possibile usare <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> per eseguire automaticamente questa procedura ma tale operazione non viene mostrata in questo argomento.  
  
2. Implementare il metodo <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> per leggere il flusso di dati suddiviso e scrivere i byte su disco. Questa implementazione genera inoltre eventi relativi allo stato di avanzamento che possono essere utilizzati da un controllo grafico, ad esempio un indicatore di stato.  
  
## <a name="example"></a>Esempio  
Nell'esempio di codice riportato di seguito viene mostrato il metodo Web sul client che disattiva la memorizzazione nel buffer ASP.NET. L'esempio mostra inoltre l'implementazione lato client dell'interfaccia <xref:System.Xml.Serialization.IXmlSerializable> che suddivide i dati nel metodo <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.  
  
[!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
[!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Nel codice riportato di seguito vengono utilizzati i seguenti spazi dei nomi: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization> e <xref:System.Xml.Schema>.  
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione personalizzata](custom-serialization.md)
