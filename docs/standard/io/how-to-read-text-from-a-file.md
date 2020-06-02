---
title: 'Procedura: leggere testo da un file'
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
ms.openlocfilehash: c46ccaf70d4d1aec030fb61bd8b2924d986e19d1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291760"
---
# <a name="how-to-read-text-from-a-file"></a>Procedura: leggere testo da un file
Negli esempi seguenti viene illustrato come leggere il testo in modo sincrono e in modo asincrono da un file di testo usando .NET per le applicazioni desktop. In entrambi gli esempi, quando si crea l'istanza della classe <xref:System.IO.StreamReader>, si immette il percorso relativo o assoluto del file.
  
> [!NOTE]
> Questi esempi di codice non sono applicabili allo sviluppo di applicazioni UWP (Universal Windows Platform), perché Windows Runtime offre tipi di flusso diversi per la lettura e la scrittura nei file. Per un esempio che illustra come leggere il testo da un file in un'app UWP, vedere [Guida introduttiva: lettura e scrittura di file](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)). Per esempi che illustrano come eseguire la conversione tra flussi .NET Framework e flussi Windows Runtime, vedere [procedura: eseguire la conversione tra flussi di .NET Framework e flussi Windows Runtime](how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example-synchronous-read-in-a-console-app"></a>Esempio: lettura sincrona in un'app console  
L'esempio seguente mostra un'operazione di lettura sincrona in un'app console. In questo esempio viene aperto il file di testo usando un lettore di flusso, il contenuto viene copiato in una stringa e la stringa viene quindi restituita nella console.  
  
> [!IMPORTANT]
> L'esempio presuppone che un file denominato *TestFile.txt* esista già nella stessa cartella dell'app.  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a>Esempio: lettura asincrona in un'app WPF
 L'esempio seguente illustra un'operazione di lettura asincrona in un'app Windows Presentation Foundation (WPF).  
  
> [!IMPORTANT]
> L'esempio presuppone che un file denominato *TestFile.txt* esista già nella stessa cartella dell'app.  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [I/O di file asincrono](asynchronous-file-i-o.md)  
- [Procedura: creare un elenco di directory](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Quickstart: Reading and writing files (Guida introduttiva: Lettura e scrittura di file)](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [Procedura: eseguire la conversione tra flussi .NET Framework e flussi Windows Runtime](how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [Procedura: leggere e scrivere in un file di dati appena creato](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Procedura: aprire e accodare un file di log](how-to-open-and-append-to-a-log-file.md)  
- [Procedura: scrivere testo in un file](how-to-write-text-to-a-file.md)  
- [Procedura: leggere caratteri da una stringa](how-to-read-characters-from-a-string.md)  
- [Procedura: scrivere caratteri in una stringa](how-to-write-characters-to-a-string.md)  
- [I/O di file e di flussi](index.md)
