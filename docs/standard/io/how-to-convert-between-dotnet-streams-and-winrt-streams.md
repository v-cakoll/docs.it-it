---
title: 'Procedura: eseguire la conversione tra flussi .NET Framework e Windows Runtime (solo Windows)'
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
ms.openlocfilehash: 7413c3fae7d7189ec8dca43b0c77f6b56158f416
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159468"
---
# <a name="how-to-convert-between-net-framework-and-windows-runtime-streams-windows-only"></a>Procedura: eseguire la conversione tra flussi .NET Framework e Windows Runtime (solo Windows)

.NET Framework per le app UWP è un subset della versione completa di .NET Framework. Per motivi di sicurezza e di altri requisiti per le app UWP, non è possibile usare l'intero set di API di .NET Framework per aprire e leggere i file. Per altre informazioni, vedere [.NET for UWP apps overview](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)) (Panoramica di .NET per le app UWP). Tuttavia, è possibile usare le API di .NET Framework per altre operazioni di manipolazione di un flusso. Per modificare questi flussi, è possibile eseguire la conversione tra un tipo di flusso di .NET Framework come <xref:System.IO.MemoryStream> o <xref:System.IO.FileStream> e un flusso di Windows Runtime come <xref:Windows.Storage.Streams.IInputStream>, <xref:Windows.Storage.Streams.IOutputStream> o <xref:Windows.Storage.Streams.IRandomAccessStream>.

La classe <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=nameWithType> contiene metodi che semplificano queste conversioni. Tuttavia, le differenze sottostanti tra i flussi in .NET Framework e Windows Runtime hanno effetto sui risultati dell'uso di questi metodi, come descritto nelle sezioni seguenti:

## <a name="convert-from-a-windows-runtime-to-a-net-framework-stream"></a>Eseguire la conversione da un flusso di Windows Runtime a un flusso di .NET Framework
Per convertire un flusso di Windows Runtime in un flusso di .NET Framework, usare uno dei metodi <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=nameWithType> seguenti:

- <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A?displayProperty=nameWithType> converte un flusso ad accesso casuale di Windows Runtime in un flusso gestito di .NET per app UWP.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite%2A?displayProperty=nameWithType> converte un flusso di output di Windows Runtime in un flusso gestito di .NET per app UWP.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A?displayProperty=nameWithType> converte un flusso di input di Windows Runtime in un flusso gestito di .NET per app UWP.

Windows Runtime offre tipi di flusso che supportano solo la lettura, solo la scrittura oppure la lettura e la scrittura. Queste funzionalità vengono mantenute quando si converte un flusso di Windows Runtime in un flusso di .NET Framework. Inoltre, se un flusso di Windows Runtime viene convertito in un flusso di .NET Framework e viceversa, si ottiene l'istanza originale di Windows Runtime.

È consigliabile usare il metodo di conversione corrispondente alle funzionalità del flusso di Windows Runtime da convertire. Tuttavia, dato che <xref:Windows.Storage.Streams.IRandomAccessStream> è leggibile e modificabile (implementa sia <xref:Windows.Storage.Streams.IOutputStream> che <xref:Windows.Storage.Streams.IInputStream>) i metodi di conversione mantengono le funzionalità del flusso originale. Ad esempio, se si usa <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A?displayProperty=nameWithType> per convertire <xref:Windows.Storage.Streams.IRandomAccessStream>, il flusso convertito di .NET Framework non viene limitato alla sola lettura, ma è accessibile anche in scrittura.

## <a name="example-convert-windows-runtime-random-access-to-net-framework-stream"></a>Esempio: convertire Windows Runtime accesso casuale al flusso .NET Framework
Per convertire un flusso ad accesso casuale di Windows Runtime in un flusso di .NET Framework, usare il metodo <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A?displayProperty=nameWithType>.

Nell'esempio di codice seguente viene richiesto di selezionare un file, che viene poi aperto con le API di Windows Runtime e convertito in un flusso di .NET Framework. L'esempio legge il flusso e genera l'output in un blocco di testo. Il flusso viene in genere manipolato tramite le API di .NET Framework prima di restituire i risultati.

Per eseguire l'esempio, creare un'app UWP che contiene un blocco di testo denominato `TextBlock1` e un pulsante denominato `Button1`. Associare l'evento click del pulsante al metodo `button1_Click` nell'esempio.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage1.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage1.xaml.vb)]

## <a name="convert-from-a-net-framework-to-a-windows-runtime-stream"></a>Eseguire la conversione da un flusso di .NET Framework a un flusso di Windows Runtime
Per convertire un flusso di .NET Framework in un flusso di Windows Runtime, usare uno dei metodi <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=nameWithType> seguenti:

- <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A?displayProperty=nameWithType> converte un flusso gestito di .NET per app UWP in un flusso di input di Windows Runtime.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsOutputStream%2A?displayProperty=nameWithType> converte un flusso gestito di .NET per app UWP in un flusso di output di Windows Runtime.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream%2A?displayProperty=nameWithType> converte un flusso gestito in .NET per app UWP in un flusso ad accesso casuale che può essere usato da Windows Runtime per la lettura o la scrittura.

Quando si converte un flusso di .NET Framework in un flusso di Windows Runtime, le funzionalità del flusso convertito dipendono dal flusso originale. Ad esempio, se il flusso originale supporta sia la lettura che la scrittura e si chiama <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A?displayProperty=nameWithType> per convertirlo, il tipo restituito è `IRandomAccessStream`. `IRandomAccessStream` implementa `IInputStream` e `IOutputStream` e supporta lettura e scrittura.

I flussi di .NET Framework non supportano la clonazione, anche dopo la conversione. Se si converte un flusso di .NET Framework in un flusso di Windows Runtime e si chiama <xref:Windows.Storage.Streams.InMemoryRandomAccessStream.GetInputStreamAt%2A> o <xref:Windows.Storage.Streams.IRandomAccessStream.GetOutputStreamAt%2A>, che chiama <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> oppure si chiama <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> direttamente, si verifica un'eccezione.

## <a name="example-convert-net-framework-to-windows-runtime-random-access-stream"></a>Esempio: convertire .NET Framework in Windows Runtime flusso ad accesso casuale

Per convertire un flusso di .NET Framework in un flusso ad accesso casuale di Windows Runtime usare il metodo <xref:System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream%2A>, come illustrato nell'esempio seguente:

> [!IMPORTANT]
> Assicurarsi che il flusso di .NET Framework usato supporti la ricerca oppure copiarlo in un flusso che la supporti. A tale scopo, è possibile usare la proprietà <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType> .

Per eseguire l'esempio, creare un'app XAML UWP destinata a .NET Framework 4.5.1 contenente un blocco di testo denominato `TextBlock2` e un pulsante denominato `Button2`. Associare l'evento click del pulsante al metodo `button2_Click` nell'esempio.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage2.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage2.xaml.vb)]

## <a name="see-also"></a>Vedere anche

- [Guida introduttiva: lettura e scrittura di un file (Windows)](https://docs.microsoft.com/previous-versions/windows/apps/hh464978(v=win.10))  
- [Panoramica di .NET per le app di Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))  
- [.NET per le API delle app di Windows Store](https://docs.microsoft.com/previous-versions/br230232(v=vs.120))  
