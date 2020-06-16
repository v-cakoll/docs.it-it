---
title: 'Procedura: Comprimere ed estrarre file'
description: Comprime & estrarre i file usando System. IO. Compression. Vedere gli esempi di utilizzo di ZipFile, ZipArchive, ZipArchiveEntry, DeflateStream, & GZipStream.
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
ms.openlocfilehash: c13f464432aa6f67136d3a844bdeda256e7ab9b6
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769236"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="c4fcc-104">Procedura: Comprimere ed estrarre file</span><span class="sxs-lookup"><span data-stu-id="c4fcc-104">How to: Compress and extract files</span></span>

<span data-ttu-id="c4fcc-105">Lo spazio dei nomi <xref:System.IO.Compression> contiene i tipi seguenti per la compressione e la decompressione di file e flussi.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-105">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="c4fcc-106">È possibile usare questi tipi anche per leggere e modificare il contenuto di un file compresso.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-106">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="c4fcc-107">Gli esempi seguenti mostrano alcune delle operazioni che è possibile eseguire con i file compressi.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-107">The following examples show some of the operations you can perform with compressed files.</span></span> <span data-ttu-id="c4fcc-108">Per questi esempi è necessario aggiungere al progetto i pacchetti NuGet seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4fcc-108">These examples require the following NuGet packages to be added to your project:</span></span>

- [<span data-ttu-id="c4fcc-109">System.IO.Compression</span><span class="sxs-lookup"><span data-stu-id="c4fcc-109">System.IO.Compression</span></span>](https://www.nuget.org/packages/System.IO.Compression)
- [<span data-ttu-id="c4fcc-110">System.IO.Compression.ZipFile</span><span class="sxs-lookup"><span data-stu-id="c4fcc-110">System.IO.Compression.ZipFile</span></span>](https://www.nuget.org/packages/System.IO.Compression.ZipFile)

<span data-ttu-id="c4fcc-111">Se si usa .NET Framework, aggiungere i riferimenti alle due librerie seguenti al progetto:</span><span class="sxs-lookup"><span data-stu-id="c4fcc-111">If you're using .NET Framework, add references to these two libraries to your project:</span></span>

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="c4fcc-112">Esempio 1: creare ed estrarre un file zip</span><span class="sxs-lookup"><span data-stu-id="c4fcc-112">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="c4fcc-113">Nell'esempio seguente viene illustrato come creare ed estrarre un file *ZIP* compresso usando la classe <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-113">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="c4fcc-114">L'esempio comprime il contenuto di una cartella in un nuovo file *ZIP* e quindi estrae il contenuto in una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-114">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span>

<span data-ttu-id="c4fcc-115">Per eseguire l'esempio, creare una cartella *start* nella cartella del programma e copiarvi i file da comprimere.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-115">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="c4fcc-116">Esempio 2: estrarre estensioni di file specifiche</span><span class="sxs-lookup"><span data-stu-id="c4fcc-116">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="c4fcc-117">Il prossimo esempio mostra come eseguire l'iterazione del contenuto di un file *ZIP* esistente ed estrarre i file con estensione *txt*.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-117">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="c4fcc-118">Usa la classe <xref:System.IO.Compression.ZipArchive> per accedere al file ZIP e la classe <xref:System.IO.Compression.ZipArchiveEntry> per controllare le singole voci.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-118">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="c4fcc-119">Il metodo di estensione <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> per l'oggetto <xref:System.IO.Compression.ZipArchiveEntry> è disponibile nella classe <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-119">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="c4fcc-120">Per eseguire l'esempio, inserire un file *ZIP* denominato *result.zip* nella cartella del programma.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-120">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="c4fcc-121">Quando richiesto, specificare un nome di cartella in cui estrarre i file.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-121">When prompted, provide a folder name to extract to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4fcc-122">Quando si decomprimono i file, è necessario cercare percorsi dannosi che possono sfuggire alla directory in cui si esegue la decompressione.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-122">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="c4fcc-123">Si tratta di un attacco noto come attacco path traversal.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-123">This is known as a path traversal attack.</span></span> <span data-ttu-id="c4fcc-124">L'esempio seguente illustra come verificare la presenza di percorsi file dannosi e offre un metodo sicuro per la decompressione.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-124">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="c4fcc-125">Esempio 3: aggiungere un file a un file Zip esistente</span><span class="sxs-lookup"><span data-stu-id="c4fcc-125">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="c4fcc-126">L'esempio seguente usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file *ZIP* esistente e aggiunge un nuovo file al file compresso.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-126">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="c4fcc-127">Il nuovo file viene compresso quando lo si aggiunge al file ZIP esistente.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-127">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="c4fcc-128">Esempio 4: comprimere e decomprimere i file. gz</span><span class="sxs-lookup"><span data-stu-id="c4fcc-128">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="c4fcc-129">È possibile usare anche le classi <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> per comprimere e decomprimere dati.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-129">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="c4fcc-130">Queste due classi usano lo stesso algoritmo di compressione.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-130">They use the same compression algorithm.</span></span> <span data-ttu-id="c4fcc-131">È possibile decomprimere gli oggetti <xref:System.IO.Compression.GZipStream> scritti in un file con estensione *gz* con molti strumenti comuni.</span><span class="sxs-lookup"><span data-stu-id="c4fcc-131">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="c4fcc-132">L'esempio seguente illustra come comprimere e decomprimere una directory di file usando la classe <xref:System.IO.Compression.GZipStream>:</span><span class="sxs-lookup"><span data-stu-id="c4fcc-132">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="c4fcc-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4fcc-133">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="c4fcc-134">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="c4fcc-134">File and stream I/O</span></span>](index.md)
