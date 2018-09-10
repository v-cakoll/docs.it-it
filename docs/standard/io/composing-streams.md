---
title: Composizione dei flussi
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e52b827f337892c33ec61b9affa1cc646a759c5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44182464"
---
# <a name="composing-streams"></a><span data-ttu-id="bdef1-102">Composizione dei flussi</span><span class="sxs-lookup"><span data-stu-id="bdef1-102">Composing Streams</span></span>
<span data-ttu-id="bdef1-103">Un archivio di backup è un supporto di archiviazione, ad esempio un disco o la memoria.</span><span class="sxs-lookup"><span data-stu-id="bdef1-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="bdef1-104">Ogni tipo di archivio di backup implementa il flusso come implementazione della classe <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="bdef1-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="bdef1-105">Ogni tipo di flusso legge e scrive i byte da e nel relativo archivio di backup.</span><span class="sxs-lookup"><span data-stu-id="bdef1-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="bdef1-106">I flussi che si connettono agli archivi di backup sono chiamati flussi di base.</span><span class="sxs-lookup"><span data-stu-id="bdef1-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="bdef1-107">I flusso di base hanno costruttori con i parametri necessari per connettere il flusso all'archivio di backup.</span><span class="sxs-lookup"><span data-stu-id="bdef1-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="bdef1-108"><xref:System.IO.FileStream>, ad esempio, ha costruttori che specificano un parametro del percorso, che specifica come il file verrà condiviso dai processi e così via.</span><span class="sxs-lookup"><span data-stu-id="bdef1-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="bdef1-109">La progettazione delle classi <xref:System.IO> consente una composizione dei flussi semplificata.</span><span class="sxs-lookup"><span data-stu-id="bdef1-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="bdef1-110">I flussi di base possono essere collegati a uno o più flussi pass-through che forniscono la funzionalità desiderata.</span><span class="sxs-lookup"><span data-stu-id="bdef1-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="bdef1-111">Un reader o un writer può essere accodato alla fine della catena in modo che i tipi preferiti possano essere letti o scritti facilmente.</span><span class="sxs-lookup"><span data-stu-id="bdef1-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="bdef1-112">L'esempio di codice seguente crea un elemento **FileStream** attorno all'elemento `MyFile.txt` esistente per memorizzare nel buffer `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="bdef1-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="bdef1-113">Si noti che gli elementi **FileStream** vengono memorizzati nel buffer per impostazione predefinita. Viene quindi creato un elemento <xref:System.IO.StreamReader> per leggere i caratteri dal **FileStream**, che viene passato allo **StreamReader** come argomento del costruttore.</span><span class="sxs-lookup"><span data-stu-id="bdef1-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="bdef1-114"><xref:System.IO.StreamReader.ReadLine%2A> legge finché <xref:System.IO.StreamReader.Peek%2A> non trova più caratteri.</span><span class="sxs-lookup"><span data-stu-id="bdef1-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="bdef1-115">L'esempio di codice seguente crea un elemento **FileStream** attorno all'elemento `MyFile.txt` esistente per memorizzare nel buffer `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="bdef1-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="bdef1-116">Si noti che gli elementi **FileStream** vengono memorizzati nel buffer per impostazione predefinita. Viene quindi creato un **BinaryReader** per leggere i byte dal **FileStream**, che viene passato al **BinaryReader** come argomento del costruttore.</span><span class="sxs-lookup"><span data-stu-id="bdef1-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="bdef1-117"><xref:System.IO.BinaryReader.ReadByte%2A> legge finché <xref:System.IO.BinaryReader.PeekChar%2A> non trova più byte.</span><span class="sxs-lookup"><span data-stu-id="bdef1-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="bdef1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdef1-118">See also</span></span>

- <xref:System.IO.StreamReader>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
