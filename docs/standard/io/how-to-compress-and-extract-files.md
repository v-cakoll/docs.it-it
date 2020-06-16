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
# <a name="how-to-compress-and-extract-files"></a>Procedura: Comprimere ed estrarre file

Lo spazio dei nomi <xref:System.IO.Compression> contiene i tipi seguenti per la compressione e la decompressione di file e flussi. È possibile usare questi tipi anche per leggere e modificare il contenuto di un file compresso.

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

Gli esempi seguenti mostrano alcune delle operazioni che è possibile eseguire con i file compressi. Per questi esempi è necessario aggiungere al progetto i pacchetti NuGet seguenti:

- [System.IO.Compression](https://www.nuget.org/packages/System.IO.Compression)
- [System.IO.Compression.ZipFile](https://www.nuget.org/packages/System.IO.Compression.ZipFile)

Se si usa .NET Framework, aggiungere i riferimenti alle due librerie seguenti al progetto:

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a>Esempio 1: creare ed estrarre un file zip

Nell'esempio seguente viene illustrato come creare ed estrarre un file *ZIP* compresso usando la classe <xref:System.IO.Compression.ZipFile>. L'esempio comprime il contenuto di una cartella in un nuovo file *ZIP* e quindi estrae il contenuto in una nuova cartella.

Per eseguire l'esempio, creare una cartella *start* nella cartella del programma e copiarvi i file da comprimere.

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a>Esempio 2: estrarre estensioni di file specifiche

Il prossimo esempio mostra come eseguire l'iterazione del contenuto di un file *ZIP* esistente ed estrarre i file con estensione *txt*. Usa la classe <xref:System.IO.Compression.ZipArchive> per accedere al file ZIP e la classe <xref:System.IO.Compression.ZipArchiveEntry> per controllare le singole voci. Il metodo di estensione <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> per l'oggetto <xref:System.IO.Compression.ZipArchiveEntry> è disponibile nella classe <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.

Per eseguire l'esempio, inserire un file *ZIP* denominato *result.zip* nella cartella del programma. Quando richiesto, specificare un nome di cartella in cui estrarre i file.

> [!IMPORTANT]
> Quando si decomprimono i file, è necessario cercare percorsi dannosi che possono sfuggire alla directory in cui si esegue la decompressione. Si tratta di un attacco noto come attacco path traversal. L'esempio seguente illustra come verificare la presenza di percorsi file dannosi e offre un metodo sicuro per la decompressione.

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a>Esempio 3: aggiungere un file a un file Zip esistente

L'esempio seguente usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file *ZIP* esistente e aggiunge un nuovo file al file compresso. Il nuovo file viene compresso quando lo si aggiunge al file ZIP esistente.

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a>Esempio 4: comprimere e decomprimere i file. gz

È possibile usare anche le classi <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> per comprimere e decomprimere dati. Queste due classi usano lo stesso algoritmo di compressione. È possibile decomprimere gli oggetti <xref:System.IO.Compression.GZipStream> scritti in un file con estensione *gz* con molti strumenti comuni. L'esempio seguente illustra come comprimere e decomprimere una directory di file usando la classe <xref:System.IO.Compression.GZipStream>:

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [I/O di file e di flussi](index.md)
