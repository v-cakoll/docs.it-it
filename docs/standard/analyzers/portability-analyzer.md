---
title: .NET Portability Analyzer | .NET
description: Informazioni su come usare lo strumento .NET Portability Analyzer per valutare la portabilità del codice tra le diverse implementazioni di .NET, inclusi .NET Core, .NET Standard, UWP e Xamarin.
ms.date: 09/13/2019
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: d2a9551565e9ef0a2ed76960c869829fc2e86a1f
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903610"
---
# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

È possibile fare in modo che le librerie in uso supportino architetture multi-piattaforma Si vuole vedere quanto lavoro è necessario per l'esecuzione dell'applicazione .NET Framework in .NET Core? [.NET Portability Analyzer](https://github.com/microsoft/dotnet-apiport) è uno strumento che analizza gli assembly e fornisce un report dettagliato sulle API .NET mancanti affinché le applicazioni o le librerie siano portabili sulle piattaforme .NET di destinazione specificate. Portability Analyzer è offerto come [estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), che analizza un assembly per ogni progetto e come [app console ApiPort](https://aka.ms/apiportdownload), che analizza gli assembly in base ai file o alla directory specificati.

Dopo aver convertito il progetto in modo che sia destinato alla nuova piattaforma, ad esempio .NET Core, è possibile usare lo [strumento Analizzatore di API](api-analyzer.md) basato su Roslyn per identificare le API che generano <xref:System.PlatformNotSupportedException> eccezioni e altri problemi di compatibilità.

## <a name="common-targets"></a>Destinazioni comuni

- [.NET Core](../../core/index.yml): ha una progettazione modulare, supporta l'installazione side-by-side e ha come destinazione scenari multipiattaforma. L'installazione side-by-Side consente di adottare le nuove versioni di .NET Core senza compromettere altre app. Se l'obiettivo è quello di trasferire l'app in .NET Core e supportare più piattaforme, questa è la destinazione consigliata.
- . [NET standard](../net-standard.md): include le API .NET standard disponibili in tutte le implementazioni di .NET. Se l'obiettivo è fare in modo che la libreria venga eseguita su tutte le piattaforme supportate da .NET, questa è la destinazione consigliata.
- [ASP.NET Core](/aspnet/core): un framework Web moderno basato su .NET Core. Se l'obiettivo è di convertire l'app Web in .NET Core per supportare più piattaforme, questa è la destinazione consigliata.
- .NET Core + [estensioni della piattaforma](../../core/porting/windows-compat-pack.md): include le API di .NET Core, oltre a Windows Compatibility Pack, che offre molte delle .NET Framework tecnologie disponibili. Questa è una destinazione consigliata per la conversione dell'app da .NET Framework a .NET Core in Windows.
- .NET Standard + [estensioni della piattaforma](../../core/porting/windows-compat-pack.md): include le API .NET standard, oltre a Windows Compatibility Pack, che offre molte delle tecnologie .NET Framework disponibili. Questa è una destinazione consigliata per la conversione della libreria da .NET Framework a .NET Core in Windows.

## <a name="how-to-use-the-net-portability-analyzer"></a>Come usare .NET Portability Analyzer

Per iniziare a usare .NET Portability Analyzer in Visual Studio, è prima necessario scaricare l'estensione da [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) e installarla. Funziona in Visual Studio 2017 e versioni successive. È possibile configurarlo in Visual Studio tramite **analizza**  >  **le impostazioni di Portability Analyzer** e selezionare le piattaforme di destinazione, ovvero le piattaforme .NET e le versioni di cui si vuole valutare i gap di portabilità rispetto alla piattaforma/versione con cui viene compilato l'assembly corrente.

![Screenshot di Portability Analyzer.](./media/portability-analyzer/portability-screenshot.png)

È anche possibile usare l'applicazione console ApiPort, scaricandola dal [repository ApiPort](https://aka.ms/apiportdownload). È possibile usare l'opzione di comando `listTargets` per visualizzare l'elenco di destinazioni disponibili e quindi selezionare le piattaforme di destinazione specificando l'opzione di comando `-t` o `--target`.

### <a name="solution-wide-view"></a>Visualizzazione a livello di soluzione

Un passaggio utile per l'analisi di una soluzione con molti progetti consiste nel visualizzare le dipendenze per comprendere quale subset di assembly dipende da cosa. La raccomandazione generale consiste nell'applicare i risultati dell'analisi in un approccio dal basso verso l'alto a partire dai nodi foglia in un grafico delle dipendenze.

Per recuperare questo problema, è possibile eseguire il comando seguente:

```
ApiPort.exe analyze -r DGML -f [directory or file]
```

Il risultato sarà simile al seguente quando viene aperto in Visual Studio:

![Screenshot dell'analisi DGML.](./media/portability-analyzer/dgml-example.png)

### <a name="analyze-portability"></a>Analizzare la portabilità
Per analizzare l'intero progetto in Visual Studio, fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionare **Analyze Assembly Portability** (Analizza portabilità dell'assembly). In caso contrario, accedere al menu **Analizza** e selezionare **Analyze Assembly Portability** (Analizza portabilità assembly). Da qui selezionare il file eseguibile o la DLL del progetto.

![Screenshot di Portability Analyzer da Esplora soluzioni.](./media/portability-analyzer/portability-solution-explorer.png)

È anche possibile usare l'[app console ApiPort](https://aka.ms/apiportdownload).

- Digitare il comando seguente per analizzare la directory corrente: `ApiPort.exe analyze -f .`
- Per analizzare un elenco specifico di file con estensione dll, digitare il comando seguente: `ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`
- Per altre informazioni, eseguire il comando `ApiPort.exe -?`

È consigliabile includere tutti i file con estensione exe e dll correlati disponibili che si vogliono convertire, escludendo i file da cui l'app dipende, ma di cui non si ha la proprietà e che non si è in grado di convertire. Questa operazione consentirà di ottenere il report di portabilità più pertinente possibile.

### <a name="view-and-interpret-portability-result"></a>Visualizzare e interpretare i risultati di portabilità

Nel report sono visualizzate solo le API non supportate da una piattaforma di destinazione.
Dopo aver eseguito l'analisi in Visual Studio, si vedrà comparire il collegamento al file del report sulla portabilità .NET. Se è stata usata l'[app console ApiPort](https://aka.ms/apiportdownload), il report sulla portabilità .NET è stato salvato in un file nel formato specificato. Il valore predefinito corrisponde a un file di Excel (*xlsx*) nella directory corrente.

#### <a name="portability-summary"></a>Riepilogo della portabilità

![Screenshot del riepilogo della portabilità.](./media/portability-analyzer/api-catalog-portablility-summary.png)

La sezione Portability Summary (Riepilogo della portabilità) del report indica la percentuale di portabilità per ogni assembly incluso nell'esecuzione. Nell'esempio precedente, il 71,24% delle API .NET Framework usate nell'app `svcutil` sono disponibili in .NET Core + Estensioni della piattaforma. Se si esegue lo strumento .NET Portability Analyzer per più assembly, per ognuno di questi deve essere presente una riga nel report di riepilogo della portabilità.

#### <a name="details"></a>Dettagli

![Schermata dei dettagli relativi alla portabilità.](./media/portability-analyzer/api-catalog-portablility-details.png)

La sezione dei **Dettagli** del report elenca le API mancanti da una delle piattaforme di **destinazione**selezionate.

- Target type (Tipo di destinazione): per il tipo manca un'API da una piattaforma di destinazione
- Target member (Membro di destinazione): il metodo manca da una piattaforma di destinazione
- Assembly name (Nome dell'assembly): assembly .NET Framework in cui deve trovarsi l'API mancante.
- Ognuna delle piattaforme di destinazione selezionate è una colonna, ad esempio ".NET Core": il valore "non supportato" indica che l'API non è supportata in questa piattaforma di destinazione.
- Modifiche consigliate: l'API o la tecnologia consigliata per passare a. Attualmente, questo campo è vuoto o non aggiornato per molte API. A causa dell'elevato numero di API, abbiamo una sfida significativa per mantenerla aggiornata. Stiamo esaminando soluzioni alternative per fornire informazioni utili ai clienti.

#### <a name="missing-assemblies"></a>Assembly mancanti

![Screenshot degli assembly mancanti.](./media/portability-analyzer/api-catalog-missing-assemblies.png)

Nel report può essere presente la sezione Missing Assemblies (Assembly mancanti). Questa sezione contiene un elenco di assembly a cui fanno riferimento gli assembly analizzati e che non sono stati analizzati. Se si tratta di un assembly di cui si è proprietari, includerlo in API Portability Analyzer, in modo che sia possibile ottenere un report dettagliato di portabilità a livello di API. Se si tratta di una libreria di terze parti, verificare se è presente una versione più recente che supporta la piattaforma di destinazione e provare a eseguire il passaggio alla versione più recente. Infine, l'elenco deve includere tutti gli assembly di terze parti da cui dipende l'app che dispongono di una versione che supporta la piattaforma di destinazione.

Per altre informazioni su .NET Portability Analyzer, vedere la [documentazione di GitHub](https://github.com/Microsoft/dotnet-apiport#documentation) e il video [A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) (Panoramica rapida di .NET Portability Analyzer) in Channel 9.
