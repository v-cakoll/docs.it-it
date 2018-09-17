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
ms.openlocfilehash: 669936d15cfe1ea125ed36ffdfcfd093b6aacbe1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45687634"
---
# <a name="how-to-compress-and-extract-files"></a>Procedura: Comprimere ed estrarre file

Lo spazio dei nomi <xref:System.IO.Compression> contiene i tipi seguenti per la compressione e la decompressione di file e flussi. È possibile usare questi tipi anche per leggere e modificare il contenuto di un file compresso:

- <xref:System.IO.Compression.ZipFile>

- <xref:System.IO.Compression.ZipArchive>

- <xref:System.IO.Compression.ZipArchiveEntry>

- <xref:System.IO.Compression.DeflateStream>

- <xref:System.IO.Compression.GZipStream>

Gli esempi seguenti mostrano alcune delle funzioni che è possibile eseguire quando si usano file compressi.

## <a name="example-1---create-and-extract-a-zip-file"></a>Esempio 1: creare ed estrarre un file con estensione zip

L'esempio seguente illustra come creare ed estrarre un file compresso con estensione zip usando la classe <xref:System.IO.Compression.ZipFile>. L'esempio comprime il contenuto di una cartella in un nuovo file ZIP e quindi estrae il contenuto in una nuova cartella. Per usare la classe <xref:System.IO.Compression.ZipFile>, è necessario referenziare l'assembly `System.IO.Compression.FileSystem` nel progetto.

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2---extract-specific-file-extensions"></a>Esempio 2: estrarre estensioni file specifiche

L'esempio seguente mostra come eseguire l'iterazione del contenuto di un file ZIP esistente ed estrarre file con estensione txt. L'esempio usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file ZIP esistente e la classe <xref:System.IO.Compression.ZipArchiveEntry> per controllare le singole voci nel file compresso. Usa un metodo di estensione (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) per l'oggetto <xref:System.IO.Compression.ZipArchiveEntry>. Il metodo di estensione è disponibile nella classe <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>. Per usare la classe <xref:System.IO.Compression.ZipFileExtensions>, è necessario referenziare l'assembly `System.IO.Compression.FileSystem` nel progetto.

> [!IMPORTANT]
> Quando si decomprimono i file, è necessario cercare percorsi dannosi che possono sfuggire alla directory in cui si vuole eseguire la decompressione. Si tratta di un attacco noto come attacco path traversal.

L'esempio seguente illustra come verificare la presenza di percorsi file dannosi e offre un metodo sicuro per la decompressione:

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3---add-a-new-file-to-an-existing-zip-file"></a>Esempio 3: aggiungere un nuovo file in un file con estensione zip esistente

L'esempio seguente usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file con estensione zip esistente e aggiunge un nuovo file al file compresso. Il nuovo file viene compresso quando lo si aggiunge al file ZIP esistente.

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4---compress-and-decompress-a-directory-of-gz-files"></a>Esempio 4: comprimere e decomprimere una directory di file con estensione gz

È possibile usare anche le classi <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> per comprimere e decomprimere dati. Queste due classi usano lo stesso algoritmo di compressione. Gli oggetti <xref:System.IO.Compression.GZipStream> compressi scritti in un file con estensione gz possono essere decompressi usando molti strumenti comuni oltre ai metodi forniti da <xref:System.IO.Compression.GZipStream>. L'esempio seguente illustra come comprimere e decomprimere una directory di file usando la classe <xref:System.IO.Compression.GZipStream>:

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [I/O di file e di flussi](../../../docs/standard/io/index.md)
