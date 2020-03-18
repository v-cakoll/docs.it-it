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
ms.openlocfilehash: 5aa25e265ed6ffb613e9916414c6f2335a4aaf57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159377"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="8f766-102">Procedura: Comprimere ed estrarre file</span><span class="sxs-lookup"><span data-stu-id="8f766-102">How to: Compress and extract files</span></span>

<span data-ttu-id="8f766-103">Lo spazio dei nomi <xref:System.IO.Compression> contiene i tipi seguenti per la compressione e la decompressione di file e flussi.</span><span class="sxs-lookup"><span data-stu-id="8f766-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="8f766-104">È possibile usare questi tipi anche per leggere e modificare il contenuto di un file compresso.</span><span class="sxs-lookup"><span data-stu-id="8f766-104">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="8f766-105">Gli esempi seguenti mostrano alcune delle operazioni che è possibile eseguire con i file compressi.</span><span class="sxs-lookup"><span data-stu-id="8f766-105">The following examples show some of the operations you can perform with compressed files.</span></span>

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="8f766-106">Esempio 1: Creare ed estrarre un file .zipExample 1: Create and extract a .zip file</span><span class="sxs-lookup"><span data-stu-id="8f766-106">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="8f766-107">Nell'esempio seguente viene illustrato come creare ed estrarre un file *ZIP* compresso usando la classe <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="8f766-107">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="8f766-108">L'esempio comprime il contenuto di una cartella in un nuovo file *ZIP* e quindi estrae il contenuto in una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="8f766-108">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span>

<span data-ttu-id="8f766-109">Per eseguire l'esempio, creare una cartella *start* nella cartella del programma e copiarvi i file da comprimere.</span><span class="sxs-lookup"><span data-stu-id="8f766-109">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span>

<span data-ttu-id="8f766-110">Se viene visualizzato l'errore di compilazione "Il nome 'ZipFile' non esiste nel contesto corrente", aggiungere un riferimento all'assembly `System.IO.Compression.FileSystem` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="8f766-110">If you get the build error "The name 'ZipFile' does not exist in the current context," add a reference to the `System.IO.Compression.FileSystem` assembly to your project.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="8f766-111">Esempio 2: Estrarre estensioni di file specificheExample 2: Extract specific file extensions</span><span class="sxs-lookup"><span data-stu-id="8f766-111">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="8f766-112">Il prossimo esempio mostra come eseguire l'iterazione del contenuto di un file *ZIP* esistente ed estrarre i file con estensione *txt*.</span><span class="sxs-lookup"><span data-stu-id="8f766-112">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="8f766-113">Usa la classe <xref:System.IO.Compression.ZipArchive> per accedere al file ZIP e la classe <xref:System.IO.Compression.ZipArchiveEntry> per controllare le singole voci.</span><span class="sxs-lookup"><span data-stu-id="8f766-113">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="8f766-114">Il metodo di estensione <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> per l'oggetto <xref:System.IO.Compression.ZipArchiveEntry> è disponibile nella classe <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8f766-114">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="8f766-115">Per eseguire l'esempio, inserire un file *ZIP* denominato *result.zip* nella cartella del programma.</span><span class="sxs-lookup"><span data-stu-id="8f766-115">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="8f766-116">Quando richiesto, specificare un nome di cartella in cui estrarre i file.</span><span class="sxs-lookup"><span data-stu-id="8f766-116">When prompted, provide a folder name to extract to.</span></span>

<span data-ttu-id="8f766-117">Se viene visualizzato l'errore di compilazione "Il nome 'ZipFile' non esiste nel contesto corrente", aggiungere un riferimento all'assembly `System.IO.Compression.FileSystem` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="8f766-117">If you get the build error "The name 'ZipFile' does not exist in the current context," add a reference to the `System.IO.Compression.FileSystem` assembly to your project.</span></span>

<span data-ttu-id="8f766-118">Se viene visualizzato l'errore "Il tipo 'ZipArchive' è definito in un assembly di cui manca il riferimento", aggiungere un riferimento all'assembly `System.IO.Compression` al progetto.</span><span class="sxs-lookup"><span data-stu-id="8f766-118">If you get the error "The type 'ZipArchive' is defined in an assembly that is not referenced," add a reference to the `System.IO.Compression` assembly to your project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f766-119">Quando si decomprimono i file, è necessario cercare percorsi dannosi che possono sfuggire alla directory in cui si esegue la decompressione.</span><span class="sxs-lookup"><span data-stu-id="8f766-119">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="8f766-120">Si tratta di un attacco noto come attacco path traversal.</span><span class="sxs-lookup"><span data-stu-id="8f766-120">This is known as a path traversal attack.</span></span> <span data-ttu-id="8f766-121">L'esempio seguente illustra come verificare la presenza di percorsi file dannosi e offre un metodo sicuro per la decompressione.</span><span class="sxs-lookup"><span data-stu-id="8f766-121">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="8f766-122">Esempio 3: Aggiungere un file a un file zip esistenteExample 3: Add a file to an existing zip</span><span class="sxs-lookup"><span data-stu-id="8f766-122">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="8f766-123">L'esempio seguente usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file *ZIP* esistente e aggiunge un nuovo file al file compresso.</span><span class="sxs-lookup"><span data-stu-id="8f766-123">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="8f766-124">Il nuovo file viene compresso quando lo si aggiunge al file ZIP esistente.</span><span class="sxs-lookup"><span data-stu-id="8f766-124">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="8f766-125">Esempio 4: comprimere e decomprimere i file .gz</span><span class="sxs-lookup"><span data-stu-id="8f766-125">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="8f766-126">È possibile usare anche le classi <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> per comprimere e decomprimere dati.</span><span class="sxs-lookup"><span data-stu-id="8f766-126">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="8f766-127">Queste due classi usano lo stesso algoritmo di compressione.</span><span class="sxs-lookup"><span data-stu-id="8f766-127">They use the same compression algorithm.</span></span> <span data-ttu-id="8f766-128">È possibile decomprimere gli oggetti <xref:System.IO.Compression.GZipStream> scritti in un file con estensione *gz* con molti strumenti comuni.</span><span class="sxs-lookup"><span data-stu-id="8f766-128">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="8f766-129">L'esempio seguente illustra come comprimere e decomprimere una directory di file usando la classe <xref:System.IO.Compression.GZipStream>:</span><span class="sxs-lookup"><span data-stu-id="8f766-129">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="8f766-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f766-130">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="8f766-131">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="8f766-131">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
