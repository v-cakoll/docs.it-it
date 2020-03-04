---
title: 'Procedura: scrivere testo in un file'
ms.date: 01/04/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
ms.openlocfilehash: ba1c1815f0e49c02d1f0ee3c48ba01b7c2f5e727
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160248"
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="7f2d8-102">Procedura: scrivere testo in un file</span><span class="sxs-lookup"><span data-stu-id="7f2d8-102">How to: Write text to a file</span></span>
<span data-ttu-id="7f2d8-103">Questo argomento illustra diversi modi per scrivere testo in un file per un'app .NET.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-103">This topic shows different ways to write text to a file for a .NET app.</span></span>

<span data-ttu-id="7f2d8-104">Per scrivere un testo in un file vengono in genere usati le classi e i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f2d8-104">The following classes and methods are typically used to write text to a file:</span></span>  
  
- <span data-ttu-id="7f2d8-105"><xref:System.IO.StreamWriter> contiene metodi per scrivere in un file in modo sincrono (<xref:System.IO.StreamWriter.Write%2A> e <xref:System.IO.TextWriter.WriteLine%2A>) o asincrono (<xref:System.IO.StreamWriter.WriteAsync%2A> e <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span><span class="sxs-lookup"><span data-stu-id="7f2d8-105"><xref:System.IO.StreamWriter> contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> and <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
- <span data-ttu-id="7f2d8-106"><xref:System.IO.File> specifica metodi statici per scrivere un testo in un file, ad esempio <xref:System.IO.File.WriteAllLines%2A> e <xref:System.IO.File.WriteAllText%2A> o per accodare testo a un file, ad esempio <xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> e <xref:System.IO.File.AppendText%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-106"><xref:System.IO.File> provides static methods to write text to a file, such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file, such as <xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A>, and <xref:System.IO.File.AppendText%2A>.</span></span>  
  
- <span data-ttu-id="7f2d8-107"><xref:System.IO.Path> è destinato alle stringhe che contengono informazioni sul percorso di file o directory.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-107"><xref:System.IO.Path> is for strings that have file or directory path information.</span></span> <span data-ttu-id="7f2d8-108">Contiene il metodo <xref:System.IO.Path.Combine%2A> e in .NET Core 2.1 e versioni successive i metodi <xref:System.IO.Path.Join%2A> e <xref:System.IO.Path.TryJoin%2A>, che consentono la concatenazione di stringhe per compilare un percorso di file o directory.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-108">It contains the <xref:System.IO.Path.Combine%2A> method and, in .NET Core 2.1 and later, the <xref:System.IO.Path.Join%2A> and <xref:System.IO.Path.TryJoin%2A> methods, which allow concatenation of strings to build a file or directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="7f2d8-109">Gli esempi seguenti visualizzano solo la quantità minima di codice necessario.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-109">The following examples show only the minimum amount of code needed.</span></span> <span data-ttu-id="7f2d8-110">Un'applicazione reale include in genere procedure di controllo degli errori e di gestione delle eccezioni più efficaci.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-110">A real-world app usually provides more robust error checking and exception handling.</span></span>  
  
## <a name="example-synchronously-write-text-with-streamwriter"></a><span data-ttu-id="7f2d8-111">Esempio: scrivere testo in modo sincrono con StreamWriter</span><span class="sxs-lookup"><span data-stu-id="7f2d8-111">Example: Synchronously write text with StreamWriter</span></span>

<span data-ttu-id="7f2d8-112">L'esempio seguente illustra come usare la classe <xref:System.IO.StreamWriter> per scrivere un testo in modo sincrono una riga alla volta in un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-112">The following example shows how to use the <xref:System.IO.StreamWriter> class to synchronously write text to a new file one line at a time.</span></span> <span data-ttu-id="7f2d8-113">Poiché l'oggetto <xref:System.IO.StreamWriter> viene dichiarato in un'istruzione `using` in cui viene creata anche un'istanza dell'oggetto stesso, viene chiamato il metodo <xref:System.IO.StreamWriter.Dispose%2A> che scarica e chiude automaticamente il flusso.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-113">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked, which automatically flushes and closes the stream.</span></span>  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/write.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/write.vb)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="example-synchronously-append-text-with-streamwriter"></a><span data-ttu-id="7f2d8-114">Esempio: accodare in modo sincrono il testo con StreamWriter</span><span class="sxs-lookup"><span data-stu-id="7f2d8-114">Example: Synchronously append text with StreamWriter</span></span>

<span data-ttu-id="7f2d8-115">L'esempio seguente illustra come usare la classe <xref:System.IO.StreamWriter> per accodare testo in modo sincrono al file di testo creato nel primo esempio.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-115">The following example shows how to use the <xref:System.IO.StreamWriter> class to synchronously append text to the text file created in the first example.</span></span>

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/append.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/append.vb)]  

## <a name="example-asynchronously-write-text-with-streamwriter"></a><span data-ttu-id="7f2d8-116">Esempio: scrivere in modo asincrono un testo con StreamWriter</span><span class="sxs-lookup"><span data-stu-id="7f2d8-116">Example: Asynchronously write text with StreamWriter</span></span>

<span data-ttu-id="7f2d8-117">L'esempio seguente illustra come scrivere in modo asincrono un testo in un nuovo file usando la classe <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="7f2d8-117">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="7f2d8-118">Per chiamare il metodo <xref:System.IO.StreamWriter.WriteAsync%2A>, la chiamata al metodo deve essere inclusa in un metodo `async`.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-118">To invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call must be within an `async` method.</span></span> <span data-ttu-id="7f2d8-119">L'esempio C# richiede C# 7.1 o versioni successive, che aggiunge il supporto per il modificatore `async` nel punto di ingresso del programma.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-119">The C# example requires C# 7.1 or later, which adds support for the `async` modifier on the program entry point.</span></span>

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/async.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/async.vb)]  

## <a name="example-write-and-append-text-with-the-file-class"></a><span data-ttu-id="7f2d8-120">Esempio: scrivere e aggiungere testo con la classe file</span><span class="sxs-lookup"><span data-stu-id="7f2d8-120">Example: Write and append text with the File class</span></span>

<span data-ttu-id="7f2d8-121">L'esempio seguente illustra come scrivere un testo in un nuovo file e aggiungere nuove righe di testo nello stesso file usando la classe <xref:System.IO.File> .</span><span class="sxs-lookup"><span data-stu-id="7f2d8-121">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="7f2d8-122">I metodi <xref:System.IO.File.WriteAllText%2A> e <xref:System.IO.File.AppendAllLines%2A> aprono e chiudono automaticamente il file.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-122">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="7f2d8-123">Se il percorso specificato per il metodo <xref:System.IO.File.WriteAllText%2A> esiste già, il file viene sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="7f2d8-123">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file is overwritten.</span></span>  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/file.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/file.vb)]  

## <a name="see-also"></a><span data-ttu-id="7f2d8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f2d8-124">See also</span></span>

- <xref:System.IO.StreamWriter>
- <xref:System.IO.Path>
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7f2d8-125">Procedura: enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="7f2d8-125">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [<span data-ttu-id="7f2d8-126">Procedura: leggere e scrivere in un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="7f2d8-126">How to: Read and write to a newly-created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [<span data-ttu-id="7f2d8-127">Procedura: aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="7f2d8-127">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [<span data-ttu-id="7f2d8-128">Procedura: leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="7f2d8-128">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [<span data-ttu-id="7f2d8-129">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="7f2d8-129">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
