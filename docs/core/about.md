---
title: Informazioni su .NET Core
description: Informazioni su .NET Core.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.openlocfilehash: 93619fce58a3b3aa94e6c14fc7cfeb1b0bf48272
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126978"
---
# <a name="about-net-core"></a>Informazioni su .NET Core

.NET Core ha le caratteristiche seguenti:

- **Multipiattaforma:** viene eseguito in [sistemi operativi](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) Windows, macOS e Linux.
- **Coerenza in tutte le architetture:** esegue il codice con lo stesso comportamento in molteplici architetture, tra cui x64, x86 e ARM.
- **Strumenti da riga di comando:** include strumenti da riga di comando facili da usare per lo sviluppo locale e in scenari di integrazione continua.
- **Distribuzione flessibile:** può essere incluso nell'app o installato side-by-side a livello di computer o di utente. Può essere usato con i [contenitori Docker](docker/index.md).
- **Compatibile:** .NET Core è compatibile con .NET Framework, Xamarin e Mono tramite [.NET Standard](../standard/net-standard.md).
- **Open source:** la piattaforma .NET Core è open source e usa le licenze MIT e Apache 2. .NET Core è un progetto [.NET Foundation](https://dotnetfoundation.org/).
- **Supportato da Microsoft:** .NET Core è supportato da Microsoft, in base al [Supporto di .NET Core](https://www.microsoft.com/net/core/support/).

## <a name="languages"></a>Linguaggi

È possibile usare i linguaggi C#, Visual Basic e F# per scrivere librerie e applicazioni per .NET Core. Questi linguaggi sono o possono essere integrati negli editor di testo e ambienti di sviluppo integrati preferiti, tra cui [Visual Studio](https://visualstudio.microsoft.com/vs/), [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp), Sublime Text e Vim. Questa integrazione è resa in parte possibile dai progetti [OmniSharp](https://www.omnisharp.net/) e [Ionide](http://ionide.io).

## <a name="apis"></a>API

.NET Core espone API per molti scenari, tra cui i seguenti:

- Tipi primitivi, ad esempio [bool](../csharp/language-reference/keywords/bool.md) e [int](../csharp/language-reference/keywords/int.md).
- Raccolte, ad esempio <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> e <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Tipi di utilità, ad esempio <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> e <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Tipi di dati, ad esempio <xref:System.Data.DataSet?displayProperty=nameWithType> e [DbSet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/).
- Tipi con prestazioni elevate, ad esempio <xref:System.Numerics.Vector?displayProperty=nameWithType> e [Pipelines](https://blogs.msdn.microsoft.com/dotnet/2018/07/09/system-io-pipelines-high-performance-io-in-net/).

.NET Core assicura la compatibilità con le API .NET Framework e Mono tramite l'implementazione della specifica [.NET Standard](../standard/net-standard.md).

## <a name="frameworks"></a>Framework

.NET Core è la base di molteplici framework:

- [ASP.NET Core](/aspnet/core/)
- [Piattaforma UWP (Universal Windows Platform) di Windows 10](https://developer.microsoft.com/windows)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>Composizione

.NET Core è costituito dalle parti seguenti:

- Il [runtime di .NET Core](https://github.com/dotnet/coreclr) che offre un sistema di tipi, il caricamento di assembly, un Garbage Collector, interoperabilità nativa e altri servizi di base. [Librerie del framework .NET Core](https://github.com/dotnet/corefx) con tipi di dati primitivi, tipi di composizione app e utilità fondamentali.
- Il [runtime di ASP.NET](https://github.com/aspnet/home) che offre un framework per la compilazione di moderne applicazioni connesse a Internet e basate sul cloud, ad esempio app Web, app IoT e back-end per dispositivi mobili.
- Gli [strumenti dell'interfaccia della riga di comando di .NET Core](https://github.com/dotnet/cli) e compilatori di linguaggio ([Roslyn](https://github.com/dotnet/roslyn) e [F#](https://github.com/microsoft/visualfsharp)) che rendono possibile l'esperienza di sviluppo .NET Core.
- [dotnet tool](https://github.com/dotnet/core-setup), usato per avviare le app e gli strumenti dell'interfaccia della riga di comando di .NET Core. Consente di selezionare il runtime e di ospitarlo, offre criteri di caricamento di assembly e avvia app e strumenti.

Questi componenti sono distribuiti nei modi seguenti:

- [Runtime di .NET Core](https://www.microsoft.com/net/download/dotnet-core/2.1): include il runtime e le librerie del framework .NET Core.
- [Runtime di ASP.NET Core](https://www.microsoft.com/net/download/dotnet-core/2.1): include il runtime e le librerie dei framework ASP.NET Core e .NET Core.
- [.NET Core SDK](https://www.microsoft.com/net/download/dotnet-core/2.1): include gli strumenti dell'interfaccia della riga di comando di .NET, il runtime di ASP.NET Core, nonché il runtime e il framework .NET Core.

### <a name="open-source"></a>Open source

[.NET Core](https://github.com/dotnet/core) è open source ([licenza MIT](https://github.com/dotnet/core/blob/master/LICENSE.TXT)) ed è stato offerto alla [.NET Foundation](https://dotnetfoundation.org) da Microsoft nel 2014. Attualmente è uno dei progetti .NET Foundation più attivi. Può essere adottato liberamente da singoli utenti e società, anche a scopo commerciale, accademico o personale. Numerose società usano .NET Core come parte di app, strumenti, nuove piattaforme e servizi di hosting. Alcune di queste società apportano contributi significativi a .NET Core su GitHub e forniscono indicazioni sull'uso del prodotto come parte del gruppo [.NET Foundation Technical Steering Group](https://dotnetfoundation.org/blog/tsg-welcome).

### <a name="designed-for-adaptability"></a>Progettato per l'adattabilità

.NET Core è stato progettato come prodotto molto simile, ma allo stesso tempo unico rispetto ad altri prodotti .NET. È stato progettato per consentire un'ampia adattabilità alle nuove piattaforme e ai nuovi carichi di lavoro. Ha diverse porte del sistema operativo e della CPU disponibili e può essere trasferito a molte altre.

Il prodotto è suddiviso in più parti, in modo che queste possano essere adattate a nuove piattaforme in momenti diversi. Il runtime e le librerie di base specifiche della piattaforma devono essere trasferite come elementi univoci. Le librerie indipendenti dalla piattaforma dovrebbero funzionare in modo indipendente su tutte le piattaforme, per costruzione. Esiste una propensione del progetto alla riduzione delle implementazioni specifiche della piattaforma al fine di aumentare l'efficienza dello sviluppatore, preferendo il codice C# indipendente dalla piattaforma ogni volta che un algoritmo o un'API può essere implementata completamente o in parte in questo modo.

In genere, viene richiesto come implementare .NET Core al fine di supportare più sistemi operativi e se sono disponibili implementazioni separate o viene usata [la compilazione condizionale](https://en.wikipedia.org/wiki/Conditional_compilation). Sono disponibili entrambe le opzioni, con una forte preferenza per la compilazione condizionale.

Nel grafico seguente si può notare che la maggior parte del codice [CoreFX](https://github.com/dotnet/corefx) è indipendente dalla piattaforma ed è condiviso tra tutte le piattaforme. Il codice indipendente dalla piattaforma può essere implementato come assembly portabile individuale usato su tutte le piattaforme.

![CoreFX: righe di codice per ogni piattaforma](../images/corefx-platforms-loc.png)

Le implementazioni Windows e Unix hanno dimensioni simili. Windows ha un'implementazione più vasta poiché CoreFX implementa alcune funzionalità esclusive di Windows, ad esempio [Microsoft.Win32.Registry](https://github.com/dotnet/corefx/tree/master/src/Microsoft.Win32.Registry), ma non implementa ancora molti concetti esclusivi di Unix. Si può inoltre notare che la maggior parte delle implementazioni di Linux e macOS sono condivise con un'implementazione di Unix, mentre le implementazioni specifiche di Linux e macOS sono analoghe nella dimensione.

In .NET Core è disponibile una combinazione di librerie specifiche della piattaforma e indipendenti dalla piattaforma. È possibile visualizzarne le caratteristiche in alcuni esempi:

- [CoreCLR](https://github.com/dotnet/coreclr) è specifica della piattaforma. È basata su sottosistemi del sistema operativo, quali ad esempio lo strumento di gestione della memoria e l'utilità di pianificazione thread.
- [System.IO](https://github.com/dotnet/corefx/tree/master/src/System.IO) e [System.Security.Cryptography.Algorithms](https://github.com/dotnet/corefx/tree/master/src/System.Security.Cryptography.Algorithms) sono specifiche della piattaforma, dato che le API di archiviazione e crittografia sono diverse in ogni sistema operativo.
- [System.Collections](https://github.com/dotnet/corefx/tree/master/src/System.Collections) e [System.Linq](https://github.com/dotnet/corefx/tree/master/src/System.Linq) sono indipendenti dalla piattaforma, dato che creano e operano su strutture di dati.

## <a name="comparisons-to-other-net-implementations"></a>Confronto con altre implementazioni di .NET

Per semplificare la comprensione dell'importanza di .NET Core, può essere utile un confronto con altre implementazioni di .NET esistenti.

### <a name="comparison-with-net-framework"></a>Confronto con .NET Framework

La piattaforma .NET è stata annunciata per la prima volta da Microsoft nel 2000 e da quel momento ha conosciuto una notevole evoluzione. .NET Framework è stata l'implementazione di .NET principale prodotta da Microsoft durante questo periodo di quasi due decenni.

Differenze principali tra .NET Core e .NET Framework:

- **Modelli app**: .NET Core non supporta tutti i modelli app .NET Framework. In particolare, non supporta Web Form ASP.NET e MVC. È stato annunciato che [.NET Core 3 supporterà WPF e Windows Forms](https://blogs.msdn.microsoft.com/dotnet/2018/05/07/net-core-3-and-support-for-windows-desktop-applications/).
- **API**: .NET Core contiene un ampio sottoinsieme della libreria di classi base di .NET Framework, con caratteristiche diverse. I nomi degli assembly sono ad esempio diversi e i membri esposti sui tipi sono diversi nei casi principali. A causa di queste differenze, per trasferire l'origine in .NET Core è necessario, in alcuni casi, apportare modifiche (vedere [microsoft/dotnet-apiport](https://github.com/microsoft/dotnet-apiport)). .NET Core implementa la specifica API [.NET Standard](../standard/net-standard.md).
- **Sottosistemi**: .NET Core implementa un sottoinsieme dei sottosistemi di .NET Framework, al fine di ottenere un'implementazione più semplice e un modello di programmazione. Ad esempio, la sicurezza dall'accesso di codice non è supportata, mentre la reflection lo è.
- **Piattaforme**: .NET Framework supporta Windows e Windows Server, mentre .NET Core supporta anche macOS e Linux.
- **Open Source**: .NET Core è open source, mentre in [.NET Framework è open source un sottoinsieme di sola lettura](https://github.com/microsoft/referencesource).

Sebbene .NET Core sia unico e presenti differenze significative rispetto a .NET Framework e ad altre implementazioni .NET, la condivisione del codice tra queste implementazioni risulta molto semplice tramite l'uso di tecniche di condivisione del codice sorgente o binario.

### <a name="comparison-with-mono"></a>Confronto con Mono

[Mono](https://www.mono-project.com/) è la multipiattaforma originale e [open source](https://github.com/mono/mono) dell'implementazione .NET, rilasciata nel 2004. Può essere considerato un duplicato della community di .NET Framework. Il team di progetto di Mono si basava sugli [standard .NET](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) open source (in particolare ECMA 335) pubblicati da Microsoft per fornire un'implementazione compatibile.

Le differenze principali tra .NET Core e Mono sono:

- **Modelli di app**: Mono supporta un sottoinsieme dei modelli di app di .NET Framework (ad esempio, Windows Form) e alcuni modelli aggiuntivi (ad esempio, [Xamarin.IOS](https://www.xamarin.com/platform)) attraverso il prodotto Xamarin. .NET Core non li supporta.
- **API**: Mono supporta un [ampio sottoinsieme](http://docs.go-mono.com/?link=root%3a%2fclasslib) delle API di .NET Framework e usa gli stessi nomi di assembly e le stesse caratteristiche.
- **Piattaforme**: Mono supporta molte piattaforme e CPU.
- **Open source**: Mono e .NET Core usano entrambi la licenza MIT e sono progetti di .NET Foundation.
- **Obiettivo**: l'obiettivo principale di Mono negli ultimi anni sono le piattaforme per dispositivi mobili, mentre quello di .NET Core sono i carichi di lavoro cloud e desktop.
