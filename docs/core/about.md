---
title: Panoramica di .NET Core
description: Informazioni sulle caratteristiche e la composizione di .NET Core e sul confronto con altre implementazioni di .NET.
ms.date: 03/26/2020
ms.openlocfilehash: e57451968ed8c4d5457acea084d3c6c9f998b8da
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144526"
---
# <a name="net-core-overview"></a>Panoramica di .NET Core

.NET Core ha le caratteristiche seguenti:

- **Multipiattaforma:** Viene eseguito nei [sistemi operativi](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md)Windows, MacOS e Linux.
- **Open Source:** Il Framework .NET Core è [Open Source](https://github.com/dotnet/core), usando le licenze mit e Apache 2. .NET Core è un progetto [.NET Foundation](https://dotnetfoundation.org/).
- **Moderno:** Implementa paradigmi moderni come la programmazione asincrona, i modelli senza copia usando gli struct e la governance delle risorse per i contenitori.
- **Prestazioni:**  Offre [prestazioni elevate](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-core-3-0/) con funzionalità quali [intrinseci hardware](https://devblogs.microsoft.com/dotnet/hardware-intrinsics-in-net-core/), compilazione a più [livelli](https://github.com/dotnet/coreclr/blob/master/Documentation/design-docs/tiered-compilation.md)e [span \<T> ](../standard/memory-and-spans/index.md).
- **Coerenza tra gli ambienti:** Esegue il codice con lo stesso comportamento in più sistemi operativi e architetture, tra cui x64, x86 e ARM.
- **Strumenti da riga di comando:**  Include strumenti da riga di comando di facile utilizzo che possono essere utilizzati per lo sviluppo locale e per l'integrazione continua.
- **Distribuzione flessibile:** È possibile includere .NET Core nell'app o installarlo side-by-Side (installazioni a livello di utente o a livello di sistema). Può essere usato con i [contenitori Docker](docker/introduction.md).

## <a name="languages"></a>Linguaggi

I linguaggi [C#](../csharp/index.yml), [Visual Basic](../visual-basic/index.yml)e [F #](../fsharp/index.yml) possono essere usati per scrivere applicazioni e librerie per .NET Core. Questi linguaggi possono essere usati nell'editor di testo preferito o nell'ambiente di sviluppo integrato (IDE), tra cui:

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://code.visualstudio.com/download)

L'integrazione dell'editor viene fornita, in parte, dai collaboratori dei progetti [OmniSharp](https://www.omnisharp.net/) e [Ionide](https://ionide.io) .

## <a name="apis"></a>API

.NET Core espone Framework per la compilazione di qualsiasi tipo di app:

* App cloud con [ASP.NET Core](/aspnet/core/)
* App per dispositivi mobili con [Novell](/xamarin)
* App per Internet delle cose con [System. Device. GPIO](https://docs.microsoft.com/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0)
* App client Windows con [WPF](../desktop-wpf/overview/index.md) e Windows Forms
* [Ml.NET](../machine-learning/index.yml) di Machine Learning

Sono incluse molte API che soddisfano le esigenze comuni:

- Tipi primitivi, ad esempio <xref:System.Boolean?displayProperty=nameWithType> e <xref:System.Int32?displayProperty=nameWithType> .
- Raccolte, ad esempio <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> e <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Tipi di utilità, ad esempio <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> e <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Tipi di dati, ad esempio <xref:System.Data.DataSet?displayProperty=nameWithType> , e <xref:System.Data.Entity.DbSet?displayProperty=nameWithType> .
- Tipi a prestazioni elevate, ad <xref:System.Span%601?displayProperty=nameWithType> esempio <xref:System.Numerics.Vector?displayProperty=nameWithType> [pipeline](../standard/io/pipelines.md), e.

.NET Core assicura la compatibilità con le API .NET Framework e Mono tramite l'implementazione della specifica [.NET Standard](../standard/net-standard.md).

## <a name="composition"></a>Composizione

.NET Core è costituito dalle parti seguenti:

- Il [runtime di .NET Core](https://github.com/dotnet/runtime/tree/master/src/coreclr), che fornisce un sistema di tipi, il caricamento di assembly, una Garbage Collector, l'interoperabilità nativa e altri servizi di base. Le [librerie .NET Core Framework](https://github.com/dotnet/runtime/tree/master/src/libraries) forniscono tipi di dati primitivi, tipi di composizione delle app e utilità fondamentali.
- Il [runtime di ASP.NET Core](https://github.com/dotnet/aspnetcore), che fornisce un Framework per la compilazione di app moderne basate su cloud e connesse a Internet, ad esempio app Web, app per le cose e backend per dispositivi mobili.
- Il [.NET Core SDK](https://github.com/dotnet/sdk) e i compilatori di linguaggio ([Roslyn](https://github.com/dotnet/roslyn) e [F #](https://github.com/microsoft/visualfsharp)) che consentono l'esperienza dello sviluppatore di .NET Core.
- Il [comando DotNet](./tools/dotnet.md), che viene usato per avviare le app .NET Core e i comandi dell'interfaccia della riga di comando. Seleziona e ospita il runtime, fornisce un criterio di caricamento degli assembly e avvia le app e gli strumenti.

### <a name="open-source"></a>Aprire origine

[.NET Core](about.md) è una piattaforma di sviluppo [Open Source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)per utilizzo generico. È possibile creare app .NET Core per Windows, macOS e Linux per i processori x64, x86, ARM32 e ARM64. I Framework e le API sono forniti [cloud](/aspnet/core/)per cloud [, Internet delle cose,](https://docs.microsoft.com/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0) [interfaccia utente client](../desktop-wpf/overview/index.md)e [Machine Learning](../machine-learning/index.yml).

## <a name="support"></a>Supporto

.NET Core è [supportato da Microsoft](https://dotnet.microsoft.com/platform/support/policy) in Windows, MacOS e Linux. Viene aggiornata regolarmente per la sicurezza e la qualità (il secondo martedì di ogni mese).

Le distribuzioni binarie di .NET Core da Microsoft vengono compilate e testate sui server gestiti da Microsoft in Azure e seguono le procedure di progettazione e sicurezza Microsoft.

[Red Hat supporta .NET Core](https://developers.redhat.com/topics/dotnet/) in Red Hat Enterprise Linux (RHEL). Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.

[Tizen supporta .NET Core](https://developer.tizen.org/development/training/.net-application) su piattaforme Tizen.
