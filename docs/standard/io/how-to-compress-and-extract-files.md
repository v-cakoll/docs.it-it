---
title: 'Procedura: comprimere ed estrarre file'
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
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 33c9249692998aea8c22ddbf75a5a9b7bdf28708
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="a4914-102">Procedura: comprimere ed estrarre file</span><span class="sxs-lookup"><span data-stu-id="a4914-102">How to: Compress and Extract Files</span></span>
<span data-ttu-id="a4914-103">Lo spazio dei nomi <xref:System.IO.Compression> contiene i tipi seguenti per la compressione e la decompressione di file e flussi.</span><span class="sxs-lookup"><span data-stu-id="a4914-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="a4914-104">È possibile usare questi tipi anche per leggere e modificare il contenuto di un file compresso:</span><span class="sxs-lookup"><span data-stu-id="a4914-104">You can also use these types to read and modify the contents of a compressed file:</span></span>  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 <span data-ttu-id="a4914-105">Gli esempi seguenti mostrano alcune delle funzioni che è possibile eseguire quando si usano file compressi.</span><span class="sxs-lookup"><span data-stu-id="a4914-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4914-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4914-106">Example</span></span>  
 <span data-ttu-id="a4914-107">Questo esempio mostra come creare ed estrarre un file compresso con estensione zip usando la classe <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="a4914-107">This example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="a4914-108">L'esempio comprime il contenuto di una cartella in un nuovo file ZIP e quindi estrae il contenuto in una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="a4914-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="a4914-109">Per usare la classe <xref:System.IO.Compression.ZipFile>, è necessario referenziare l'assembly `System.IO.Compression.FileSystem` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="a4914-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="a4914-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4914-110">Example</span></span>  
 <span data-ttu-id="a4914-111">L'esempio seguente mostra come eseguire l'iterazione del contenuto di un file ZIP esistente ed estrarre file con estensione txt.</span><span class="sxs-lookup"><span data-stu-id="a4914-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="a4914-112">L'esempio usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file ZIP esistente e la classe <xref:System.IO.Compression.ZipArchiveEntry> per controllare le singole voci nel file compresso.</span><span class="sxs-lookup"><span data-stu-id="a4914-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="a4914-113">Usa un metodo di estensione (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) per l'oggetto <xref:System.IO.Compression.ZipArchiveEntry>.</span><span class="sxs-lookup"><span data-stu-id="a4914-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="a4914-114">Il metodo di estensione è disponibile nella classe <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a4914-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a4914-115">Per usare la classe <xref:System.IO.Compression.ZipFileExtensions>, è necessario referenziare l'assembly `System.IO.Compression.FileSystem` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="a4914-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="a4914-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4914-116">Example</span></span>  
 <span data-ttu-id="a4914-117">L'esempio seguente usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file ZIP esistente e aggiunge un nuovo file al file compresso.</span><span class="sxs-lookup"><span data-stu-id="a4914-117">The next example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="a4914-118">Il nuovo file viene compresso quando lo si aggiunge al file ZIP esistente.</span><span class="sxs-lookup"><span data-stu-id="a4914-118">The new file gets compressed when you add it to the existing .zip file.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="a4914-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4914-119">Example</span></span>  
 <span data-ttu-id="a4914-120">È possibile usare anche le classi <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> per comprimere e decomprimere dati.</span><span class="sxs-lookup"><span data-stu-id="a4914-120">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="a4914-121">Queste due classi usano lo stesso algoritmo di compressione.</span><span class="sxs-lookup"><span data-stu-id="a4914-121">They use the same compression algorithm.</span></span> <span data-ttu-id="a4914-122">Gli oggetti <xref:System.IO.Compression.GZipStream> compressi scritti in un file con estensione gz possono essere decompressi usando molti strumenti comuni oltre ai metodi forniti da <xref:System.IO.Compression.GZipStream>.</span><span class="sxs-lookup"><span data-stu-id="a4914-122">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="a4914-123">Questo esempio mostra come comprimere e decomprimere una directory di file usando la classe <xref:System.IO.Compression.GZipStream>.</span><span class="sxs-lookup"><span data-stu-id="a4914-123">This example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class.</span></span>  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a4914-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4914-124">See Also</span></span>  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [<span data-ttu-id="a4914-125">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="a4914-125">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
