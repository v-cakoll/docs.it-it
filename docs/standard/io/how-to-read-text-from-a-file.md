---
title: 'Procedura: Leggere testo da un file'
ms.date: 01/03/2019
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
ms.openlocfilehash: aa6787e018b540dbf19b6da3473b699096cc4ae3
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674399"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="ce372-102">Procedura: Leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="ce372-102">How to: Read text from a file</span></span>
<span data-ttu-id="ce372-103">Negli esempi seguenti viene illustrato come leggere il testo in modo sincrono e in modo asincrono da un file di testo usando .NET per le applicazioni desktop.</span><span class="sxs-lookup"><span data-stu-id="ce372-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="ce372-104">In entrambi gli esempi, quando si crea l'istanza della classe <xref:System.IO.StreamReader>, si immette il percorso relativo o assoluto del file.</span><span class="sxs-lookup"><span data-stu-id="ce372-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ce372-105">Questi esempi di codice non sono applicabili allo sviluppo di applicazioni UWP (Universal Windows Platform), perché Windows Runtime offre tipi di flusso diversi per la lettura e la scrittura nei file.</span><span class="sxs-lookup"><span data-stu-id="ce372-105">These code examples do not apply to developing for Universal Windows (UWP) apps, because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="ce372-106">Per un esempio che mostra come leggere testo da un file in un'app UWP, vedere [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)) (Avvio rapido Lettura e scrittura di file).</span><span class="sxs-lookup"><span data-stu-id="ce372-106">For an example that shows how to read text from a file in a UWP app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="ce372-107">Per esempi che illustrano come eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime, vedere [Procedura: Eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="ce372-107">For examples that show how to convert between .NET Framework streams and Windows Runtime streams, see [How to: Convert between .NET Framework streams and Windows Runtime streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example-synchronous-read-in-a-console-app"></a><span data-ttu-id="ce372-108">Esempio: Lettura sincrona in un'app console</span><span class="sxs-lookup"><span data-stu-id="ce372-108">Example: Synchronous read in a console app</span></span>  
<span data-ttu-id="ce372-109">L'esempio seguente mostra un'operazione di lettura sincrona in un'app console.</span><span class="sxs-lookup"><span data-stu-id="ce372-109">The following example shows a synchronous read operation within a console app.</span></span> <span data-ttu-id="ce372-110">In questo esempio viene aperto il file di testo usando un lettore di flusso, il contenuto viene copiato in una stringa e la stringa viene quindi restituita nella console.</span><span class="sxs-lookup"><span data-stu-id="ce372-110">This example opens the text file using a stream reader, copies the contents to a string, and outputs the string to the console.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ce372-111">L'esempio presuppone che un file denominato *TestFile.txt* esista già nella stessa cartella dell'app.</span><span class="sxs-lookup"><span data-stu-id="ce372-111">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a><span data-ttu-id="ce372-112">Esempio: Lettura asincrona in un'app WPF</span><span class="sxs-lookup"><span data-stu-id="ce372-112">Example: Asynchronous read in a WPF app</span></span> 
 <span data-ttu-id="ce372-113">L'esempio seguente illustra un'operazione di lettura asincrona in un'app Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ce372-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) app.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ce372-114">L'esempio presuppone che un file denominato *TestFile.txt* esista già nella stessa cartella dell'app.</span><span class="sxs-lookup"><span data-stu-id="ce372-114">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ce372-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce372-115">See also</span></span>

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="ce372-116">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="ce372-116">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [<span data-ttu-id="ce372-117">Procedura: Creare una visualizzazione directory</span><span class="sxs-lookup"><span data-stu-id="ce372-117">How to: Create a directory listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
- [<span data-ttu-id="ce372-118">Avvio rapido: Lettura e scrittura di file</span><span class="sxs-lookup"><span data-stu-id="ce372-118">Quickstart: Reading and writing files</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [<span data-ttu-id="ce372-119">Procedura: Eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="ce372-119">How to: Convert between .NET Framework streams and Windows Runtime streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [<span data-ttu-id="ce372-120">Procedura: Leggere e scrivere in un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="ce372-120">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="ce372-121">Procedura: Aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="ce372-121">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="ce372-122">Procedura: Scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="ce372-122">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="ce372-123">Procedura: Leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="ce372-123">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="ce372-124">Procedura: Scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="ce372-124">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="ce372-125">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="ce372-125">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
