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
# <a name="how-to-compress-and-extract-files"></a>Procedura: comprimere ed estrarre file
Lo spazio dei nomi <xref:System.IO.Compression> contiene i tipi seguenti per la compressione e la decompressione di file e flussi. È possibile usare questi tipi anche per leggere e modificare il contenuto di un file compresso:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 Gli esempi seguenti mostrano alcune delle funzioni che è possibile eseguire quando si usano file compressi.  
  
## <a name="example"></a>Esempio  
 Questo esempio mostra come creare ed estrarre un file compresso con estensione zip usando la classe <xref:System.IO.Compression.ZipFile>. L'esempio comprime il contenuto di una cartella in un nuovo file ZIP e quindi estrae il contenuto in una nuova cartella. Per usare la classe <xref:System.IO.Compression.ZipFile>, è necessario referenziare l'assembly `System.IO.Compression.FileSystem` nel progetto.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come eseguire l'iterazione del contenuto di un file ZIP esistente ed estrarre file con estensione txt. L'esempio usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file ZIP esistente e la classe <xref:System.IO.Compression.ZipArchiveEntry> per controllare le singole voci nel file compresso. Usa un metodo di estensione (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) per l'oggetto <xref:System.IO.Compression.ZipArchiveEntry>. Il metodo di estensione è disponibile nella classe <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>. Per usare la classe <xref:System.IO.Compression.ZipFileExtensions>, è necessario referenziare l'assembly `System.IO.Compression.FileSystem` nel progetto.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa la classe <xref:System.IO.Compression.ZipArchive> per accedere a un file ZIP esistente e aggiunge un nuovo file al file compresso. Il nuovo file viene compresso quando lo si aggiunge al file ZIP esistente.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a>Esempio  
 È possibile usare anche le classi <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> per comprimere e decomprimere dati. Queste due classi usano lo stesso algoritmo di compressione. Gli oggetti <xref:System.IO.Compression.GZipStream> compressi scritti in un file con estensione gz possono essere decompressi usando molti strumenti comuni oltre ai metodi forniti da <xref:System.IO.Compression.GZipStream>. Questo esempio mostra come comprimere e decomprimere una directory di file usando la classe <xref:System.IO.Compression.GZipStream>.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)
