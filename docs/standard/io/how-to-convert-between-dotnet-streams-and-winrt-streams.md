---
title: 'Procedura: Eseguire la conversione tra flussi di .NET Framework e di Windows Runtime (solo Windows)'
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc38e69a79af7c7220b8e3b55d4cb1f4ca3695f6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255198"
---
# <a name="how-to-convert-between-net-framework-and-windows-runtime-streams-windows-only"></a>Procedura: Eseguire la conversione tra flussi di .NET Framework e di Windows Runtime (solo Windows)

.NET Framework per le app UWP è un subset della versione completa di .NET Framework. Per motivi di sicurezza e di altri requisiti per le app UWP, non è possibile usare l'intero set di API di .NET Framework per aprire e leggere i file. Per altre informazioni, vedere [.NET for UWP apps overview](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)) (Panoramica di .NET per le app UWP). Tuttavia, è possibile usare le API di .NET Framework per altre operazioni di manipolazione di un flusso. Per modificare questi flussi, è possibile eseguire la conversione tra un tipo di flusso di .NET Framework come <xref:System.IO.MemoryStream> o <xref:System.IO.FileStream> e un flusso di Windows Runtime come <xref:Windows.Storage.Streams.IInputStream>, <xref:Windows.Storage.Streams.IOutputStream> o <xref:Windows.Storage.Streams.IRandomAccessStream>.

La classe [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx) contiene metodi che semplificano queste conversioni. Tuttavia, le differenze sottostanti tra i flussi in .NET Framework e Windows Runtime hanno effetto sui risultati dell'uso di questi metodi, come descritto nelle sezioni seguenti:

## <a name="convert-from-a-windows-runtime-to-a-net-framework-stream"></a>Eseguire la conversione da un flusso di Windows Runtime a un flusso di .NET Framework
Per convertire un flusso di Windows Runtime in un flusso di .NET Framework, usare uno dei metodi [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx) seguenti:

- [System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx) converte un flusso ad accesso casuale in Windows Runtime in un flusso gestito in .NET per app UWP.
  
- [System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforwrite.aspx) converte un flusso di output in Windows Runtime in un flusso gestito in .NET per app UWP.
  
- [System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx) converte un flusso di input in Windows Runtime in un flusso gestito in .NET per app UWP.

Windows Runtime offre tipi di flusso che supportano solo la lettura, solo la scrittura oppure la lettura e la scrittura. Queste funzionalità vengono mantenute quando si converte un flusso di Windows Runtime in un flusso di .NET Framework. Inoltre, se un flusso di Windows Runtime viene convertito in un flusso di .NET Framework e viceversa, si ottiene l'istanza originale di Windows Runtime. 

È consigliabile usare il metodo di conversione corrispondente alle funzionalità del flusso di Windows Runtime da convertire. Tuttavia, dato che <xref:Windows.Storage.Streams.IRandomAccessStream> è leggibile e modificabile (implementa sia <xref:Windows.Storage.Streams.IOutputStream> che <xref:Windows.Storage.Streams.IInputStream>) i metodi di conversione mantengono le funzionalità del flusso originale. Ad esempio, se si usa [System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx) per convertire <xref:Windows.Storage.Streams.IRandomAccessStream>, il flusso convertito di .NET Framework non viene limitato alla sola lettura, ma è accessibile anche in scrittura.

## <a name="example-convert-windows-runtime-random-access-to-net-framework-stream"></a>Esempio: Convertire un flusso ad accesso casuale di Windows Runtime in un flusso di .NET Framework
Per convertire un flusso ad accesso casuale di Windows Runtime in un flusso di .NET Framework, usare il metodo [System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx):

Nell'esempio di codice seguente viene richiesto di selezionare un file, che viene poi aperto con le API di Windows Runtime e convertito in un flusso di .NET Framework. L'esempio legge il flusso e genera l'output in un blocco di testo. Il flusso viene in genere manipolato tramite le API di .NET Framework prima di restituire i risultati.

Per eseguire l'esempio, creare un'app UWP che contiene un blocco di testo denominato `TextBlock1` e un pulsante denominato `Button1`. Associare l'evento click del pulsante al metodo `button1_Click` nell'esempio.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage1.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage1.xaml.vb)]

## <a name="convert-from-a-net-framework-to-a-windows-runtime-stream"></a>Eseguire la conversione da un flusso di .NET Framework a un flusso di Windows Runtime
Per convertire un flusso di .NET Framework in un flusso di Windows Runtime, usare uno dei metodi [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx) seguenti:

- [System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx) converte un flusso gestito in .NET per app UWP in un flusso di input in Windows Runtime.
  
- [System.IO.WindowsRuntimeStreamExtensions.AsOutputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asoutputstream.aspx) converte un flusso gestito in .NET per app UWP in un flusso di output in Windows Runtime.
  
- [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md) converte un flusso gestito in .NET per app UWP in un flusso ad accesso casuale che può essere usato da Windows Runtime per la lettura o la scrittura.

Quando si converte un flusso di .NET Framework in un flusso di Windows Runtime, le funzionalità del flusso convertito dipendono dal flusso originale. Ad esempio, se il flusso originale supporta sia la lettura che la scrittura e si chiama [System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx) per convertire il flusso, il tipo restituito è `IRandomAccessStream`. `IRandomAccessStream` implementa `IInputStream` e `IOutputStream` e supporta lettura e scrittura.

I flussi di .NET Framework non supportano la clonazione, anche dopo la conversione. Se si converte un flusso di .NET Framework in un flusso di Windows Runtime e si chiama <xref:Windows.Storage.Streams.InMemoryRandomAccessStream.GetInputStreamAt%2A> o <xref:Windows.Storage.Streams.IRandomAccessStream.GetOutputStreamAt%2A>, che chiama <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> oppure si chiama <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> direttamente, si verifica un'eccezione.

## <a name="example-convert-net-framework-to-windows-runtime-random-access-stream"></a>Esempio: Convertire un flusso di .NET Framework in un flusso ad accesso casuale di Windows Runtime

Per convertire un flusso di .NET Framework in un flusso ad accesso casuale di Windows Runtime, usare il metodo [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md), come illustrato nell'esempio seguente:

> [!IMPORTANT]
> Assicurarsi che il flusso di .NET Framework usato supporti la ricerca oppure copiarlo in un flusso che la supporti. A tale scopo, è possibile usare la proprietà <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType> .

Per eseguire l'esempio, creare un'app XAML UWP destinata a .NET Framework 4.5.1 contenente un blocco di testo denominato `TextBlock2` e un pulsante denominato `Button2`. Associare l'evento click del pulsante al metodo `button2_Click` nell'esempio.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage2.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage2.xaml.vb)]

## <a name="see-also"></a>Vedere anche

- [Avvio rapido: Read and write a file (Windows)](https://msdn.microsoft.com/library/windows/apps/hh464978.aspx) (Leggere e scrivere file in Windows)  
- [Panoramica di .NET per le app di Windows Store](https://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
- [.NET for Windows Store apps: Supported APIs](https://msdn.microsoft.com/library/windows/apps/br230232.aspx) (.NET per app Windows Store: API supportate)  
