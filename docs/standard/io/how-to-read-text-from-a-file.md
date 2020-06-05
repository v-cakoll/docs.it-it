---
title: 'Procedura: leggere testo da un file'
description: In questo articolo, vedere esempi di come leggere il testo in modo sincrono o asincrono da un file di testo, usando la classe StreamReader in .NET per le applicazioni desktop.
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
ms.openlocfilehash: cbdeab3e907b34b6658eef7228fa6567ae198b08
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447056"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="a38c6-103">Procedura: leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="a38c6-103">How to: Read text from a file</span></span>
<span data-ttu-id="a38c6-104">Negli esempi seguenti viene illustrato come leggere il testo in modo sincrono e in modo asincrono da un file di testo usando .NET per le applicazioni desktop.</span><span class="sxs-lookup"><span data-stu-id="a38c6-104">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="a38c6-105">In entrambi gli esempi, quando si crea l'istanza della classe <xref:System.IO.StreamReader>, si immette il percorso relativo o assoluto del file.</span><span class="sxs-lookup"><span data-stu-id="a38c6-105">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a38c6-106">Questi esempi di codice non sono applicabili allo sviluppo di applicazioni UWP (Universal Windows Platform), perché Windows Runtime offre tipi di flusso diversi per la lettura e la scrittura nei file.</span><span class="sxs-lookup"><span data-stu-id="a38c6-106">These code examples do not apply to developing for Universal Windows (UWP) apps, because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="a38c6-107">Per un esempio che illustra come leggere il testo da un file in un'app UWP, vedere [Guida introduttiva: lettura e scrittura di file](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="a38c6-107">For an example that shows how to read text from a file in a UWP app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="a38c6-108">Per esempi che illustrano come eseguire la conversione tra flussi .NET Framework e flussi Windows Runtime, vedere [procedura: eseguire la conversione tra flussi di .NET Framework e flussi Windows Runtime](how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="a38c6-108">For examples that show how to convert between .NET Framework streams and Windows Runtime streams, see [How to: Convert between .NET Framework streams and Windows Runtime streams](how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example-synchronous-read-in-a-console-app"></a><span data-ttu-id="a38c6-109">Esempio: lettura sincrona in un'app console</span><span class="sxs-lookup"><span data-stu-id="a38c6-109">Example: Synchronous read in a console app</span></span>  
<span data-ttu-id="a38c6-110">L'esempio seguente mostra un'operazione di lettura sincrona in un'app console.</span><span class="sxs-lookup"><span data-stu-id="a38c6-110">The following example shows a synchronous read operation within a console app.</span></span> <span data-ttu-id="a38c6-111">In questo esempio viene aperto il file di testo usando un lettore di flusso, il contenuto viene copiato in una stringa e la stringa viene quindi restituita nella console.</span><span class="sxs-lookup"><span data-stu-id="a38c6-111">This example opens the text file using a stream reader, copies the contents to a string, and outputs the string to the console.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a38c6-112">L'esempio presuppone che un file denominato *TestFile.txt* esista già nella stessa cartella dell'app.</span><span class="sxs-lookup"><span data-stu-id="a38c6-112">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a><span data-ttu-id="a38c6-113">Esempio: lettura asincrona in un'app WPF</span><span class="sxs-lookup"><span data-stu-id="a38c6-113">Example: Asynchronous read in a WPF app</span></span>
 <span data-ttu-id="a38c6-114">L'esempio seguente illustra un'operazione di lettura asincrona in un'app Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="a38c6-114">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) app.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a38c6-115">L'esempio presuppone che un file denominato *TestFile.txt* esista già nella stessa cartella dell'app.</span><span class="sxs-lookup"><span data-stu-id="a38c6-115">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a38c6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a38c6-116">See also</span></span>

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="a38c6-117">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="a38c6-117">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)  
- <span data-ttu-id="a38c6-118">[Procedura: creare un elenco di directory](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a38c6-118">[How to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="a38c6-119">Quickstart: Reading and writing files (Guida introduttiva: Lettura e scrittura di file)</span><span class="sxs-lookup"><span data-stu-id="a38c6-119">Quickstart: Reading and writing files</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [<span data-ttu-id="a38c6-120">Procedura: eseguire la conversione tra flussi .NET Framework e flussi Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="a38c6-120">How to: Convert between .NET Framework streams and Windows Runtime streams</span></span>](how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [<span data-ttu-id="a38c6-121">Procedura: leggere e scrivere in un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="a38c6-121">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="a38c6-122">Procedura: aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="a38c6-122">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="a38c6-123">Procedura: scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="a38c6-123">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="a38c6-124">Procedura: leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="a38c6-124">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="a38c6-125">Procedura: scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="a38c6-125">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="a38c6-126">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="a38c6-126">File and stream I/O</span></span>](index.md)
