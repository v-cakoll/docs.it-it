---
title: 'Procedura: Comprimere ed estrarre file'
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
ms.openlocfilehash: 28f9a0baa73f58b0a5c7f93a4b0b3ece3b87c3a5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288563"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="49aaf-102">Procedura: Comprimere ed estrarre file</span><span class="sxs-lookup"><span data-stu-id="49aaf-102">How to: Compress and extract files</span></span>

<span data-ttu-id="49aaf-103">Lo spazio dei nomi <xref:System.IO.Compression> contiene i tipi seguenti per la compressione e la decompressione di file e flussi.</span><span class="sxs-lookup"><span data-stu-id="49aaf-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="49aaf-104">È possibile usare questi tipi anche per leggere e modificare il contenuto di un file compresso.</span><span class="sxs-lookup"><span data-stu-id="49aaf-104">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="49aaf-105">Gli esempi seguenti mostrano alcune delle operazioni che è possibile eseguire con i file compressi.</span><span class="sxs-lookup"><span data-stu-id="49aaf-105">The following examples show some of the operations you can perform with compressed files.</span></span> <span data-ttu-id="49aaf-106">Per questi esempi è necessario aggiungere al progetto i pacchetti NuGet seguenti:</span><span class="sxs-lookup"><span data-stu-id="49aaf-106">These examples require the following NuGet packages to be added to your project:</span></span>

- [<span data-ttu-id="49aaf-107">System.IO.Compression</span><span class="sxs-lookup"><span data-stu-id="49aaf-107">System.IO.Compression</span></span>](https://www.nuget.org/packages/System.IO.Compression)
- [<span data-ttu-id="49aaf-108">System.IO.Compression.ZipFile</span><span class="sxs-lookup"><span data-stu-id="49aaf-108">System.IO.Compression.ZipFile</span></span>](https://www.nuget.org/packages/System.IO.Compression.ZipFile)

<span data-ttu-id="49aaf-109">Se si usa .NET Framework, aggiungere i riferimenti alle due librerie seguenti al progetto:</span><span class="sxs-lookup"><span data-stu-id="49aaf-109">If you're using .NET Framework, add references to these two libraries to your project:</span></span>

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="49aaf-110">Esempio 1: creare ed estrarre un file zip</span><span class="sxs-lookup"><span data-stu-id="49aaf-110">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="49aaf-111">Nell'esempio seguente viene illustrato come creare ed estrarre un file *ZIP* compresso usando la classe <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="49aaf-111">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="49aaf-112">L'esempio comprime il contenuto di una cartella in un nuovo file *ZIP* e quindi estrae il contenuto in una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="49aaf-112">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span>

<span data-ttu-id="49aaf-113">Per eseguire l'esempio, creare una cartella *start* nella cartella del programma e copiarvi i file da comprimere.</span><span class="sxs-lookup"><span data-stu-id="49aaf-113">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="49aaf-114">Esempio 2: estrarre estensioni di file specifiche</span><span class="sxs-lookup"><span data-stu-id="49aaf-114">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="49aaf-115">Il prossimo esempio mostra come eseguire l'iterazione del contenuto di un file *ZIP* esistente ed estrarre i file con estensione *txt*.</span><span class="sxs-lookup"><span data-stu-id="49aaf-115">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="49aaf-116">Usa la classe <xref:System.IO.Compression.ZipArchive> per accedere al file ZIP e la classe <xref:System.IO.Compression.ZipArchiveEntry> per controllare le singole voci.</span><span class="sxs-lookup"><span data-stu-id="49aaf-116">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="49aaf-117">Il metodo di estensione <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> per l'oggetto <xref:System.IO.Compression.ZipArchiveEntry> è disponibile nella classe <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="49aaf-117">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="49aaf-118">Per eseguire l'esempio, inserire un file *ZIP* denominato *result.zip* nella cartella del programma.</span><span class="sxs-lookup"><span data-stu-id="49aaf-118">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="49aaf-119">Quando richiesto, specificare un nome di cartella in cui estrarre i file.</span><span class="sxs-lookup"><span data-stu-id="49aaf-119">When prompted, provide a folder name to extract to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49aaf-120">Quando si decomprimono i file, è necessario cercare percorsi dannosi che possono sfuggire alla directory in cui si esegue la decompressione.</span><span class="sxs-lookup"><span data-stu-id="49aaf-120">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="49aaf-121">Si tratta di un attacco noto come attacco path traversal.</span><span class="sxs-lookup"><span data-stu-id="49aaf-121">This is known as a path traversal attack.</span></span> <span data-ttu-id="49aaf-122">L'esempio seguente illustra come verificare la presenza di percorsi file dannosi e offre un metodo sicuro per la decompressione.</span><span class="sxs-lookup"><span data-stu-id="49aaf-122">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="49aaf-123">Esempio 3: aggiungere un file a un file Zip esistente</span><span class="sxs-lookup"><span data-stu-id="49aaf-123">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="49aaf-124">L'esempio seguente usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file *ZIP* esistente e aggiunge un nuovo file al file compresso.</span><span class="sxs-lookup"><span data-stu-id="49aaf-124">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="49aaf-125">Il nuovo file viene compresso quando lo si aggiunge al file ZIP esistente.</span><span class="sxs-lookup"><span data-stu-id="49aaf-125">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="49aaf-126">Esempio 4: comprimere e decomprimere i file. gz</span><span class="sxs-lookup"><span data-stu-id="49aaf-126">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="49aaf-127">È possibile usare anche le classi <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> per comprimere e decomprimere dati.</span><span class="sxs-lookup"><span data-stu-id="49aaf-127">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="49aaf-128">Queste due classi usano lo stesso algoritmo di compressione.</span><span class="sxs-lookup"><span data-stu-id="49aaf-128">They use the same compression algorithm.</span></span> <span data-ttu-id="49aaf-129">È possibile decomprimere gli oggetti <xref:System.IO.Compression.GZipStream> scritti in un file con estensione *gz* con molti strumenti comuni.</span><span class="sxs-lookup"><span data-stu-id="49aaf-129">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="49aaf-130">L'esempio seguente illustra come comprimere e decomprimere una directory di file usando la classe <xref:System.IO.Compression.GZipStream>:</span><span class="sxs-lookup"><span data-stu-id="49aaf-130">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="49aaf-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49aaf-131">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="49aaf-132">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="49aaf-132">File and stream I/O</span></span>](index.md)
