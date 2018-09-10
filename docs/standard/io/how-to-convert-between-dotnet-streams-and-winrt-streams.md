---
title: 'Procedura: eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96067ab6c8e13417158e4ebf7fae0e08cb9fbea4
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087479"
---
# <a name="how-to-convert-between-net-framework-streams-and-windows-runtime-streams"></a>Procedura: eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime

.NET Framework per le applicazioni Windows Store è un subset della versione completa di .NET Framework. Per motivi di sicurezza e di altri requisiti per le applicazioni Windows Store, non è possibile usare l'Integer set di API di .NET Framework per aprire e leggere i file. Per altre informazioni, vedere [Panoramica di .NET per le applicazioni Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Tuttavia, è possibile usare le API di .NET Framework per altre operazioni di manipolazione di un flusso. Per modificare questi flussi, potrebbe essere necessario eseguire la conversione tra un tipo di flusso di .NET Framework come <xref:System.IO.MemoryStream> o <xref:System.IO.FileStream> e un flusso di Windows Runtime come <xref:Windows.Storage.Streams.IInputStream>, <xref:Windows.Storage.Streams.IOutputStream> o <xref:Windows.Storage.Streams.IRandomAccessStream>.

La classe [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx) contiene metodi che semplificano queste conversioni. Tuttavia, esistono differenze sottostanti tra flussi in .NET Framework e Windows Runtime che avranno effetto sui risultati dell'utilizzo di questi metodi. I dettagli sono descritti nelle sezioni seguenti.

## <a name="converting-from-a-windows-runtime-stream-to-a-net-framework-stream"></a>Conversione da un flusso di Windows Runtime nel flusso di .NET Framework

È possibile convertire un flusso di Windows Runtime in un flusso di .NET Framework usando uno dei seguenti metodi [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx):

[System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx)  
Converte un flusso ad accesso casuale in Windows Runtime in un flusso gestito nel subset di .NET per applicazioni Windows Store.

[System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforwrite.aspx)  
Converte un flusso di output in Windows Runtime in un flusso gestito nel subset di .NET per applicazioni Windows Store.

[System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx)  
Converte un flusso di input in Windows Runtime in un flusso gestito nel subset di .NET per applicazioni Windows Store.

Windows Runtime offre tipi di flusso che supportano solo lettura, solo scrittura o lettura e scrittura e queste funzionalità vengono mantenute quando si converte un flusso di Windows Runtime in un flusso di .NET Framework. Inoltre, se un flusso di Windows Runtime viene convertito in un flusso di .NET Framework e viceversa, si ottiene l'istanza originale di Windows Runtime. È consigliabile usare il metodo di conversione corrispondente alle funzionalità del flusso di Windows Runtime che si desidera convertire. Tuttavia, poiché <xref:Windows.Storage.Streams.IRandomAccessStream> è leggibile e modificabile (implementa sia <xref:Windows.Storage.Streams.IOutputStream> che <xref:Windows.Storage.Streams.IInputStream>) è possibile usare uno dei metodi di conversione e le funzionalità del flusso originale vengono mantenute. Ad esempio, se si usa [System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx) per convertire <xref:Windows.Storage.Streams.IRandomAccessStream>, il flusso convertito di .NET Framework non sarà limitato alla sola lettura, ma sarà anche modificabile.

### <a name="to-convert-from-a-windows-runtime-random-access-stream-to-a-net-framework-stream"></a>Per convertire un flusso ad accesso casuale di Windows Runtime in un flusso di .NET Framework

- Usare il metodo [System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx).

  L'esempio di codice seguente mostra come chiedere all'utente di selezionare un file, aprirlo con le API di Windows Runtime e convertirlo in un flusso di .NET Framework, che viene letto e restituito in un blocco di testo. In questo scenario, il flusso viene in genere manipolato tramite le API di .NET Framework prima di restituire i risultati.

  Per eseguire l'esempio, è necessario creare un'applicazione Windows Store in XAML che contiene un blocco di testo denominato `TextBlock1` e un pulsante denominato  `Button1`. L'evento click del pulsante deve essere associato al metodo `button1_Click` illustrato nell'esempio.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]
  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#1)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#1)]

## <a name="converting-from-a-net-framework-stream-to-a-windows-runtime-stream"></a>Conversione da un flusso di .NET Framework nel flusso di Windows Runtime

È possibile convertire un flusso di .NET Framework in un flusso di Windows Runtime usando uno dei metodi seguenti [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx):

[System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx) Converte un flusso gestito nel subset di .NET per applicazioni Windows Store in un flusso di input in Windows Runtime.

[System.IO.WindowsRuntimeStreamExtensions.AsOutputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asoutputstream.aspx) Converte un flusso gestito nel subset di .NET per applicazioni Windows Store in un flusso di output in Windows Runtime.

[AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md) Converte un flusso gestito nel subset di .NET per applicazioni Windows Store in un flusso ad accesso casuale che può essere usato per la lettura o scrittura in Windows Runtime.

Quando si converte un flusso di .NET Framework in un flusso di Windows Runtime, le funzionalità del flusso convertito dipenderanno dal flusso originale. Ad esempio, se il flusso originale supporta sia la lettura che la scrittura e si chiama [System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx) per convertire il flusso, il tipo restituito sarà `IRandomAccessStream`, che implementa `IInputStream` e `IOutputStream` e supporta lettura e scrittura.

I flussi di .NET Framework non supportano la clonazione, anche dopo la conversione. Ciò significa che se si converte un flusso di .NET Framework in un flusso di Windows Runtime e si chiama <xref:Windows.Storage.Streams.InMemoryRandomAccessStream.GetInputStreamAt%2A> o <xref:Windows.Storage.Streams.IRandomAccessStream.GetOutputStreamAt%2A> che chiama <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A>o <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> direttamente, si verificherà un'eccezione.

### <a name="to-convert-from-a-net-framework-stream-to-a-windows-runtime-random-access-stream"></a>Per convertire un flusso di .NET Framework in un flusso ad accesso casuale di Windows Runtime

- Usare il metodo [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md), come illustrato nell'esempio seguente:

  > [!IMPORTANT]
  > Assicurarsi che il flusso di .NET Framework usato supporti la ricerca oppure copiarlo in un flusso che la supporti. A tale scopo, è possibile usare la proprietà <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType>.

  Per eseguire l'esempio, è necessario creare un'applicazione Windows Store in XAML destinata a .NET Framework 4.5.1 contenente un blocco di testo denominato `TextBlock2` e un pulsante denominato `Button2`. L'evento click del pulsante deve essere associato al metodo `button2_Click` illustrato nell'esempio.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]
  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#2](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#2)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#2)]

## <a name="see-also"></a>Vedere anche

- [Guida introduttiva: Lettura e scrittura di un file (Windows)](https://msdn.microsoft.com/library/windows/apps/hh464978.aspx)  
- [Panoramica di .NET per le app di Windows Store](https://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
- [.NET per app di Windows Store – API supportate](https://msdn.microsoft.com/library/windows/apps/br230232.aspx)  