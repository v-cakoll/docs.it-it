---
title: 'Procedura: leggere e scrivere su un file di dati appena creato'
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
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b547f2c85495a497e5fc384f9a2ea44de7bf861c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Procedura: leggere e scrivere su un file di dati appena creato
Il <xref:System.IO.BinaryWriter> e <xref:System.IO.BinaryReader?displayProperty=nameWithType> classi vengono utilizzate per la scrittura e lettura dei dati anziché di stringhe di caratteri. Nell'esempio riportato di seguito viene illustrato come scrivere e leggere i dati da un nuovo flusso di file vuoto denominato `Test.data`. Dopo aver creato il file di dati nella directory corrente associata <xref:System.IO.BinaryWriter> e <xref:System.IO.BinaryReader> vengono creati oggetti e <xref:System.IO.BinaryWriter> oggetto viene utilizzato per scrivere gli interi da 0 a 10 per `Test.data`, che lascia il puntatore del file alla fine del file. Dopo aver impostato il puntatore del file sull'origine, il <xref:System.IO.BinaryReader> oggetto legge il contenuto specificato.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se `Test.data` esiste già nella directory corrente, un <xref:System.IO.IOException> viene generata un'eccezione. Utilizzare l'opzione della modalità file <xref:System.IO.FileMode.Create?displayProperty=nameWithType> quando si inizializza il flusso di file per creare sempre un nuovo file senza generare un'eccezione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryWriter>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
 <xref:System.IO.SeekOrigin>  
 [Procedura: Enumerare directory e file](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [Procedura: Aprire e accodare un file di log](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [Procedura: Leggere testo da un file](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [Procedura: Scrivere un testo in un file](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Procedura: Leggere caratteri da una stringa](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [Procedura: Scrivere caratteri in una stringa](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)
