---
title: 'Procedura: leggere e scrivere in un file di dati appena creato'
description: Informazioni su come leggere e scrivere in un file di dati appena creato in .NET usando le classi System. IO. BinaryReader e System. IO. BinaryWriter.
ms.date: 01/21/2019
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
ms.openlocfilehash: 9a6b2985b7f532476c0f4c0f998d710f95e55d3a
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769158"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Procedura: leggere e scrivere in un file di dati appena creato
Le classi <xref:System.IO.BinaryWriter?displayProperty=nameWithType> e <xref:System.IO.BinaryReader?displayProperty=nameWithType> vengono usate per scrivere e leggere i dati diversi da stringhe di caratteri. L'esempio seguente illustra come creare un flusso di file vuoto, quindi scrivere e leggere dati in tale flusso.

L'esempio crea un file di dati denominato *Test.data* nella directory corrente, crea gli oggetti <xref:System.IO.BinaryWriter> e <xref:System.IO.BinaryReader> associati e usa l'oggetto <xref:System.IO.BinaryWriter> per scrivere i valori interi da 0 a 10 in *Test.data*, lasciando il puntatore del file alla fine del file. L'oggetto <xref:System.IO.BinaryReader> reimposta quindi il puntatore del file sull'origine e legge il contenuto specificato.  
  
> [!NOTE]
> Se *Test.data* è già presente nella directory corrente, viene generata un'eccezione <xref:System.IO.IOException>. Usare l'opzione della modalità file <xref:System.IO.FileMode.Create?displayProperty=nameWithType> invece di <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> per creare sempre un nuovo file senza generare un'eccezione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [Procedura: enumerare directory e file](how-to-enumerate-directories-and-files.md)  
- [Procedura: aprire e accodare un file di log](how-to-open-and-append-to-a-log-file.md)  
- [Procedura: leggere testo da un file](how-to-read-text-from-a-file.md)  
- [Procedura: scrivere testo in un file](how-to-write-text-to-a-file.md)  
- [Procedura: leggere caratteri da una stringa](how-to-read-characters-from-a-string.md)  
- [Procedura: scrivere caratteri in una stringa](how-to-write-characters-to-a-string.md)  
- [I/O di file e di flussi](index.md)
