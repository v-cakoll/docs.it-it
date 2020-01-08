---
title: Glossario .NET
description: Significato di termini selezionati usati nella documentazione di .NET.
ms.date: 01/22/2019
ms.technology: dotnet-standard
ms.openlocfilehash: 21b2b0fb606333ace05b6525c9f461e6ee1709d1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338527"
---
# <a name="net-glossary"></a>Glossario .NET

Scopo principale di questo glossario è quello di chiarire il significato di acronimi e termini selezionati usati frequentemente nella documentazione di .NET senza definizioni.

## <a name="aot"></a>AOT

Compilatore Ahead Of Time.

Simile a [JIT](#jit), questo compilatore esegue anche la conversione del linguaggio [IL](#il) in codice macchina. A differenza della compilazione JIT, la compilazione AOT viene eseguita prima dell'esecuzione dell'applicazione, generalmente in un computer diverso. Dal momento che le toolchain AOT non eseguono compilazioni in fase di esecuzione, non devono ridurre al minimo il tempo impiegato per la compilazione e possono dedicare più tempo all'ottimizzazione. Il contesto di AOT è l'intera applicazione, pertanto il compilatore AOT esegue anche il collegamento tra i moduli e l'analisi dell'intero programma, di conseguenza vengono seguiti tutti i riferimenti e viene generato un unico file eseguibile.

Vedere [CoreRT](#corert) e [.NET Native](#net-native).

## <a name="aspnet"></a>ASP.NET 

Implementazione originale di ASP.NET inclusa con .NET Framework.

In alcuni casi ASP.NET è un termine generico che fa riferimento a entrambe le implementazioni di ASP.NET, inclusa ASP.NET Core. Il significato assunto dal termine in una specifica istanza è determinato dal contesto. Fare riferimento ad ASP.NET 4.x per definire che non si sta usando ASP.NET per indicare entrambe le implementazioni. 

Vedere [Documentazione di ASP.NET](/aspnet/#pivot=aspnet).

## <a name="aspnet-core"></a>ASP.NET Core

Implementazione open source, ad alte prestazioni e multi-piattaforma di ASP.NET basata su .NET Core.

Vedere [Documentazione di ASP.NET Core](/aspnet/#pivot=core).

## <a name="assembly"></a>assembly

File *DLL*/*EXE* che possono contenere una raccolta di API che possono essere chiamate da applicazioni o altri assembly.

Un assembly può includere tipi, ad esempio interfacce, classi, strutture, enumerazioni e delegati. Gli assembly presenti nella cartella *bin* di un progetto sono anche denominati *binari*. Vedere anche [libreria](#library).

## <a name="clr"></a>CLR per

Common Language Runtime.

Il significato esatto dipende dal contesto, ma questo in genere si riferisce al runtime di .NET Framework. CLR gestisce allocazione e gestione della memoria. È inoltre una macchina virtuale che non solo esegue app, ma che genera e compila codice automaticamente usando un compilatore [JIT](#jit). L'implementazione corrente di Microsoft CLR è solo Windows.

## <a name="coreclr"></a>CoreCLR

.NET Core Common Language Runtime.

Questo tipo di CLR viene creato dalla stessa base di codice di CLR. In origine, CoreCLR era il runtime di Silverlight ed è stato progettato per l'esecuzione su più piattaforme, in particolare Windows e OS X. CoreCLR è ora incluso in .NET Core e rappresenta una versione semplificata di CLR. È comunque un runtime [multipiattaforma](#cross-platform), che include ora il supporto per molte distribuzioni Linux. CoreCLR è anche una macchina virtuale con funzionalità JIT e di esecuzione del codice.

## <a name="corefx"></a>CoreFX

Libreria di classi base .NET Core (BCL)

Set di librerie che comprende gli spazi dei nomi System.* (e in modo limitato quelli Microsoft.*. La libreria di classi base è un framework generico di livello inferiore su cui si basano framework applicazione di livello superiore, ad esempio ASP.NET Core. Il codice sorgente della libreria di classi base .NET Core è incluso reperibile nel [repository CoreFX](https://github.com/dotnet/corefx). La maggior parte delle API .NET Core sono però anche disponibili in .NET Framework, di conseguenza è possibile considerare CoreFX come un fork della libreria di classi base .NET Framework.

## <a name="corert"></a>CoreRT

Runtime di .NET Core.

A differenza di CLR/CoreCLR, CoreRT non è una macchina virtuale, ovvero non include le funzionalità per generare ed eseguire codice al volo perché non include un [JIT](#jit). Include invece la [Garbage Collection](#gc) e la funzionalità per l'identificazione del tipo di runtime (RTTI) e la reflection. Tuttavia, il sistema di tipi di questo runtime è progettato in modo tale da rendere superflui i metadati per la reflection. Si ottiene pertanto una toolchain [AOT](#aot) in grado di scollegare i metadati superflui e, più importante, identificare il codice non usato dall'app. CoreRT è in fase di sviluppo.

Vedere [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md) (Introduzione a .NET Native e CoreRT).

## <a name="cross-platform"></a>multipiattaforma

La possibilità di sviluppare ed eseguire un'applicazione che può essere usata in più sistemi operativi diversi, come Linux, Windows e iOS, senza dover riscrivere in modo specifico il codice per ciascuno. Questo permette di riutilizzare il codice e la coerenza tra le applicazioni in piattaforme diverse.

## <a name="ecosystem"></a>ecosistema

Tutto il software di runtime, gli strumenti di sviluppo e le risorse della community usati per creare ed eseguire applicazioni per una determinata tecnologia.

Il termine "ecosistema .NET" è diverso da termini simili, quali "stack .NET", quando è inserito in app e librerie di terze parti. Eccone un esempio in una frase:

- "La motivazione alla base di [.NET Standard](#net-standard) è l'esigenza di creare maggiore uniformità nell'ecosistema .NET". 

## <a name="framework"></a>framework

In termini generali, una raccolta completa di API che consente di semplificare lo sviluppo e la distribuzione di applicazioni basate su una particolare tecnologia. In tal senso, ASP.NET Core e Windows Form sono esempi di framework applicazione. Vedere anche [libreria](#library).

La parola "framework" presenta un significato tecnico più specifico nei termini seguenti:

- [.NET Framework](#net-framework)
- [framework di destinazione](#target-framework)
- [TFM (moniker framework di destinazione)](#tfm)

Nella documentazione esistente il termine "framework" si riferisce talvolta a un'[implementazione di .NET](#implementation-of-net). In un articolo, ad esempio, è possibile che .NET Core venga considerato un framework. È intenzione di Microsoft chiarire il significato di questo termine nella documentazione.

## <a name="gc"></a>GC

Garbage Collector.

Il Garbage Collector è un'implementazione di un sistema di gestione automatica della memoria.  Libera infatti la memoria occupata da oggetti che non vengono più usati. 

Vedere [Garbage Collection](garbage-collection/index.md).

## <a name="il"></a>IL

Linguaggio intermedio.

Con i linguaggi .NET di livello superiore, ad esempio C#, la compilazione viene eseguita fino a un set di istruzioni indipendente dall'hardware, che viene chiamato linguaggio intermedio (IL). Tale linguaggio intermedio è noto anche come MSIL (Microsoft IL) o CIL (Common IL).

## <a name="jit"></a>JIT

Compilatore JIT.

Simile a [AOT](#aot), questo compilatore esegue la conversione del linguaggio [IL](#il) in codice macchina riconosciuto dal processore. A differenza di AOT, la compilazione JIT viene eseguita su richiesta e nello stesso computer in cui deve essere eseguito il codice. La compilazione JIT viene eseguita durante l'esecuzione dell'applicazione, di conseguenza la fase di compilazione fa parte del runtime. I compilatori JIT devono quindi bilanciare il tempo impiegato per l'ottimizzazione del tempo con i possibili risparmi ottenuti dal codice risultante. Ma dal momento che un compilatore JIT riconosce l'hardware effettivamente in uso, gli sviluppatori non devono più fornire implementazioni diverse.

## <a name="implementation-of-net"></a>implementazione di .NET

Un'implementazione di .NET include i componenti seguenti:

- Uno o più runtime. Esempi: CLR, CoreCLR, CoreRT.
- Una libreria di classi che implementa una versione di .NET Standard e può includere API aggiuntive. Esempi: libreria di classi base .NET Framework, libreria di classi base .NET Core.
- Facoltativamente, uno o più framework applicazione. Esempi: ASP.NET, Windows Forms e WPF sono inclusi in .NET Framework.
- Facoltativamente, strumenti di sviluppo. Alcuni strumenti di sviluppo sono condivisi tra più implementazioni.

Esempi di implementazioni di .NET:

- [.NET Framework](#net-framework)
- [.NET Core](#net-core)
- [Piattaforma UWP (Universal Windows Platform)](#uwp)

## <a name="library"></a>libreria

Raccolta di API che possono essere chiamate da app o altre librerie. Una libreria .NET è composta da uno o più [assembly](#assembly).

Le parole libreria e [framework](#framework) vengono spesso usate come sinonimi.

## <a name="metapackage"></a>metapacchetto

Pacchetto NuGet che non contiene una propria libreria, ma è costituito da un elenco di dipendenze. Facoltativamente, i pacchetti inclusi possono stabilire l'API per un framework di destinazione.

Vedere [Pacchetti, metapacchetti e framework](../core/packages.md)

## <a name="mono"></a>Mono

Mono è un'implementazione .NET [multipiattaforma](#cross-platform) open source che viene usata prevalentemente quando è necessario un runtime di dimensioni ridotte. Si tratta del runtime su cui si basano le applicazioni Xamarin in Android, Mac, iOS, tvOS e watchOS ed è incentrato principalmente su app che richiedono un footprint ridotto.

Supporta tutte le versioni attualmente pubblicate di .NET Standard.

In precedenza, Mono implementava le API di dimensioni maggiori di .NET Framework ed emulava alcune delle funzionalità più diffuse su Unix. Viene a volte usato per eseguire applicazioni .NET che si basano su tali funzionalità in Unix.

Mono viene in genere usato con un compilatore JIT, ma include anche un compilatore statico completo (compilazione Ahead Of Time), usato in piattaforme quali iOS.

Per altre informazioni su Mono, vedere la [documentazione Mono](https://www.mono-project.com/docs/).

## <a name="net"></a>.NET

Termine generico per riferirsi a [.NET Standard](#net-standard) e a tutti i carichi di lavoro e le [implementazioni di .NET](#implementation-of-net). Questo termine è sempre scritto in lettere maiuscole, pertanto la grafia ".Net" è errata.

Vedere [Guida alla piattaforma .NET](index.md).

## <a name="net-core"></a>.NET Core 

Implementazione open source, ad alte prestazioni e multi-piattaforma di .NET. Include Core Common Language Runtime (CoreCLR), il runtime Core AOT (CoreRT, in fase di sviluppo), la libreria di classi base Core e Core SDK.

Vedere [.NET Core](../core/index.md).

## <a name="net-core-cli"></a>Interfaccia della riga di comando di .NET Core

Toolchain multipiattaforma per lo sviluppo di applicazioni .NET Core.

Vedere [Strumenti dell'interfaccia della riga di comando di .NET Core](../core/tools/index.md).

## <a name="net-core-sdk"></a>.NET Core SDK

Set di librerie e strumenti che consente agli sviluppatori di creare applicazioni e librerie .NET Core. Include l'[interfaccia della riga di comando di .NET Core](#net-core-cli) per la creazione di app, le librerie e il runtime .NET Core per la compilazione e l'esecuzione di app e l'eseguibile dotnet (*dotnet.exe*) per l'esecuzione delle applicazioni e dei comandi dell'interfaccia della riga di comando.

Vedere [Panoramica di .NET Core SDK](../core/sdk.md).

## <a name="net-framework"></a>.NET Framework

Implementazione di .NET che viene eseguita solo in Windows. Include Common Language Runtime (CLR), la libreria di classi base e le librerie del framework applicazione, quali ASP.NET, Windows Form e WPF.

Vedere [Guida a .NET Framework](../framework/index.md).

## <a name="net-native"></a>.NET Native

Toolchain del compilatore che produce codice nativo Ahead Of Time (AOT), in contrapposizione a quello JIT.

La compilazione viene eseguita nel computer dello sviluppatore in modo analogo al funzionamento di un compilatore e un linker C++. Il codice inutilizzato viene rimosso e viene dedicato più tempo all'ottimizzazione. Il codice viene estratto dalle librerie e unito nel file eseguibile. Il risultato è un singolo modulo che rappresenta l'intera app.

Il primo framework applicazione supportato da .NET Native è stata la piattaforma UWP. Ora è supportata la compilazione di app console native per Windows, macOS e Linux.

Vedere [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md) (Introduzione a .NET Native e CoreRT).

## <a name="net-standard"></a>.NET Standard

Specifica formale delle API .NET che sono disponibili in tutte le implementazioni di .NET.

La specifica .NET Standard è talvolta indicata come libreria nella documentazione. Dal momento che una libreria include le implementazioni delle API e non solo di specifiche (interfacce), è fuorviante usare il termine "libreria" in riferimento a .NET Standard. È intenzione di Microsoft chiarire il significato di questo termine nella documentazione, ad eccezione dei casi in cui viene fatto riferimento al nome del metapacchetto .NET Standard (`NETStandard.Library`).

Vedere [.NET Standard](net-standard.md).

## <a name="ngen"></a>NGEN

Generazione di immagini native.

È possibile considerare questa tecnologia come un compilatore JIT permanente. Il codice viene in genere compilato nel computer stesso in cui viene eseguito il codice, ma la compilazione viene eseguita di solito durante l'installazione.

## <a name="package"></a>pacchetto

Un pacchetto NuGet &mdash; o semplicemente un pacchetto &mdash; è un file *ZIP* contenente uno o più assembly con lo stesso nome, unitamente a metadati aggiuntivi, quali il nome dell'autore.

Il file *ZIP* è caratterizzato dall'estensione *NUPKG* e può contenere asset, quali file *DLL* e *XML*, da usare con più framework e versioni di destinazione. Quando vengono installati in un'app o una libreria, gli asset appropriati vengono selezionati in base al framework di destinazione specificato dall'app o dalla libreria. Gli asset che definiscono l'interfaccia si trovano nella cartella *ref*, mentre quelli che definiscono l'implementazione si trovano nella cartella *lib*.

## <a name="platform"></a>piattaforma

Sistema operativo e hardware in cui viene eseguito, ad esempio Windows, macOS, Linux, iOS e Android.

Ecco alcuni esempio di utilizzo nelle frasi:

- ".NET Core è un'implementazione multipiattaforma di .NET". 
- "I profili delle librerie di classi portabili rappresentano piattaforme Microsoft, mentre .NET Standard è indipendente dalla piattaforma".

Nella documentazione di .NET si usa spesso "piattaforma .NET" per indicare un'implementazione di .NET o lo stack .NET che include tutte le implementazioni. Entrambe queste accezioni generano confusione con il significato primario (sistema operativo/hardware), di conseguenza Microsoft intende eliminarle dalla documentazione.

## <a name="runtime"></a>runtime di

Ambiente di esecuzione per un programma gestito.

Il sistema operativo è parte dell'ambiente di runtime, ma non del runtime di .NET. Ecco alcuni esempi di runtime .NET:

- Common Language Runtime (CLR)
- Core Common Language Runtime (CoreCLR)
- .NET Native (per la piattaforma UWP)
- Runtime di Mono

Nella documentazione di .NET si usa talvolta "runtime" per indicare un'implementazione di .NET. Ad esempio, nelle frasi seguenti "runtime" deve essere sostituito da "implementazione":

- "I diversi runtime .NET implementano versioni specifiche di .NET Standard".
- "Le librerie da eseguire su più runtime devono avere come destinazione questo framework" (in riferimento a .NET Standard).
- "I diversi runtime .NET implementano versioni specifiche di .NET Standard. … Ciascuna versione del runtime .NET annuncia la versione .NET Standard più recente supportata...".

Microsoft intende eliminare questa incoerenza. 

## <a name="stack"></a>stack

Set di tecnologie di programmazione che vengono usate in combinazione per compilare ed eseguire applicazioni.

Il termine "stack .NET" si riferisce a .NET Standard e a tutte le implementazioni di .NET. L'espressione "uno stack .NET" può fare riferimento a una singola implementazione di .NET. 

## <a name="target-framework"></a>framework di destinazione

Raccolta di API su cui si basa un'app o una libreria .NET.

Un'app o una libreria può essere destinata a una versione di .NET Standard (ad esempio .NET Standard 2.0), che è la specifica di un set standardizzato di API in tutte le implementazioni di .NET. Un'app o una libreria può anche essere destinata a una versione di un'implementazione specifica di .NET. In tal caso, ottiene l'accesso ad API specifiche dell'implementazione. Ad esempio, un'app destinata a Xamarin.iOS ottiene l'accesso ai wrapper di API iOS forniti da Xamarin.

Per alcuni framework di destinazione, ad esempio .NET Framework, le API disponibili vengono definite dagli assembly installati da un framework .NET in un sistema e potrebbero includere API del framework applicazione, ad esempio, ASP.NET e WinForms. Per i framework di destinazione basati su pacchetti, ad esempio .NET Standard e .NET Core, le API del framework vengono definite dai pacchetti installati nell'app o nella libreria. In tal caso, il framework di destinazione specifica in modo implicito un metapacchetto che fa riferimento a tutti i pacchetti che costituiscono complessivamente il framework.

Vedere [Framework di destinazione](frameworks.md).

## <a name="tfm"></a>Moniker framework di destinazione

Moniker framework di destinazione.

Formato di token standardizzato per specificare il framework di destinazione di un'app o di una libreria .NET. In genere, per fare riferimento ai framework di destinazione si usa un nome breve, ad esempio `net462`. Sono presenti anche moniker framework di destinazione in formato lungo (ad esempio .NETFramework,Version=4.6.2), che però non vengono in genere usati per specificare un framework di destinazione.

Vedere [Framework di destinazione](frameworks.md).

## <a name="uwp"></a>UWP

Piattaforma UWP (Universal Windows Platform).

Implementazione di .NET usata per la creazione di applicazioni Windows moderne e abilitate per il tocco e di software per Internet delle cose. È stata progettata per unificare i diversi tipi di dispositivi da specificare come destinazione, ad esempio computer, tablet, phablet, telefoni e anche Xbox. La piattaforma UWP offre molti servizi, ad esempio un App Store centralizzato, un ambiente di esecuzione (AppContainer) e un set di API di Windows da usare invece di Win32 (WinRT). Le app possono essere scritte C++in C#,, Visual Basic e JavaScript. Quando si C# usano e Visual Basic, le API .NET vengono fornite da .NET Core.

## <a name="see-also"></a>Vedere anche

- [Guida di .NET](index.md)
- [Guida a .NET Framework](../framework/index.md)
- [.NET Core](../core/index.md)
- [Panoramica di ASP.NET](/aspnet/index#pivot=aspnet)
- [Panoramica di ASP.NET Core](/aspnet/index#pivot=core)
