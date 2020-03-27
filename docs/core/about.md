---
title: Panoramica di .NET Core
description: Informazioni sulle caratteristiche e la composizione di .NET Core e confrontarle con altre implementazioni di .NET.
ms.date: 09/17/2019
ms.openlocfilehash: f2f97fe6a5f822266582c443fd916c270cb0cb6a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345206"
---
# <a name="net-core-overview"></a>Panoramica di .NET Core

.NET Core ha le caratteristiche seguenti:

- **Multipiattaforma:** Funziona su [sistemi operativi](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md)Windows, macOS e Linux.
- **Coerenza in tutte le architetture:** esegue il codice con lo stesso comportamento in molteplici architetture, tra cui x64, x86 e ARM.
- **Strumenti da riga di comando:** include strumenti da riga di comando facili da usare per lo sviluppo locale e in scenari di integrazione continua.
- **Implementazione flessibile:** Può essere incluso nell'app o installato side-by-side (installazioni a livello di utente o di sistema). Può essere usato con i [contenitori Docker](docker/introduction.md).
- **Compatibile:** .NET Core è compatibile con le implementazioni di .NET Framework, Xamarin e Mono tramite [.NET Standard](../standard/net-standard.md).
- **Open source:** la piattaforma .NET Core è open source e usa le licenze MIT e Apache 2. .NET Core è un progetto [.NET Foundation](https://dotnetfoundation.org/).
- **Supportato da Microsoft:** .NET Core è [supportato da Microsoft](https://dotnet.microsoft.com/platform/support/policy).

## <a name="languages"></a>Languages

È possibile usare i linguaggi C#, Visual Basic ed F# per scrivere librerie e applicazioni per .NET Core. Questi linguaggi possono essere utilizzati nell'editor di testo preferito o nell'ambiente di sviluppo integrato (IDE), tra cui:These languages can be used in your favorite text editor or Integrated Development Environment (IDE), including:

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://code.visualstudio.com/download)
- Sublime Text
- Vim

L'integrazione dell'editor è fornita, in parte, dai contributori dei progetti [OmniSharp](https://www.omnisharp.net/) e [Ionide.](http://ionide.io)

## <a name="apis"></a>API

Sono incluse molte API che soddisfano esigenze comuni, ad esempio:Many APIs are included that satisfy common needs, such as:

- Tipi primitivi, <xref:System.Boolean?displayProperty=nameWithType> ad <xref:System.Int32?displayProperty=nameWithType>esempio e .
- Raccolte, ad esempio <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> e <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Tipi di utilità, ad esempio <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> e <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Tipi di dati, ad esempio <xref:System.Data.DataSet?displayProperty=nameWithType> e [DbSet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/).
- Tipi ad alte prestazioni, ad <xref:System.Numerics.Vector?displayProperty=nameWithType> esempio e [Pipelines](../standard/io/pipelines.md).

.NET Core assicura la compatibilità con le API .NET Framework e Mono tramite l'implementazione della specifica [.NET Standard](../standard/net-standard.md).

## <a name="frameworks"></a>Framework

Più framework sono stati creati su .NET Core, tra cui:

- [ASP.NET Core](/aspnet/core/)
- [Piattaforma UWP (Universal Windows Platform)](/windows/uwp/)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>Composizione

.NET Core è costituito dalle parti seguenti:

- Il [runtime di .NET Core](https://github.com/dotnet/runtime/tree/master/src/coreclr), che fornisce un sistema di tipi, il caricamento di assembly, un Garbage Collector, l'interoperabilità nativa e altri servizi di base. Le [librerie del framework .NET Core](https://github.com/dotnet/runtime/tree/master/src/libraries) forniscono tipi di dati primitivi, tipi di composizione dell'app e utilità fondamentali.
- Il [runtime di ASP.NET Core](https://github.com/dotnet/aspnetcore), che fornisce un framework per la creazione di app moderne, basate su cloud e connesse a Internet, ad esempio app Web, app IoT e back-end per dispositivi mobili.
- L'SDK di [.NET Core](https://github.com/dotnet/sdk) e i compilatori di linguaggio ([Roslyn](https://github.com/dotnet/roslyn) e [F](https://github.com/microsoft/visualfsharp)) che consentono l'esperienza di sviluppo di .NET Core.
- Il [comando dotnet](./tools/dotnet.md), utilizzato per avviare le app .NET Core e i comandi cli. Seleziona e ospita il runtime, fornisce un criterio di caricamento dell'assembly e avvia app e strumenti.

Questi componenti sono distribuiti nei modi seguenti:

- [Runtime di .NET Core](https://dotnet.microsoft.com/download): include il runtime e le librerie del framework .NET Core.
- [ASP.NET Core Runtime:](https://dotnet.microsoft.com/download) include i runtime e le librerie del framework di ASP.NET Core e .NET Core.ASP.NET Core Runtime -- include il runtime e le librerie del framework di Core e .NET Core.
- [.NET Core SDK:](https://dotnet.microsoft.com/download) include l'interfaccia della riga di comando di .NET Core, il runtime ASP.NET Core e il runtime e il framework .NET Core.

### <a name="open-source"></a>Aprire origine

[.NET Core](https://github.com/dotnet/core) è open source ([licenza MIT](https://github.com/dotnet/core/blob/master/LICENSE.TXT)) ed è stato contribuito a [.NET Foundation](https://dotnetfoundation.org) da Microsoft nel 2014. È ora uno dei progetti .NET Foundation più attivi. Può essere utilizzato da individui e aziende, anche per scopi personali, accademici o commerciali. Più aziende utilizzano .NET Core come parte di app, strumenti, nuove piattaforme e servizi di hosting. Alcune di queste società apportano contributi significativi a .NET Core su GitHub e forniscono indicazioni sull'uso del prodotto come parte del gruppo [.NET Foundation Technical Steering Group](https://dotnetfoundation.org/blog/tsg-welcome).

### <a name="designed-for-adaptability"></a>Progettato per l'adattabilità

.NET Core è stato creato come un prodotto simile ma unico rispetto ad altri prodotti .NET. È stato progettato per consentire un'ampia adattabilità a nuove piattaforme e carichi di lavoro e dispone di diverse porte del sistema operativo e della CPU disponibili (e può essere portato a molti altri).

Il prodotto è suddiviso in più parti, in modo che queste possano essere adattate a nuove piattaforme in momenti diversi. Il runtime e le librerie di base specifiche della piattaforma devono essere trasferite come elementi univoci. Le librerie indipendenti dalla piattaforma dovrebbero funzionare in modo indipendente su tutte le piattaforme, per costruzione. C'è una distorsione del progetto verso la riduzione delle implementazioni specifiche della piattaforma per aumentare l'efficienza degli sviluppatori, preferendo il codice C' indipendente dalla piattaforma ogni volta che un algoritmo o un'API può essere implementato in full o in-part in questo modo.

In genere, viene richiesto come implementare .NET Core al fine di supportare più sistemi operativi e se sono disponibili implementazioni separate o viene usata [la compilazione condizionale](https://en.wikipedia.org/wiki/Conditional_compilation). Sono disponibili entrambe le opzioni, con una forte preferenza per la compilazione condizionale.

È possibile vedere nel grafico seguente che la maggior parte delle [librerie .NET Core](https://github.com/dotnet/runtime/tree/master/src/libraries) vengono compilate da codice indipendente dalla piattaforma condiviso tra tutte le piattaforme. Il codice indipendente dalla piattaforma può essere implementato come un singolo assembly portabile utilizzato in tutte le piattaforme.

![CoreFX: righe di codice per ogni piattaforma](../images/corefx-platforms-loc.png)

Le implementazioni di Windows e Unix hanno dimensioni simili. L'implementazione di Windows contiene alcune funzionalità solo di Windows, ad esempio [Microsoft.Win32.Registry](https://github.com/dotnet/runtime/tree/master/src/libraries/Microsoft.Win32.Registry), ma non implementa ancora molti concetti solo Unix. Gran parte delle implementazioni Linux e macOS è condivisa tra un'implementazione Unix. Le implementazioni specifiche di Linux e macOS hanno dimensioni simili.

C'è una combinazione di librerie specifiche della piattaforma e indipendenti dalla piattaforma in .NET Core.There's a mix of platform-specific and platform-neutral libraries in .NET Core. È possibile visualizzarne le caratteristiche in alcuni esempi:

- [CoreCLR](https://github.com/dotnet/runtime/tree/master/src/coreclr) è specifica della piattaforma. È basata su sottosistemi del sistema operativo, quali ad esempio lo strumento di gestione della memoria e l'utilità di pianificazione thread.
- [System.IO](https://github.com/dotnet/runtime/tree/master/src/libraries/System.IO) e [System.Security.Cryptography.Algorithms](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Security.Cryptography.Algorithms) sono specifiche della piattaforma, dato che le API di archiviazione e crittografia sono diverse in ogni sistema operativo.
- [System.Collections](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Collections) e [System.Linq](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Linq) sono indipendenti dalla piattaforma, dato che creano e operano su strutture di dati.

## <a name="comparisons-to-other-net-implementations"></a>Confronto con altre implementazioni di .NET

Per comprendere le dimensioni e la forma di .NET Core, le sezioni seguenti lo confrontano con le implementazioni .NET esistenti.

### <a name="net-core-vs-net-framework"></a>Confronto tra .NET Core e .NET Framework .NET Core

.NET è stato annunciato per la prima volta da Microsoft nel 2000 e si è evoluto da lì. .NET Framework è stata l'implementazione .NET principale prodotta da Microsoft durante questo quasi due decennio.

Le principali differenze tra .NET Core e .NET Framework sono:

- **I modelli di app** -- .NET Core non supportano tutti i modelli di app di .NET Framework. In particolare non supporta Web Form ASP.NET e ASP.NET MVC, ma supporta ASP.NET Core MVC. E a partire da .NET Core 3.0, .NET Core supporta anche WPF e Windows Form solo in Windows.
- **API**: .NET Core contiene un ampio sottoinsieme della libreria di classi base di .NET Framework, con caratteristiche diverse. I nomi degli assembly sono ad esempio diversi e i membri esposti sui tipi sono diversi nei casi principali. In some cases, these differences require changes to port source to .NET Core. Per ulteriori informazioni, vedere [Analizzatore di portabilità .NET](../standard/analyzers/portability-analyzer.md). .NET Core implementa la specifica API [.NET Standard](../standard/net-standard.md).
- **I sottosistemi** -- .NET Core implementano un sottoinsieme dei sottosistemi in .NET Framework, con l'obiettivo di un modello di implementazione e programmazione più semplice. Ad esempio, la sicurezza dall'accesso di codice (CAS) non è supportata, mentre la reflection è supportata.
- **Piattaforme** -- .NET Framework supporta Windows e Windows Server, mentre .NET Core supporta anche macOS e Linux.
- **L'open source** -- .NET Core è open source, mentre un [sottoinsieme di sola lettura di .NET Framework](https://github.com/microsoft/referencesource) è open source.

Sebbene .NET Core sia univoco e presenti differenze significative rispetto a .NET Framework e ad altre implementazioni di .NET, è semplice condividere il codice tra queste implementazioni, usando tecniche di condivisione di origine o binaria.

Poiché .NET Core supporta l'installazione side-by-side e il relativo runtime è completamente indipendente da .NET Framework, è possibile installarlo nei computer in cui è installato .NET Framework senza problemi.

### <a name="net-core-vs-mono"></a>Confronto tra .NET Core e Mono.NET Core vs.

[Mono](https://www.mono-project.com/) è l'implementazione multipiattaforma originale di .NET. E 'iniziato come un'alternativa [open-source](https://github.com/mono/mono) a .NET Framework e la transizione a dispositivi mobili di destinazione come dispositivi iOS e Android è diventato popolare. Può essere considerato come un clone della comunità di .NET Framework. Per fornire un'implementazione compatibile, il team di progetto Mono si è basato sugli [standard .NET](https://github.com/dotnet/runtime/blob/master/docs/project/dotnet-standards.md) aperti (in particolare ECMA 335) pubblicati da Microsoft.

Le principali differenze tra .NET Core e Mono sono:

- **App-models** -- Mono supporta un sottoinsieme dei modelli di app di .NET Framework (ad esempio, Windows Form) e alcuni altri per lo sviluppo per dispositivi mobili (ad esempio, [Xamarin.iOS](https://www.xamarin.com/platform)) tramite il prodotto Xamarin. .NET Core non supporta Xamarin.
- **API**: Mono supporta un [ampio sottoinsieme](http://docs.go-mono.com/?link=root%3a%2fclasslib) delle API di .NET Framework e usa gli stessi nomi di assembly e le stesse caratteristiche.
- **Piattaforme**: Mono supporta molte piattaforme e CPU.
- **Open source**: Mono e .NET Core usano entrambi la licenza MIT e sono progetti di .NET Foundation.
- **Obiettivo**: l'obiettivo principale di Mono negli ultimi anni sono le piattaforme per dispositivi mobili, mentre quello di .NET Core sono i carichi di lavoro cloud e desktop.

## <a name="support"></a>Supporto

.NET Core è [supportato da Microsoft](https://dotnet.microsoft.com/platform/support/policy) su Windows, macOS e Linux. Viene aggiornato regolarmente per la sicurezza e la qualità (secondo martedì di ogni mese).

Le distribuzioni binarie .NET Core di Microsoft vengono create e testate su server gestiti da Microsoft in Azure e seguono le procedure di progettazione e sicurezza Microsoft.

[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL). Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.

[Tizen supporta .NET Core](https://developer.tizen.org/development/training/.net-application) su piattaforme Tizen.
