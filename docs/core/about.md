---
title: Informazioni su .NET Core
description: Informazioni su .NET Core.
ms.date: 09/17/2019
ms.openlocfilehash: 22530e861f6a13a6930b2fb35c91b4f7a95a17c7
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801957"
---
# <a name="about-net-core"></a>Informazioni su .NET Core

.NET Core ha le caratteristiche seguenti:

- **Multipiattaforma:** Viene eseguito nei [sistemi operativi](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md)Windows, MacOS e Linux.
- **Coerenza in tutte le architetture:** esegue il codice con lo stesso comportamento in molteplici architetture, tra cui x64, x86 e ARM.
- **Strumenti da riga di comando:** include strumenti da riga di comando facili da usare per lo sviluppo locale e in scenari di integrazione continua.
- **Distribuzione flessibile:** Può essere incluso nell'app o installato side-by-Side (installazioni a livello di utente o a livello di sistema). Può essere usato con i [contenitori Docker](docker/introduction.md).
- **Compatibile:** .NET Core è compatibile con .NET Framework, Novell e mono, tramite [.NET standard](../standard/net-standard.md).
- **Open source:** la piattaforma .NET Core è open source e usa le licenze MIT e Apache 2. .NET Core è un progetto [.NET Foundation](https://dotnetfoundation.org/).
- **Supportato da Microsoft:** .NET Core è supportato da Microsoft, in base al [Supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy).

## <a name="languages"></a>Linguaggi

È possibile usare i linguaggi C#, Visual Basic e F# per scrivere librerie e applicazioni per .NET Core. Questi linguaggi possono essere usati nell'editor di testo preferito o nell'ambiente di sviluppo integrato (IDE), tra cui:

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)
- Testo sublime
- Vim

