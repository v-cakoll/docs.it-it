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
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22a95ce18b602d4e329499c5d36557213e08a8b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="95df9-102">Procedura: comprimere ed estrarre file</span><span class="sxs-lookup"><span data-stu-id="95df9-102">How to: Compress and Extract Files</span></span>
<span data-ttu-id="95df9-103">Il <xref:System.IO.Compression> dello spazio dei nomi contiene i seguenti tipi per la compressione e decompressione dei file e flussi.</span><span class="sxs-lookup"><span data-stu-id="95df9-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="95df9-104">È inoltre possibile utilizzare questi tipi per leggere e modificare il contenuto di un file compresso:</span><span class="sxs-lookup"><span data-stu-id="95df9-104">You can also use these types to read and modify the contents of a compressed file:</span></span>  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 <span data-ttu-id="95df9-105">Gli esempi seguenti mostrano alcune delle funzioni che è possibile eseguire quando si lavora con i file compressi.</span><span class="sxs-lookup"><span data-stu-id="95df9-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95df9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="95df9-106">Example</span></span>  
 <span data-ttu-id="95df9-107">In questo esempio viene illustrato come creare ed estrarre un file compresso con estensione zip utilizzando la <xref:System.IO.Compression.ZipFile> classe.</span><span class="sxs-lookup"><span data-stu-id="95df9-107">This example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="95df9-108">Comprime il contenuto di una cartella in un nuovo file con estensione zip e quindi estrae il contenuto in una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="95df9-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="95df9-109">Utilizzare il <xref:System.IO.Compression.ZipFile> (classe), è necessario fare riferimento il `System.IO.Compression.FileSystem` assembly nel progetto.</span><span class="sxs-lookup"><span data-stu-id="95df9-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="95df9-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="95df9-110">Example</span></span>  
 <span data-ttu-id="95df9-111">Nell'esempio seguente viene illustrato come scorrere il contenuto di un file con estensione zip esistente ed estrarre i file con estensione txt.</span><span class="sxs-lookup"><span data-stu-id="95df9-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="95df9-112">Usa il <xref:System.IO.Compression.ZipArchive> classe per accedere al file ZIP esistenti e <xref:System.IO.Compression.ZipArchiveEntry> classe per controllare le singole voci nel file compresso.</span><span class="sxs-lookup"><span data-stu-id="95df9-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="95df9-113">Usa un metodo di estensione (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) per il <xref:System.IO.Compression.ZipArchiveEntry> oggetto.</span><span class="sxs-lookup"><span data-stu-id="95df9-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="95df9-114">Il metodo di estensione è disponibile nel <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="95df9-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="95df9-115">Utilizzare il <xref:System.IO.Compression.ZipFileExtensions> (classe), è necessario fare riferimento il `System.IO.Compression.FileSystem` assembly nel progetto.</span><span class="sxs-lookup"><span data-stu-id="95df9-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="95df9-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="95df9-116">Example</span></span>  
 <span data-ttu-id="95df9-117">L'esempio seguente viene utilizzata la <xref:System.IO.Compression.ZipArchive> classe per accedere a un file con estensione zip esistente e aggiunge un nuovo file per il file compresso.</span><span class="sxs-lookup"><span data-stu-id="95df9-117">The next example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="95df9-118">Il nuovo file viene compressa quando viene aggiunta al file con estensione zip esistente.</span><span class="sxs-lookup"><span data-stu-id="95df9-118">The new file gets compressed when you add it to the existing .zip file.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="95df9-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="95df9-119">Example</span></span>  
 <span data-ttu-id="95df9-120">È inoltre possibile utilizzare il <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> classi per comprimere e decomprimere i dati.</span><span class="sxs-lookup"><span data-stu-id="95df9-120">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="95df9-121">Usano lo stesso algoritmo di compressione.</span><span class="sxs-lookup"><span data-stu-id="95df9-121">They use the same compression algorithm.</span></span> <span data-ttu-id="95df9-122">Compresso <xref:System.IO.Compression.GZipStream> gli oggetti che vengono scritti in un file con estensione gz possono essere decompressi utilizzando numerosi strumenti comuni, oltre ai metodi forniti da <xref:System.IO.Compression.GZipStream>.</span><span class="sxs-lookup"><span data-stu-id="95df9-122">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="95df9-123">In questo esempio viene illustrato come comprimere e decomprimere una directory di file utilizzando il <xref:System.IO.Compression.GZipStream> classe.</span><span class="sxs-lookup"><span data-stu-id="95df9-123">This example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class.</span></span>  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="95df9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95df9-124">See Also</span></span>  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [<span data-ttu-id="95df9-125">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="95df9-125">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
