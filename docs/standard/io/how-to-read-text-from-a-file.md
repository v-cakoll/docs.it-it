---
title: 'Procedura: Leggere testo da un file'
ms.date: 06/19/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f667b0a757a676788b693691504512dfc227a7e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646672"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="f6bde-102">Procedura: Leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="f6bde-102">How to: Read Text from a File</span></span>
<span data-ttu-id="f6bde-103">Negli esempi seguenti viene illustrato come leggere il testo in modo sincrono e in modo asincrono da un file di testo usando .NET per le applicazioni desktop.</span><span class="sxs-lookup"><span data-stu-id="f6bde-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="f6bde-104">In entrambi gli esempi, quando si crea l'istanza della classe <xref:System.IO.StreamReader>, si immette il percorso relativo o assoluto del file.</span><span class="sxs-lookup"><span data-stu-id="f6bde-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> <span data-ttu-id="f6bde-105">Negli esempi si presuppone che il file denominato TestFile.txt sia nella stessa cartella dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6bde-105">The following examples assume that the file named TestFile.txt is in the same folder as the application.</span></span>  
  
 <span data-ttu-id="f6bde-106">Questi esempi di codice non sono applicabili allo sviluppo di applicazioni Windows Store poiché Windows Runtime offre tipi di flusso diversi per la lettura e la scrittura nei file.</span><span class="sxs-lookup"><span data-stu-id="f6bde-106">These code examples do not apply to developing for Windows Store Apps because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="f6bde-107">Per un esempio che illustri come leggere testo da un file in un'app di Windows Store, vedere [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)) (Avvio rapido Lettura e scrittura di file).</span><span class="sxs-lookup"><span data-stu-id="f6bde-107">For an example that shows how to read text from a file in a Windows Store app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="f6bde-108">Per esempi che illustrano come eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime, vedere [Procedura: Eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="f6bde-108">For examples that show how to convert between .NET Framework streams and Windows runtime streams, see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6bde-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f6bde-109">Example</span></span>  
 <span data-ttu-id="f6bde-110">L'esempio seguente illustra un'operazione di lettura sincrona in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f6bde-110">The following example shows a synchronous read operation within a console application.</span></span> <span data-ttu-id="f6bde-111">In questo esempio il file di testo viene aperto tramite un lettore del flusso e il contenuto viene copiato in una stringa, che viene trasmessa come output alla console.</span><span class="sxs-lookup"><span data-stu-id="f6bde-111">In this example, the text file is opened using a stream reader, the contents are copied to a string, and the string is output to the console.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="f6bde-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f6bde-112">Example</span></span>  
 <span data-ttu-id="f6bde-113">L'esempio seguente illustra l'operazione di lettura asincrona in un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="f6bde-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="f6bde-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6bde-114">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f6bde-115">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="f6bde-115">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
- [<span data-ttu-id="f6bde-116">NIB: Procedura: Creare una visualizzazione directory</span><span class="sxs-lookup"><span data-stu-id="f6bde-116">NIB: How to: Create a Directory Listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)
- [<span data-ttu-id="f6bde-117">Avvio rapido: Lettura e scrittura di file</span><span class="sxs-lookup"><span data-stu-id="f6bde-117">Quickstart: Reading and writing files</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)
- [<span data-ttu-id="f6bde-118">Procedura: Eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="f6bde-118">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
- [<span data-ttu-id="f6bde-119">Procedura: Leggere e scrivere su un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="f6bde-119">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [<span data-ttu-id="f6bde-120">Procedura: Aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="f6bde-120">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [<span data-ttu-id="f6bde-121">Procedura: Scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="f6bde-121">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [<span data-ttu-id="f6bde-122">Procedura: Leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="f6bde-122">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
- [<span data-ttu-id="f6bde-123">Procedura: Scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="f6bde-123">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)
- [<span data-ttu-id="f6bde-124">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="f6bde-124">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