Questa integrazione viene fornita, in parte, dai collaboratori dei progetti [OmniSharp](https://www.omnisharp.net/) e [Ionide](http://ionide.io) .

## <a name="apis"></a>APIs

.NET Core espone API per molti scenari, tra cui i seguenti:

- Tipi primitivi, come <xref:System.Boolean?displayProperty=nameWithType> e <xref:System.Int32?displayProperty=nameWithType>.
- Raccolte, ad esempio <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> e <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Tipi di utilità, ad esempio <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> e <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Tipi di dati, ad esempio <xref:System.Data.DataSet?displayProperty=nameWithType> e [DbSet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/).
- Tipi a prestazioni elevate, ad esempio <xref:System.Numerics.Vector?displayProperty=nameWithType> e [pipeline](../standard/io/pipelines.md).

.NET Core assicura la compatibilità con le API .NET Framework e Mono tramite l'implementazione della specifica [.NET Standard](../standard/net-standard.md).

## <a name="frameworks"></a>Framework

.NET Core è la base di molteplici framework:

- [ASP.NET Core](/aspnet/core/)
- [Piattaforma UWP (Universal Windows Platform) di Windows 10](https://developer.microsoft.com/windows)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>composizione

.NET Core è costituito dalle parti seguenti:

- Il [runtime di .NET Core](https://github.com/dotnet/runtime/tree/master/src/coreclr), che fornisce un sistema di tipi, il caricamento di assembly, una Garbage Collector, l'interoperabilità nativa e altri servizi di base. Le [librerie .NET Core Framework](https://github.com/dotnet/runtime/tree/master/src/libraries) forniscono tipi di dati primitivi, tipi di composizione delle app e utilità fondamentali.
- Il [runtime di ASP.NET](https://github.com/aspnet/home), che fornisce un Framework per la compilazione di moderne applicazioni connesse a Internet basate su cloud, ad esempio app Web, app per le cose e backend per dispositivi mobili.
- Gli [strumenti dell'interfaccia della riga di comando di .NET Core](https://github.com/dotnet/cli) e compilatori di linguaggio ([Roslyn](https://github.com/dotnet/roslyn) e [F#](https://github.com/microsoft/visualfsharp)) che rendono possibile l'esperienza di sviluppo .NET Core.
- [dotnet tool](https://github.com/dotnet/core-setup), usato per avviare le app e gli strumenti dell'interfaccia della riga di comando di .NET Core. Seleziona il runtime e ospita il runtime, fornisce un criterio di caricamento degli assembly e avvia le app e gli strumenti.

Questi componenti sono distribuiti nei modi seguenti:

- [Runtime di .NET Core](https://dotnet.microsoft.com/download): include il runtime e le librerie del framework .NET Core.
- [Runtime di ASP.NET Core](https://dotnet.microsoft.com/download): include il runtime e le librerie dei framework ASP.NET Core e .NET Core.
- [.NET Core SDK](https://dotnet.microsoft.com/download): include gli strumenti dell'interfaccia della riga di comando di .NET, il runtime di ASP.NET Core, nonché il runtime e il framework .NET Core.

### <a name="open-source"></a>Open source

[.NET Core](https://github.com/dotnet/core) è open source ([licenza MIT](https://github.com/dotnet/core/blob/master/LICENSE.TXT)) ed è stato offerto alla [.NET Foundation](https://dotnetfoundation.org) da Microsoft nel 2014. È ora uno dei progetti .NET Foundation più attivi. Può essere usato da singoli utenti e società, anche per scopi personali, accademici o commerciali. Più aziende usano .NET Core come parte di app, strumenti, nuove piattaforme e servizi di hosting. Alcune di queste società apportano contributi significativi a .NET Core su GitHub e forniscono indicazioni sull'uso del prodotto come parte del gruppo [.NET Foundation Technical Steering Group](https://dotnetfoundation.org/blog/tsg-welcome).

### <a name="designed-for-adaptability"></a>Progettato per l'adattabilità

.NET Core è stato progettato come prodotto molto simile ma univoco rispetto ad altri prodotti .NET. È stato progettato per consentire un'ampia adattabilità a nuove piattaforme e carichi di lavoro e dispone di diverse porte del sistema operativo e della CPU disponibili, che possono essere trasferite a molti altri.

Il prodotto è suddiviso in più parti, in modo che queste possano essere adattate a nuove piattaforme in momenti diversi. Il runtime e le librerie di base specifiche della piattaforma devono essere trasferite come elementi univoci. Le librerie indipendenti dalla piattaforma dovrebbero funzionare in modo indipendente su tutte le piattaforme, per costruzione. Esiste una distorsione del progetto per la riduzione delle implementazioni specifiche della piattaforma per aumentare l'efficienza dello sviluppatore, preferendo il codice indipendente C# dalla piattaforma ogni volta che un algoritmo o un'API può essere implementata completamente o in parte in questo modo.

In genere, viene richiesto come implementare .NET Core al fine di supportare più sistemi operativi e se sono disponibili implementazioni separate o viene usata [la compilazione condizionale](https://en.wikipedia.org/wiki/Conditional_compilation). Sono disponibili entrambe le opzioni, con una forte preferenza per la compilazione condizionale.

Nel grafico seguente è possibile vedere che la maggior parte delle [librerie .NET Core](https://github.com/dotnet/runtime/tree/master/src/libraries) è un codice indipendente dalla piattaforma condiviso tra tutte le piattaforme. Il codice indipendente dalla piattaforma può essere implementato come assembly portabile individuale usato su tutte le piattaforme.

![CoreFX: righe di codice per ogni piattaforma](../images/corefx-platforms-loc.png)

Le implementazioni Windows e Unix hanno dimensioni simili. Windows ha un'implementazione più ampia poiché le librerie .NET Core implementano alcune funzionalità solo di Windows, ad esempio [Microsoft. Win32. Registry](https://github.com/dotnet/runtime/tree/master/src/libraries/Microsoft.Win32.Registry) , ma non implementano ancora molti concetti solo UNIX. Si noterà anche che la maggior parte delle implementazioni di Linux e macOS sono condivise tra un'implementazione di UNIX, mentre le implementazioni specifiche di Linux e macOS hanno dimensioni simili.

In .NET Core è disponibile una combinazione di librerie specifiche della piattaforma e indipendenti dalla piattaforma. È possibile visualizzarne le caratteristiche in alcuni esempi:

- [CoreCLR](https://github.com/dotnet/runtime/tree/master/src/coreclr) è specifica della piattaforma. È basata su sottosistemi del sistema operativo, quali ad esempio lo strumento di gestione della memoria e l'utilità di pianificazione thread.
- [System.IO](https://github.com/dotnet/runtime/tree/master/src/libraries/System.IO) e [System.Security.Cryptography.Algorithms](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Security.Cryptography.Algorithms) sono specifiche della piattaforma, dato che le API di archiviazione e crittografia sono diverse in ogni sistema operativo.
- [System.Collections](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Collections) e [System.Linq](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Linq) sono indipendenti dalla piattaforma, dato che creano e operano su strutture di dati.

## <a name="comparisons-to-other-net-implementations"></a>Confronto con altre implementazioni di .NET

È probabilmente più semplice comprendere le dimensioni e la forma di .NET Core confrontandolo con le implementazioni di .NET esistenti.

### <a name="comparison-with-net-framework"></a>Confronto con .NET Framework

La piattaforma .NET è stata annunciata per la prima volta da Microsoft nel 2000 e da quel momento ha conosciuto una notevole evoluzione. .NET Framework è stata l'implementazione di .NET principale prodotta da Microsoft durante questo periodo di quasi due decenni.

Differenze principali tra .NET Core e .NET Framework:

- **App-models** --. NET Core non supporta tutti i modelli di app .NET Framework. In particolare non supporta Web Form ASP.NET e ASP.NET MVC, ma supporta ASP.NET Core MVC. A partire da .NET Core 3,0, .NET Core supporta anche WPF e Windows Forms solo in Windows.
- **API**: .NET Core contiene un ampio sottoinsieme della libreria di classi base di .NET Framework, con caratteristiche diverse. I nomi degli assembly sono ad esempio diversi e i membri esposti sui tipi sono diversi nei casi principali. In alcuni casi, queste differenze richiedono modifiche all'origine della porta per .NET Core. Per ulteriori informazioni, vedere [.NET Portability Analyzer](../standard/analyzers/portability-analyzer.md). .NET Core implementa la specifica API [.NET Standard](../standard/net-standard.md).
- **Sottosistemi**: .NET Core implementa un sottoinsieme dei sottosistemi di .NET Framework, al fine di ottenere un'implementazione più semplice e un modello di programmazione. Ad esempio, la sicurezza dall'accesso di codice (CAS) non è supportata, mentre la reflection è supportata.
- **Piattaforme**: .NET Framework supporta Windows e Windows Server, mentre .NET Core supporta anche macOS e Linux.
- **Open Source**: .NET Core è open source, mentre in [.NET Framework è open source un sottoinsieme di sola lettura](https://github.com/microsoft/referencesource).

.NET Core è univoco e presenta differenze significative rispetto alla .NET Framework e ad altre implementazioni di .NET, ma è semplice condividere il codice tra queste implementazioni, usando le tecniche di condivisione di origine o binaria.

Poiché .NET Core supporta l'installazione side-by-side e il relativo runtime è completamente indipendente da .NET Framework, può essere installato nei computer in cui è presente .NET Framework senza alcun problema.

### <a name="comparison-with-mono"></a>Confronto con Mono

[Mono](https://www.mono-project.com/) è l'implementazione originale multipiattaforma di .NET. È stata avviata come alternativa [Open Source](https://github.com/mono/mono) per la .NET Framework e la transizione alla destinazione dei dispositivi mobili come dispositivi iOS e Android sono diventati molto diffusi. Può essere considerato un duplicato della community di .NET Framework. Il team di progetto di mono si basava sugli [standard .NET](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) aperti, in particolare ECMA 335, pubblicati da Microsoft per fornire un'implementazione compatibile.

Le differenze principali tra .NET Core e Mono sono:

- **Modelli di app** : mono supporta un sottoinsieme dei modelli di app .NET Framework (ad esempio, Windows Forms) e altri per lo sviluppo di app per dispositivi mobili (ad esempio, [Novell. iOS](https://www.xamarin.com/platform)) attraverso il prodotto Novell. .NET Core non supporta Novell.
- **API**: Mono supporta un [ampio sottoinsieme](http://docs.go-mono.com/?link=root%3a%2fclasslib) delle API di .NET Framework e usa gli stessi nomi di assembly e le stesse caratteristiche.
- **Piattaforme**: Mono supporta molte piattaforme e CPU.
- **Open source**: Mono e .NET Core usano entrambi la licenza MIT e sono progetti di .NET Foundation.
- **Obiettivo**: l'obiettivo principale di Mono negli ultimi anni sono le piattaforme per dispositivi mobili, mentre quello di .NET Core sono i carichi di lavoro cloud e desktop.

## <a name="the-future"></a>il futuro

È stato annunciato che .NET 5 sarà la versione successiva di .NET Core e rappresenterà un'unificazione della piattaforma. Il progetto mira a migliorare .NET in pochi modi:

- Produrre un singolo Framework e Runtime .NET che può essere usato ovunque e con comportamenti di runtime uniformi ed esperienze di sviluppo.
- Espandi le funzionalità di .NET sfruttando il meglio di .NET Core, .NET Framework, Novell e mono.
- Crea il prodotto da un'unica base di codice che gli sviluppatori (Microsoft e la community) possono lavorare ed espandere insieme e migliorare tutti gli scenari.

Per ulteriori informazioni su ciò che viene pianificato per .NET 5, vedere [Introduzione a .NET 5](https://devblogs.microsoft.com/dotnet/introducing-net-5/).
