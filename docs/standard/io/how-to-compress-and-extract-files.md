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
# <a name="how-to-compress-and-extract-files"></a>Procedura: comprimere ed estrarre file
Il <xref:System.IO.Compression> dello spazio dei nomi contiene i seguenti tipi per la compressione e decompressione dei file e flussi. È inoltre possibile utilizzare questi tipi per leggere e modificare il contenuto di un file compresso:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 Gli esempi seguenti mostrano alcune delle funzioni che è possibile eseguire quando si lavora con i file compressi.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come creare ed estrarre un file compresso con estensione zip utilizzando la <xref:System.IO.Compression.ZipFile> classe. Comprime il contenuto di una cartella in un nuovo file con estensione zip e quindi estrae il contenuto in una nuova cartella. Utilizzare il <xref:System.IO.Compression.ZipFile> (classe), è necessario fare riferimento il `System.IO.Compression.FileSystem` assembly nel progetto.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come scorrere il contenuto di un file con estensione zip esistente ed estrarre i file con estensione txt. Usa il <xref:System.IO.Compression.ZipArchive> classe per accedere al file ZIP esistenti e <xref:System.IO.Compression.ZipArchiveEntry> classe per controllare le singole voci nel file compresso. Usa un metodo di estensione (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) per il <xref:System.IO.Compression.ZipArchiveEntry> oggetto. Il metodo di estensione è disponibile nel <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> classe. Utilizzare il <xref:System.IO.Compression.ZipFileExtensions> (classe), è necessario fare riferimento il `System.IO.Compression.FileSystem` assembly nel progetto.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente viene utilizzata la <xref:System.IO.Compression.ZipArchive> classe per accedere a un file con estensione zip esistente e aggiunge un nuovo file per il file compresso. Il nuovo file viene compressa quando viene aggiunta al file con estensione zip esistente.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a>Esempio  
 È inoltre possibile utilizzare il <xref:System.IO.Compression.GZipStream> e <xref:System.IO.Compression.DeflateStream> classi per comprimere e decomprimere i dati. Usano lo stesso algoritmo di compressione. Compresso <xref:System.IO.Compression.GZipStream> gli oggetti che vengono scritti in un file con estensione gz possono essere decompressi utilizzando numerosi strumenti comuni, oltre ai metodi forniti da <xref:System.IO.Compression.GZipStream>. In questo esempio viene illustrato come comprimere e decomprimere una directory di file utilizzando il <xref:System.IO.Compression.GZipStream> classe.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)
