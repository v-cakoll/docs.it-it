---
title: Comporre flussi
ms.date: 01/21/2019
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
ms.openlocfilehash: 689cc9537cd7a5fe6a677d42e5790bbcf1b3aefa
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708148"
---
# <a name="compose-streams"></a><span data-ttu-id="950c1-102">Comporre flussi</span><span class="sxs-lookup"><span data-stu-id="950c1-102">Compose streams</span></span>
<span data-ttu-id="950c1-103">Un *archivio di backup* è un supporto di archiviazione, ad esempio un disco o la memoria.</span><span class="sxs-lookup"><span data-stu-id="950c1-103">A *backing store* is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="950c1-104">Ogni tipo di archivio di backup implementa il flusso come implementazione della classe <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="950c1-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> 

<span data-ttu-id="950c1-105">Ogni tipo di flusso legge e scrive i byte da e nel relativo archivio di backup.</span><span class="sxs-lookup"><span data-stu-id="950c1-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="950c1-106">I flussi che si connettono agli archivi di backup sono chiamati *flussi di base*.</span><span class="sxs-lookup"><span data-stu-id="950c1-106">Streams that connect to backing stores are called *base streams*.</span></span> <span data-ttu-id="950c1-107">I flussi di base hanno costruttori con i parametri necessari per connettere il flusso all'archivio di backup.</span><span class="sxs-lookup"><span data-stu-id="950c1-107">Base streams have constructors with the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="950c1-108"><xref:System.IO.FileStream>, ad esempio, ha costruttori che specificano un parametro del percorso, che specifica come il file verrà condiviso dai processi.</span><span class="sxs-lookup"><span data-stu-id="950c1-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes.</span></span>  

<span data-ttu-id="950c1-109">La progettazione delle classi <xref:System.IO> consente una composizione dei flussi semplificata.</span><span class="sxs-lookup"><span data-stu-id="950c1-109">The design of the <xref:System.IO> classes provides simplified stream composition.</span></span> <span data-ttu-id="950c1-110">I flussi di base possono essere associati a uno o più flussi pass-through che forniscono la funzionalità desiderata.</span><span class="sxs-lookup"><span data-stu-id="950c1-110">You can attach base streams to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="950c1-111">Un lettore o un writer può essere collegato alla fine della catena, in modo che i tipi preferiti possano essere letti o scritti facilmente.</span><span class="sxs-lookup"><span data-stu-id="950c1-111">You can attach a reader or writer to the end of the chain, so the preferred types can be read or written easily.</span></span>  

<span data-ttu-id="950c1-112">Gli esempi di codice seguenti creano un **FileStream** per il file esistente *MyFile.txt* in modo da inserire nel buffer *MyFile.txt*.</span><span class="sxs-lookup"><span data-stu-id="950c1-112">The following code examples create a **FileStream** around the existing *MyFile.txt* in order to buffer *MyFile.txt*.</span></span> <span data-ttu-id="950c1-113">Si noti che gli elementi **FileStream** vengono memorizzati nel buffer per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="950c1-113">Note that **FileStreams** are buffered by default.</span></span>

>[!IMPORTANT]
><span data-ttu-id="950c1-114">Gli esempi presuppongono che un file denominato *MyFile.txt* esista già nella stessa cartella dell'app.</span><span class="sxs-lookup"><span data-stu-id="950c1-114">The examples assume that a file named *MyFile.txt* already exists in the same folder as the app.</span></span>  

## <a name="example-use-streamreader"></a><span data-ttu-id="950c1-115">Esempio: usare StreamReader</span><span class="sxs-lookup"><span data-stu-id="950c1-115">Example: Use StreamReader</span></span>
<span data-ttu-id="950c1-116">L'esempio seguente crea un elemento <xref:System.IO.StreamReader> per leggere i caratteri da **FileStream**, che viene passato a **StreamReader** come argomento del costruttore.</span><span class="sxs-lookup"><span data-stu-id="950c1-116">The following example creates a <xref:System.IO.StreamReader> to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="950c1-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> legge finché <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> non trova più caratteri.</span><span class="sxs-lookup"><span data-stu-id="950c1-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> then reads until <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> finds no more characters.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a><span data-ttu-id="950c1-118">Esempio: usare BinaryReader</span><span class="sxs-lookup"><span data-stu-id="950c1-118">Example: Use BinaryReader</span></span>
<span data-ttu-id="950c1-119">L'esempio seguente crea un elemento <xref:System.IO.BinaryReader> per leggere i byte da **FileStream**, che viene passato a **BinaryReader** come argomento del costruttore.</span><span class="sxs-lookup"><span data-stu-id="950c1-119">The following example creates a <xref:System.IO.BinaryReader> to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="950c1-120"><xref:System.IO.BinaryReader.ReadByte%2A> legge finché <xref:System.IO.BinaryReader.PeekChar%2A> non trova più byte.</span><span class="sxs-lookup"><span data-stu-id="950c1-120"><xref:System.IO.BinaryReader.ReadByte%2A> then reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="950c1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="950c1-121">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
