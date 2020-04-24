---
title: 'Procedura: Suddividere in blocchi i dati serializzati'
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
ms.openlocfilehash: 6a39997d8854d525146c044ed4bbf939de615d3f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602427"
---
# <a name="how-to-chunk-serialized-data"></a><span data-ttu-id="434e3-102">Procedura: Suddividere in blocchi i dati serializzati</span><span class="sxs-lookup"><span data-stu-id="434e3-102">How to: chunk serialized data</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="434e3-103">Due problemi che si verificano durante l'invio di set di dati di grandi dimensioni nei messaggi del servizio Web sono:</span><span class="sxs-lookup"><span data-stu-id="434e3-103">Two issues that occur when sending large data sets in Web service messages are:</span></span>  
  
1. <span data-ttu-id="434e3-104">Un working set (memoria) di grandi dimensioni, dovuti alla memorizzazione dei dati nel buffer da parte del motore di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="434e3-104">A large working set (memory) due to buffering by the serialization engine.</span></span>  
  
2. <span data-ttu-id="434e3-105">Consumo di larghezza di banda non controllato, dovuto all'ingrandimento del 33 percento successivo alla codifica Base64.</span><span class="sxs-lookup"><span data-stu-id="434e3-105">Inordinate bandwidth consumption due to 33 percent inflation after Base64 encoding.</span></span>  
  
 <span data-ttu-id="434e3-106">Per risolvere questi problemi, implementare l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable> per controllare la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="434e3-106">To solve these problems, implement the <xref:System.Xml.Serialization.IXmlSerializable> interface to control the serialization and deserialization.</span></span> <span data-ttu-id="434e3-107">In particolare, implementare i metodi <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> e <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> per suddividere i dati.</span><span class="sxs-lookup"><span data-stu-id="434e3-107">Specifically, implement the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> and <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> methods to chunk the data.</span></span>  
  
### <a name="to-implement-server-side-chunking"></a><span data-ttu-id="434e3-108">Per implementare il chunking lato server</span><span class="sxs-lookup"><span data-stu-id="434e3-108">To implement server-side chunking</span></span>  
  
1. <span data-ttu-id="434e3-109">Sul server, il metodo Web deve disattivare la memorizzazione nel buffer ASP.NET e restituire un tipo che implementi <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="434e3-109">On the server machine, the Web method must turn off ASP.NET buffering and return a type that implements <xref:System.Xml.Serialization.IXmlSerializable>.</span></span>  
  
2. <span data-ttu-id="434e3-110">Il tipo che implementa <xref:System.Xml.Serialization.IXmlSerializable>, suddivide i dati nel metodo <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.</span><span class="sxs-lookup"><span data-stu-id="434e3-110">The type that implements <xref:System.Xml.Serialization.IXmlSerializable> chunks the data in the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> method.</span></span>  
  
### <a name="to-implement-client-side-processing"></a><span data-ttu-id="434e3-111">Per implementare l'elaborazione lato client</span><span class="sxs-lookup"><span data-stu-id="434e3-111">To implement client-side processing</span></span>  
  
1. <span data-ttu-id="434e3-112">Modificare il metodo Web sul proxy client in modo che restituisca il tipo che implementa <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="434e3-112">Alter the Web method on the client proxy to return the type that implements <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="434e3-113">È possibile usare <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> per eseguire automaticamente questa procedura ma tale operazione non viene mostrata in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="434e3-113">You can use a <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> to do this automatically, but this isn't shown here.</span></span>  
  
2. <span data-ttu-id="434e3-114">Implementare il metodo <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> per leggere il flusso di dati suddiviso e scrivere i byte su disco.</span><span class="sxs-lookup"><span data-stu-id="434e3-114">Implement the <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> method to read the chunked data stream and write the bytes to disk.</span></span> <span data-ttu-id="434e3-115">Questa implementazione genera inoltre eventi relativi allo stato di avanzamento che possono essere utilizzati da un controllo grafico, ad esempio un indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="434e3-115">This implementation also raises progress events that can be used by a graphic control, such as a progress bar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="434e3-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="434e3-116">Example</span></span>  
<span data-ttu-id="434e3-117">Nell'esempio di codice riportato di seguito viene mostrato il metodo Web sul client che disattiva la memorizzazione nel buffer ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="434e3-117">The following code example shows the Web method on the client that turns off ASP.NET buffering.</span></span> <span data-ttu-id="434e3-118">L'esempio mostra inoltre l'implementazione lato client dell'interfaccia <xref:System.Xml.Serialization.IXmlSerializable> che suddivide i dati nel metodo <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.</span><span class="sxs-lookup"><span data-stu-id="434e3-118">It also shows the client-side implementation of the <xref:System.Xml.Serialization.IXmlSerializable> interface that chunks the data in the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> method.</span></span>  
  
[!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
[!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="434e3-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="434e3-119">Compiling the code</span></span>  
  
- <span data-ttu-id="434e3-120">Nel codice riportato di seguito vengono utilizzati i seguenti spazi dei nomi: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization> e <xref:System.Xml.Schema>.</span><span class="sxs-lookup"><span data-stu-id="434e3-120">The code uses the following namespaces: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization>, and <xref:System.Xml.Schema>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434e3-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="434e3-121">See also</span></span>

- [<span data-ttu-id="434e3-122">Serializzazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="434e3-122">Custom Serialization</span></span>](custom-serialization.md)
