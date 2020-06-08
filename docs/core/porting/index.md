---
title: Convertire da .NET Framework a .NET Core
description: Informazioni sul processo di trasferimento e sugli strumenti che possono risultare utili durante il trasferimento di un progetto .NET Framework in .NET Core.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: 74fe4519e41a07bc78a4dc346f8d1b52b5c7d092
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502769"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a>Panoramica del porting da .NET Framework a .NET Core

È possibile che si disponga di codice attualmente in esecuzione sul .NET Framework che si desidera trasferire a .NET Core. Questo articolo include:

* Panoramica del processo di porting.
* Un elenco di strumenti che possono risultare utili quando si trasferisce il codice a .NET Core.

## <a name="overview-of-the-porting-process"></a>Panoramica del processo di conversione

Il porting a .NET Core (o .NET Standard) da .NET Framework per molti progetti è relativamente semplice. Sono necessarie alcune modifiche, ma molte di esse seguono i modelli descritti di seguito. I progetti in cui il modello app è disponibile in .NET Core, ad esempio librerie, applicazioni console e applicazioni desktop, richiedono in genere piccole modifiche. I progetti che richiedono un nuovo modello di app, ad esempio il passaggio a ASP.NET Core da ASP.NET, richiedono un po' di lavoro, ma molti modelli hanno analoghi che possono essere usati durante la conversione. Questo documento consente di identificare le strategie principali che sono state usate dagli utenti per convertire correttamente le basi di codice in .NET Standard di destinazione o .NET Core e risolveranno la conversione a due livelli: a livello di soluzione e di progetto. Vedere i collegamenti nella parte inferiore per istruzioni sulle conversioni specifiche del modello app.

È consigliabile usare la procedura seguente per trasferire il progetto a .NET Core. Ognuno di questi passaggi introduce i potenziali punti per le modifiche del comportamento, quindi assicurarsi di testare adeguatamente la libreria o l'applicazione prima di continuare con i passaggi successivi. La prima procedura consiste nel preparare il progetto per un passaggio a .NET Standard o .NET Core. Se si dispone di unit test, è preferibile convertirli prima per poter continuare a testare le modifiche apportate al prodotto su cui si sta lavorando. Poiché la portabilità in .NET Core è una modifica significativa nella codebase, è consigliabile trasferire i progetti di test in modo da poter eseguire i test quando si trasferisce il codice. MSTest, xUnit e NUnit funzionano in .NET Core.

## <a name="getting-started"></a>Introduzione

Nel processo verranno usati gli strumenti seguenti:

