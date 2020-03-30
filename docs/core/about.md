---
title: Panoramica di .NET Core
description: Informazioni sulle caratteristiche e la composizione di .NET Core e confrontarle con altre implementazioni di .NET.
ms.date: 03/26/2020
ms.openlocfilehash: c9a63ddba14cf176be529e9520027c0610cfc087
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391169"
---
# <a name="net-core-overview"></a>Panoramica di .NET Core

.NET Core ha le caratteristiche seguenti:

- **Piattaforma trasversale:** Funziona su [sistemi operativi](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md)Windows, macOS e Linux.
- **Open source:** .NET Core Framework è [open source,](https://github.com/dotnet/core)utilizzando le licenze MIT e Apache 2. .NET Core è un progetto [.NET Foundation](https://dotnetfoundation.org/).
- **Moderno:** Implementa paradigmi moderni come la programmazione asincrona, i modelli di non copia usando gli struct e la governance delle risorse per i contenitori.
- **Prestazioni:**  Offre [prestazioni elevate](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-core-3-0/) con funzionalità quali [funzioni intrinseche hardware,](https://devblogs.microsoft.com/dotnet/hardware-intrinsics-in-net-core/) [compilazione a livelli](https://github.com/dotnet/coreclr/blob/master/Documentation/design-docs/tiered-compilation.md)e>Span [\<T. ](../standard/memory-and-spans/index.md)
- **Coerente tra gli ambienti:** Esegue il codice con lo stesso comportamento su più sistemi operativi e architetture, tra cui x64, x86 e ARM.
- **Strumenti della riga di comando:**  Include strumenti da riga di comando di facile utilizzo che possono essere utilizzati per lo sviluppo locale e per l'integrazione continua.
- **Implementazione flessibile:** Puoi includere .NET Core nell'app o installarlo side-by-side (installazioni a livello di utente o di sistema). Può essere usato con i [contenitori Docker](docker/introduction.md).

## <a name="languages"></a>Languages

Per scrivere applicazioni e librerie per .NET Core è possibile utilizzare i linguaggi [di C,](../csharp/index.yml) [Visual Basic](../visual-basic/index.yml)e [F.](../fsharp/index.yml) Questi linguaggi possono essere utilizzati nell'editor di testo preferito o nell'ambiente di sviluppo integrato (IDE), tra cui:These languages can be used in your favorite text editor or Integrated Development Environment (IDE), including:

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://code.visualstudio.com/download)

L'integrazione dell'editor è fornita, in parte, dai contributori dei progetti [OmniSharp](https://www.omnisharp.net/) e [Ionide.](http://ionide.io)

## <a name="apis"></a>API

.NET Core espone i framework per la compilazione di qualsiasi tipo di app:.NET Core exposes frameworks for building any kind of app:

* App cloud con [ASP.NET Core](/aspnet/core/)
* App per dispositivi mobili con [Xamarin](/xamarin)
* App IoT con [System.Device.GPIO](https://docs.microsoft.com/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0)
* App client Windows con [WPF](../desktop-wpf/overview/index.md) e Windows Form
* ML.NET di apprendimento [automatico](../machine-learning/index.yml)

Sono incluse molte API che soddisfano le esigenze comuni:Many APIs are included that satisfy common needs:

- Tipi primitivi, <xref:System.Boolean?displayProperty=nameWithType> ad <xref:System.Int32?displayProperty=nameWithType>esempio e .
- Raccolte, ad esempio <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> e <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Tipi di utilità, ad esempio <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> e <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Tipi di dati, <xref:System.Data.DataSet?displayProperty=nameWithType> <xref:System.Data.Entity.DbSet?displayProperty=nameWithType>ad esempio , e .
- Tipi ad alte prestazioni, ad <xref:System.Span%601?displayProperty=nameWithType>esempio , <xref:System.Numerics.Vector?displayProperty=nameWithType>e Pipeline [.](../standard/io/pipelines.md)

.NET Core assicura la compatibilità con le API .NET Framework e Mono tramite l'implementazione della specifica [.NET Standard](../standard/net-standard.md).

## <a name="composition"></a>Composizione

.NET Core è costituito dalle parti seguenti:

- Il [runtime di .NET Core](https://github.com/dotnet/runtime/tree/master/src/coreclr), che fornisce un sistema di tipi, il caricamento di assembly, un Garbage Collector, l'interoperabilità nativa e altri servizi di base. Le [librerie del framework .NET Core](https://github.com/dotnet/runtime/tree/master/src/libraries) forniscono tipi di dati primitivi, tipi di composizione dell'app e utilità fondamentali.
- Il [runtime di ASP.NET Core](https://github.com/dotnet/aspnetcore), che fornisce un framework per la creazione di app moderne, basate su cloud e connesse a Internet, ad esempio app Web, app IoT e back-end per dispositivi mobili.
- L'SDK di [.NET Core](https://github.com/dotnet/sdk) e i compilatori di linguaggio ([Roslyn](https://github.com/dotnet/roslyn) e [F](https://github.com/microsoft/visualfsharp)) che consentono l'esperienza di sviluppo di .NET Core.
- Il [comando dotnet](./tools/dotnet.md), utilizzato per avviare le app .NET Core e i comandi cli. Seleziona e ospita il runtime, fornisce un criterio di caricamento dell'assembly e avvia app e strumenti.

### <a name="open-source"></a>Aprire origine

[.NET Core](about.md) è una piattaforma di sviluppo [open source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)generica. Puoi creare app .NET Core per processori Windows, macOS e Linux per x64, x86, ARM32 e ARM64. Framework e API vengono forniti per [cloud](/aspnet/core/), [IoT](https://docs.microsoft.com/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [interfaccia utente client](../desktop-wpf/overview/index.md)e machine [learning](../machine-learning/index.yml).

## <a name="support"></a>Supporto

.NET Core è [supportato da Microsoft](https://dotnet.microsoft.com/platform/support/policy) su Windows, macOS e Linux. Viene aggiornato regolarmente per la sicurezza e la qualità (il secondo martedì di ogni mese).

Le distribuzioni binarie .NET Core di Microsoft vengono create e testate su server gestiti da Microsoft in Azure e seguono le procedure di progettazione e sicurezza Microsoft.

[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL). Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.

[Tizen supporta .NET Core](https://developer.tizen.org/development/training/.net-application) su piattaforme Tizen.
