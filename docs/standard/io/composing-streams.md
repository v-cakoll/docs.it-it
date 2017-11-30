---
title: Composizione dei flussi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75800210a52620c5b08a01c5f8fa888bf40843fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="composing-streams"></a><span data-ttu-id="3741d-102">Composizione dei flussi</span><span class="sxs-lookup"><span data-stu-id="3741d-102">Composing Streams</span></span>
<span data-ttu-id="3741d-103">Un archivio di backup è un supporto di archiviazione, ad esempio un disco o memoria.</span><span class="sxs-lookup"><span data-stu-id="3741d-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="3741d-104">Ogni archivio di backup diversi implementa il flusso come un'implementazione del <xref:System.IO.Stream> classe.</span><span class="sxs-lookup"><span data-stu-id="3741d-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="3741d-105">Ogni tipo di flusso legge e scrive byte da e in un archivio di backup specificato.</span><span class="sxs-lookup"><span data-stu-id="3741d-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="3741d-106">Flussi di connettono ad archivi di backup vengono chiamati i flussi di base.</span><span class="sxs-lookup"><span data-stu-id="3741d-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="3741d-107">Flussi di base hanno costruttori che accettano i presentano per il flusso di connettersi all'archivio di backup.</span><span class="sxs-lookup"><span data-stu-id="3741d-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="3741d-108">Ad esempio, <xref:System.IO.FileStream> dispone di costruttori che specificano un parametro di percorso che specifica come il file verrà condiviso dai processi e così via.</span><span class="sxs-lookup"><span data-stu-id="3741d-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="3741d-109">La progettazione della <xref:System.IO> classi fornisce la composizione di flussi.</span><span class="sxs-lookup"><span data-stu-id="3741d-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="3741d-110">Flussi di base possono essere collegati a uno o più flussi di pass-through che forniscono la funzionalità desiderata.</span><span class="sxs-lookup"><span data-stu-id="3741d-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="3741d-111">Un lettore o writer può essere collegato alla fine della catena in modo che i tipi Preferiti possono essere letto o scritti facilmente.</span><span class="sxs-lookup"><span data-stu-id="3741d-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="3741d-112">L'esempio di codice seguente crea un **FileStream** intorno esistente `MyFile.txt` per inserire nel buffer `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="3741d-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="3741d-113">(Si noti che **FileStream** vengono memorizzati nel buffer per impostazione predefinita.) Successivamente, un <xref:System.IO.StreamReader> viene creato per leggere caratteri dal **FileStream**, che viene passato al **StreamReader** come argomento del costruttore.</span><span class="sxs-lookup"><span data-stu-id="3741d-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="3741d-114"><xref:System.IO.StreamReader.ReadLine%2A>legge fino a quando <xref:System.IO.StreamReader.Peek%2A> non trova più caratteri.</span><span class="sxs-lookup"><span data-stu-id="3741d-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="3741d-115">L'esempio di codice seguente crea un **FileStream** intorno esistente `MyFile.txt` per inserire nel buffer `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="3741d-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="3741d-116">(Si noti che **FileStream** vengono memorizzati nel buffer per impostazione predefinita.) Successivamente, un **BinaryReader** viene creato per leggere i byte dal **FileStream**, che viene passato al **BinaryReader** come argomento del costruttore.</span><span class="sxs-lookup"><span data-stu-id="3741d-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="3741d-117"><xref:System.IO.BinaryReader.ReadByte%2A>legge fino a quando <xref:System.IO.BinaryReader.PeekChar%2A> non trova più byte.</span><span class="sxs-lookup"><span data-stu-id="3741d-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="3741d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3741d-118">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
