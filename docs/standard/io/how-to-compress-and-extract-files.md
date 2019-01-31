---
title: 'Procedura: Comprimere ed estrarre file'
ms.date: 06/06/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c35bf549dc4dcd5e12e3580c2357b64dcc42905b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650941"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="1e4d0-102">Procedura: Comprimere ed estrarre file</span><span class="sxs-lookup"><span data-stu-id="1e4d0-102">How to: Compress and extract files</span></span>

<span data-ttu-id="1e4d0-103">Lo spazio dei nomi <xref:System.IO.Compression> contiene i tipi seguenti per la compressione e la decompressione di file e flussi.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="1e4d0-104">È possibile usare questi tipi anche per leggere e modificare il contenuto di un file compresso:</span><span class="sxs-lookup"><span data-stu-id="1e4d0-104">You can also use these types to read and modify the contents of a compressed file:</span></span>

- <xref:System.IO.Compression.ZipFile>

- <xref:System.IO.Compression.ZipArchive>

- <xref:System.IO.Compression.ZipArchiveEntry>

- <xref:System.IO.Compression.DeflateStream>

- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="1e4d0-105">Gli esempi seguenti mostrano alcune delle funzioni che è possibile eseguire quando si usano file compressi.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>

## <a name="example-1---create-and-extract-a-zip-file"></a><span data-ttu-id="1e4d0-106">Esempio 1: creare ed estrarre un file con estensione zip</span><span class="sxs-lookup"><span data-stu-id="1e4d0-106">Example 1 - Create and extract a .zip file</span></span>

<span data-ttu-id="1e4d0-107">L'esempio seguente illustra come creare ed estrarre un file compresso con estensione zip usando la classe <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-107">The following example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="1e4d0-108">L'esempio comprime il contenuto di una cartella in un nuovo file ZIP e quindi estrae il contenuto in una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="1e4d0-109">Per usare la classe <xref:System.IO.Compression.ZipFile>, è necessario referenziare l'assembly `System.IO.Compression.FileSystem` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2---extract-specific-file-extensions"></a><span data-ttu-id="1e4d0-110">Esempio 2: estrarre estensioni file specifiche</span><span class="sxs-lookup"><span data-stu-id="1e4d0-110">Example 2 - Extract specific file extensions</span></span>

<span data-ttu-id="1e4d0-111">L'esempio seguente mostra come eseguire l'iterazione del contenuto di un file ZIP esistente ed estrarre file con estensione txt.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="1e4d0-112">L'esempio usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file ZIP esistente e la classe <xref:System.IO.Compression.ZipArchiveEntry> per controllare le singole voci nel file compresso.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="1e4d0-113">Usa un metodo di estensione (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) per l'oggetto <xref:System.IO.Compression.ZipArchiveEntry>.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="1e4d0-114">Il metodo di estensione è disponibile nella classe <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="1e4d0-115">Per usare la classe <xref:System.IO.Compression.ZipFileExtensions>, è necessario referenziare l'assembly `System.IO.Compression.FileSystem` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e4d0-116">Quando si decomprimono i file, è necessario cercare percorsi dannosi che possono sfuggire alla directory in cui si vuole eseguire la decompressione.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-116">When unzipping files, you must look for malicious file paths which can escape out of the directory where you want to unzip into.</span></span> <span data-ttu-id="1e4d0-117">Si tratta di un attacco noto come attacco path traversal.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-117">This is known as a path traversal attack.</span></span>

<span data-ttu-id="1e4d0-118">L'esempio seguente illustra come verificare la presenza di percorsi file dannosi e offre un metodo sicuro per la decompressione:</span><span class="sxs-lookup"><span data-stu-id="1e4d0-118">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip:</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3---add-a-new-file-to-an-existing-zip-file"></a><span data-ttu-id="1e4d0-119">Esempio 3: aggiungere un nuovo file in un file con estensione zip esistente</span><span class="sxs-lookup"><span data-stu-id="1e4d0-119">Example 3 - Add a new file to an existing .zip file</span></span>

<span data-ttu-id="1e4d0-120">L'esempio seguente usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file con estensione zip esistente e aggiunge un nuovo file al file compresso.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-120">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="1e4d0-121">Il nuovo file viene compresso quando lo si aggiunge al file ZIP esistente.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-121">The new file gets compressed when you add it to the existing .zip file.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4---compress-and-decompress-a-directory-of-gz-files"></a><span data-ttu-id="1e4d0-122">Esempio 4: comprimere e decomprimere una directory di file con estensione gz</span><span class="sxs-lookup"><span data-stu-id="1e4d0-122">Example 4 - Compress and decompress a directory of .gz files</span></span>

<span data-ttu-id="1e4d0-123">È possibile usare anche le classi <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> per comprimere e decomprimere dati.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-123">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="1e4d0-124">Queste due classi usano lo stesso algoritmo di compressione.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-124">They use the same compression algorithm.</span></span> <span data-ttu-id="1e4d0-125">Gli oggetti <xref:System.IO.Compression.GZipStream> compressi scritti in un file con estensione gz possono essere decompressi usando molti strumenti comuni oltre ai metodi forniti da <xref:System.IO.Compression.GZipStream>.</span><span class="sxs-lookup"><span data-stu-id="1e4d0-125">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="1e4d0-126">L'esempio seguente illustra come comprimere e decomprimere una directory di file usando la classe <xref:System.IO.Compression.GZipStream>:</span><span class="sxs-lookup"><span data-stu-id="1e4d0-126">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="1e4d0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e4d0-127">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>
- [<span data-ttu-id="1e4d0-128">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="1e4d0-128">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