- Visual Studio 2019
- Scarica [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md)
- _Facoltativo_ Installare [DotNet try-Convert](https://github.com/dotnet/try-convert)

## <a name="porting-a-solution"></a>Porting di una soluzione

Quando sono presenti più progetti in una soluzione, il porting può sembrare più complesso perché è necessario indirizzare i progetti in un ordine specifico. Il processo di conversione deve essere un approccio dal basso verso l'alto, in cui i progetti senza dipendenze da altri progetti nella soluzione vengono convertiti per primi e continuano l'intera soluzione.

Per identificare i progetti di ordine da migrare, è possibile usare gli strumenti seguenti:

- I [diagrammi di dipendenza in Visual Studio](/visualstudio/modeling/create-layer-diagrams-from-your-code) possono creare un grafico diretto del codice in una soluzione.
- Eseguire `msbuild _SolutionPath_ /t:GenerateRestoreGraphFile /p:RestoreGraphOutputPath=graph.dg.json` per generare un documento JSON che include l'elenco dei riferimenti al progetto.
- Eseguire [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) con l' `-r DGML` opzione per recuperare un diagramma delle dipendenze degli assembly. Per altre informazioni, vedere [qui](../../standard/analyzers/portability-analyzer.md#solution-wide-view).

Una volta fornite le informazioni sulle dipendenze, è possibile usare tali informazioni per iniziare dai nodi foglia e lavorare fino all'albero delle dipendenze applicando i passaggi nella sezione successiva.

## <a name="per-project-steps"></a>Passaggi per progetto

Quando si trasferisce il progetto a .NET Core, è consigliabile usare il processo seguente:

1. Convertire tutte le `packages.config` dipendenze nel formato [PackageReference](/nuget/consume-packages/package-references-in-project-files) con lo [strumento di conversione in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).

   Questo passaggio prevede la conversione delle dipendenze dal `packages.config` formato legacy. `packages.config`non funziona in .NET Core, quindi questa conversione è necessaria se sono presenti dipendenze del pacchetto. Richiede anche le dipendenze che vengono usate direttamente in un progetto, semplificando i passaggi successivi riducendo il numero di dipendenze che è necessario gestire.

1. Convertire il file di progetto nella nuova struttura dei file di tipo SDK. È possibile creare nuovi progetti per .NET Core e copiare i file di origine oppure provare a convertire il file di progetto esistente con uno strumento.

   .NET Core usa un [formato di file di progetto](../tools/csproj.md) semplificato (e diverso) rispetto a .NET Framework. Per continuare è necessario convertire i file di progetto in questo formato. Questo tipo di progetto consente anche di definire come destinazione .NET Framework, che a questo punto si desidera comunque utilizzare come destinazione.

   È possibile provare a trasferire le soluzioni più piccole o i singoli progetti in un'unica operazione al formato di file di progetto .NET Core con lo strumento [DotNet try-Convert](https://github.com/dotnet/try-convert) . `dotnet try-convert`non è garantito che funzioni per tutti i progetti e potrebbe causare modifiche minime al comportamento da cui dipende. Utilizzarlo come _punto di partenza_ per automatizzare gli elementi di base che possono essere automatizzati. Non si tratta di una soluzione garantita per la migrazione di un progetto, dal momento che esistono molte differenze nelle destinazioni usate dai progetti di stile SDK rispetto ai file di progetto obsoleti.

1. Ridestinare tutti i progetti che si desidera trasferire alla destinazione .NET Framework 4.7.2 o versione successiva.

   Questo passaggio garantisce che si possano usare le alternative alle API per le destinazioni specifiche di .NET Framework quando .NET Core non supporta un'API specifica.

1. Aggiornare tutte le dipendenze con la versione più recente. I progetti potrebbero utilizzare versioni precedenti di librerie che potrebbero non disporre del supporto .NET Standard. Tuttavia, le versioni successive possono supportarlo con un semplice Commuter. Questa operazione può richiedere modifiche al codice in caso di modifiche di rilievo nelle librerie.

1. Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per analizzare gli assembly e verificare se sono portabili a .NET Core.

   Lo strumento .NET Portability Analyzer analizza gli assembly compilati e genera un report. Questo report Mostra un riepilogo della portabilità di alto livello e una suddivisione di ogni API in uso non disponibile in .NET Core. Quando si usa lo strumento, inviare solo il singolo progetto che si sta convertendo per concentrarsi sulle modifiche API potenzialmente necessarie. Molte API hanno una disponibilità equivalente in .NET Core, a cui è possibile passare.

   Durante la lettura dei report generati dall'analizzatore, le informazioni importanti sono le API effettivamente in uso e non necessariamente la percentuale di supporto per la piattaforma di destinazione. Molte API hanno opzioni equivalenti in .NET Standard/Core e, di conseguenza, per comprendere gli scenari in cui la libreria o l'applicazione necessita dell'API, è possibile determinare le implicazioni per la portabilità.

   Ci sono alcuni casi in cui le API non sono equivalenti ed è necessario eseguire alcune direttive del preprocessore del compilatore (ovvero `#if NET45` ) per il caso speciale delle piattaforme. A questo punto, il progetto sarà ancora destinato .NET Framework. Per ognuno di questi casi di destinazione, è consigliabile utilizzare le condizioni note che possono essere comprese come uno scenario.  Ad esempio, il supporto di AppDomain in .NET Core è limitato, ma per lo scenario di caricamento e scaricamento degli assembly, esiste una nuova API che non è disponibile in .NET Core. Un modo comune per gestire questa operazione nel codice è simile al seguente:

   ```csharp
   #if FEATURE_APPDOMAIN_LOADING
   // Code that uses appdomains
   #elif FEATURE_ASSEMBLY_LOAD_CONTEXT
   // Code that uses assembly load context
   #else
   #error Unsupported platform
   #endif
   ```

1. Installare l' [analizzatore di API .NET](../../standard/analyzers/api-analyzer.md) nei progetti per identificare le API che generano <xref:System.PlatformNotSupportedException> alcune piattaforme e altri potenziali problemi di compatibilità.

   Questo strumento è simile a Portability Analyzer, ma invece di analizzare se il codice può essere compilato in .NET Core, analizza se si sta usando un'API in modo da generare un'eccezione in fase di <xref:System.PlatformNotSupportedException> esecuzione. Sebbene questo non sia comune se si passa da .NET Framework 4.7.2 o versione successiva, è opportuno verificare. Per altre informazioni sulle API che generano eccezioni in .NET Core, vedere [API che generano sempre eccezioni in .NET Core](../compatibility/unsupported-apis.md).

1. A questo punto, è possibile passare alla destinazione di .NET Core (in genere per le applicazioni) o .NET Standard (per le librerie).

   La scelta tra .NET Core e .NET Standard dipende in larga parte dalla posizione in cui verrà eseguito il progetto. Se si tratta di una libreria che verrà usata da altre applicazioni o distribuita tramite NuGet, la preferenza è in genere destinata a .NET Standard. Tuttavia, è possibile che siano presenti API disponibili solo in .NET Core per motivi di prestazioni o di altro genere; in tal caso, è consigliabile usare .NET Core come destinazione con potenzialmente una compilazione .NET Standard disponibile e con prestazioni o funzionalità ridotte. Impostando come destinazione .NET Standard, il progetto sarà pronto per l'esecuzione su nuove piattaforme, ad esempio webassembly. Se il progetto ha dipendenze da Framework di app specifici, ad esempio ASP.NET Core, la destinazione sarà limitata dalle dipendenze supportate dalle dipendenze.

   Se non sono presenti direttive per il preprocessore per il codice di compilazione condizionale per .NET Framework o .NET Standard, sarà semplice trovare quanto segue nel file di progetto:

   ```xml
   <TargetFramework>net472</TargetFramework>
   ```

   e passarlo al framework desiderato. Per .NET Core 3,1, questo è il seguente:

   ```xml
   <TargetFramework>netcoreapp3.1</TargetFramework>
   ```

   Tuttavia, se si tratta di una raccolta per la quale si desidera continuare a supportare le compilazioni specifiche di .NET Framework, è possibile usare più destinazioni sostituendo questa [funzionalità](../../standard/library-guidance/cross-platform-targeting.md) con quanto segue:

   ```xml
   <TargetFrameworks>net472;netstandard2.0</TargetFrameworks>
   ```

   Se si usano API specifiche di Windows, ad esempio l'accesso al registro di sistema, installare [Windows Compatibility Pack](./windows-compat-pack.md).

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Analizzare le dipendenze](third-party-deps.md) 
>  Pacchetto [NuGet pacchetto](../deploying/creating-nuget-packages.md) 
>  [Migrazione da ASP.NET a ASP.NET Core](/aspnet/core/migration/proper-to-2x)
