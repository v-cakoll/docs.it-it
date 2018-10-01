---
title: 'Procedura: leggere testo da un file'
ms.date: 06/19/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f979f3d09079f36d12408d0a82ef58e603da859
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2018
ms.locfileid: "47203177"
---
# <a name="how-to-read-text-from-a-file"></a>Procedura: leggere testo da un file
Negli esempi seguenti viene illustrato come leggere il testo in modo sincrono e in modo asincrono da un file di testo usando .NET per le applicazioni desktop. In entrambi gli esempi, quando si crea l'istanza della classe <xref:System.IO.StreamReader>, si immette il percorso relativo o assoluto del file. Negli esempi si presuppone che il file denominato TestFile.txt sia nella stessa cartella dell'applicazione.  
  
 Questi esempi di codice non sono applicabili allo sviluppo di applicazioni Windows Store poiché Windows Runtime offre tipi di flusso diversi per la lettura e la scrittura nei file. Per un esempio che illustri come leggere testo da un file in un'app di Windows Store, vedere [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)) (Guida introduttiva: Lettura e scrittura di file). Per esempi che illustrino come eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime, vedere [Procedura: Eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra un'operazione di lettura sincrona in un'applicazione console. In questo esempio il file di testo viene aperto tramite un lettore del flusso e il contenuto viene copiato in una stringa, che viene trasmessa come output alla console.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra l'operazione di lettura asincrona in un'applicazione Windows Presentation Foundation (WPF).  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [I/O di file asincrono](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [Procedura: creare una visualizzazione directory](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
- [Quickstart: Reading and writing files (Guida introduttiva: Lettura e scrittura di file)](https://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
- [Procedura: Eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [Procedura: Leggere e scrivere su un file di dati appena creato](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Procedura: Aprire e accodare un file di log](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Procedura: Scrivere un testo in un file](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Procedura: Leggere caratteri da una stringa](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Procedura: Scrivere caratteri in una stringa](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [I/O di file e di flussi](../../../docs/standard/io/index.md)
