---
title: 'Procedura: leggere testo da un fileHow to: Read Text from a file'
ms.date: 01/03/2019
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
ms.openlocfilehash: 8676e5f0acd0646b4854df7dde060ec15548ec3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155724"
---
# <a name="how-to-read-text-from-a-file"></a>Procedura: leggere testo da un fileHow to: Read Text from a file
Negli esempi seguenti viene illustrato come leggere il testo in modo sincrono e in modo asincrono da un file di testo usando .NET per le applicazioni desktop. In entrambi gli esempi, quando si crea l'istanza della classe <xref:System.IO.StreamReader>, si immette il percorso relativo o assoluto del file.
  
> [!NOTE]
> Questi esempi di codice non sono applicabili allo sviluppo di applicazioni UWP (Universal Windows Platform), perché Windows Runtime offre tipi di flusso diversi per la lettura e la scrittura nei file. Per un esempio che illustra come leggere il testo da un file in un'app UWP, vedere [Guida introduttiva: Lettura e scrittura](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10))di file. Per esempi che illustrano come eseguire la conversione tra flussi .NET Framework e flussi di Windows Runtime, vedere [Procedura: eseguire la conversione tra flussi .NET Framework e flussi](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)di Windows Runtime.  
  
## <a name="example-synchronous-read-in-a-console-app"></a>Esempio: lettura sincrona in un'app consoleExample: Synchronous read in a console app  
L'esempio seguente mostra un'operazione di lettura sincrona in un'app console. In questo esempio viene aperto il file di testo usando un lettore di flusso, il contenuto viene copiato in una stringa e la stringa viene quindi restituita nella console.  
  
> [!IMPORTANT]
> L'esempio presuppone che un file denominato *TestFile.txt* esista già nella stessa cartella dell'app.  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a>Esempio: lettura asincrona in un'app WPFExample: Asynchronous read in a WPF app
 L'esempio seguente illustra un'operazione di lettura asincrona in un'app Windows Presentation Foundation (WPF).  
  
> [!IMPORTANT]
> L'esempio presuppone che un file denominato *TestFile.txt* esista già nella stessa cartella dell'app.  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [I/O di file asincroni](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [Procedura: Creare un elenco di directoryHow to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Quickstart: Reading and writing files (Guida introduttiva: Lettura e scrittura di file)](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [Procedura: eseguire la conversione tra flussi di .NET Framework e flussi di Windows RuntimeHow to: Convert between .NET Framework streams and Windows Runtime streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [Procedura: leggere e scrivere in un file di dati appena creatoHow to: Read and write to a newly created data file](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Procedura: aprire e aggiungere a un file di registroHow to: Open and append to a log file](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Procedura: scrivere testo in un fileHow to: Write text to a file](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Procedura: leggere caratteri da una stringaHow to: Read characters from a string](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Procedura: scrivere caratteri in una stringaHow to: Write characters to a string](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [I/O di file e di flussi](../../../docs/standard/io/index.md)
