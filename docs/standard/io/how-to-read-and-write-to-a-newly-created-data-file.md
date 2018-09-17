---
title: 'Procedura: leggere e scrivere su un file di dati appena creato'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65c56a11531f705b7e047e435ec575969d39a616
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45592906"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Procedura: leggere e scrivere su un file di dati appena creato
Le classi <xref:System.IO.BinaryWriter> e <xref:System.IO.BinaryReader?displayProperty=nameWithType> vengono usate per scrivere e leggere i dati invece delle stringhe di caratteri. L'esempio seguente illustra come scrivere e leggere i dati in un nuovo flusso di file vuoto denominato `Test.data`. Dopo aver creato il file di dati nella directory corrente, vengono creati gli oggetti <xref:System.IO.BinaryWriter> e <xref:System.IO.BinaryReader> associati e l'oggetto <xref:System.IO.BinaryWriter> viene usato per scrivere i valori interi da 0 a 10 in `Test.data`, lasciando il puntatore del file alla fine del file. Dopo avere reimpostato il puntatore del file sull'origine, l'oggetto <xref:System.IO.BinaryReader> legge il contenuto specificato.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se `Test.data` è già presente nella directory corrente, viene generata un'eccezione <xref:System.IO.IOException>. Utilizzare l'opzione della modalità file <xref:System.IO.FileMode.Create?displayProperty=nameWithType> quando si inizializza il flusso di file per creare sempre un nuovo file senza generare un'eccezione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [Procedura: Enumerare directory e file](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Procedura: Aprire e accodare un file di log](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Procedura: Leggere testo da un file](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Procedura: Scrivere un testo in un file](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Procedura: Leggere caratteri da una stringa](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Procedura: Scrivere caratteri in una stringa](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [I/O di file e di flussi](../../../docs/standard/io/index.md)
