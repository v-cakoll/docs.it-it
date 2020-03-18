---
title: .NET Portability Analyzer | .NET
description: Informazioni su come usare lo strumento .NET Portability Analyzer per valutare la portabilità del codice tra le diverse implementazioni di .NET, inclusi .NET Core, .NET Standard, UWP e Xamarin.
ms.date: 09/13/2019
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: e0a5c791926b36fe5a35c5446471c3dcdb75cd7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "72774383"
---
# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

È possibile fare in modo che le librerie in uso supportino architetture multi-piattaforma Si desidera vedere quanto lavoro è necessario per eseguire l'applicazione .NET Framework in .NET Core? [.NET Portability Analyzer](https://github.com/microsoft/dotnet-apiport) è uno strumento che analizza gli assembly e fornisce un rapporto dettagliato sulle API .NET che risultano mancanti per le applicazioni o le librerie da portabili nelle piattaforme .NET di destinazione specificate. L'analizzatore di portabilità viene offerto come estensione di [Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), che analizza un assembly per progetto e come app [console ApiPort](https://aka.ms/apiportdownload), che analizza gli assembly in base ai file o alla directory specificati.

Dopo aver convertito il progetto per la nuova piattaforma, ad esempio .NET Core, è possibile utilizzare [lo strumento Analizzatore API](api-analyzer.md) basato su Roslyn per identificare le API che generano <xref:System.PlatformNotSupportedException> eccezioni e altri problemi di compatibilità.

## <a name="common-targets"></a>Destinazioni comuni

- [.NET Core](../../core/index.md): ha una struttura modulare, con assembly affiancato ed è destinato a scenari multi-piattaforma. La modalità affiancata consente di adottare le nuove versioni di .NET Core senza interrompere le altre applicazioni. Se l'obiettivo è di convertire l'app in una versione di .NET Core che supporta architetture multipiattaforma, questa è la destinazione consigliata.
- . [NET Standard](../../standard/net-standard.md): Include le API .NET Standard disponibili in tutte le implementazioni di .NET. Se l'obiettivo è poter eseguire la libreria in tutte le piattaforme supportate da .NET, questa è la destinazione consigliata.
- [ASP.NET Core](/aspnet/core): un moderno framework Web basato su .NET Core. Se l'obiettivo è di convertire l'app Web in .NET Core per supportare più piattaforme, questa è la destinazione consigliata.
- Estensioni di [piattaforma](../../core/porting/windows-compat-pack.md).NET Core : include le API di .NET Core oltre a Windows Compatibility Pack, che fornisce molte delle tecnologie disponibili per .NET Framework. Questa è una destinazione consigliata per la conversione dell'app da .NET Framework a .NET Core in Windows.
- Estensioni di [piattaforma](../../core/porting/windows-compat-pack.md).NET Standard - Include le API .NET Standard oltre a Windows Compatibility Pack, che fornisce molte delle tecnologie disponibili per .NET Framework. Questa è una destinazione consigliata per la conversione della libreria da .NET Framework a .NET Core in Windows.

## <a name="how-to-use-the-net-portability-analyzer"></a>Come usare .NET Portability Analyzer

Per iniziare a usare .NET Portability Analyzer in Visual Studio, è prima necessario scaricare l'estensione da [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) e installarla. Funziona in Visual Studio 2017 e versioni successive. È possibile configurarlo in Visual Studio tramite **Analizza** > **impostazioni analizzatore di portabilità** e selezionare le piattaforme di destinazione, ovvero le piattaforme/versioni .NET che si desidera valutare le lacune di portabilità confrontate con la piattaforma/versione con cui viene compilato l'assembly corrente.

![Screenshot dell'analizzatore di portabilità.](./media/portability-analyzer/portability-screenshot.png)

È anche possibile usare l'applicazione console ApiPort, scaricandola dal [repository ApiPort](https://aka.ms/apiportdownload). È possibile usare l'opzione di comando `listTargets` per visualizzare l'elenco di destinazioni disponibili e quindi selezionare le piattaforme di destinazione specificando l'opzione di comando `-t` o `--target`.

### <a name="analyze-portability"></a>Analizzare la portabilità
Per analizzare l'intero progetto in Visual Studio, fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionare **Analyze Assembly Portability** (Analizza portabilità dell'assembly). In caso contrario, accedere al menu **Analizza** e selezionare **Analyze Assembly Portability** (Analizza portabilità assembly). Da qui selezionare il file eseguibile o DLL del progetto.

![Screenshot di Analizzatore di portabilità da Esplora soluzioni.](./media/portability-analyzer/portability-solution-explorer.png)

È anche possibile usare l'[app console ApiPort](https://aka.ms/apiportdownload).

- Digitare il comando seguente per analizzare la directory corrente: `ApiPort.exe analyze -f .`
- Per analizzare un elenco specifico di file con estensione dll, digitare il comando seguente: `ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`
- Per altre informazioni, eseguire il comando `ApiPort.exe -?`

È consigliabile includere tutti i file con estensione exe e dll correlati disponibili che si vogliono convertire, escludendo i file da cui l'app dipende, ma di cui non si ha la proprietà e che non si è in grado di convertire. Questa operazione consentirà di ottenere il report di portabilità più pertinente possibile.

### <a name="view-and-interpret-portability-result"></a>Visualizzare e interpretare i risultati di portabilità

Nel report sono visualizzate solo le API non supportate da una piattaforma di destinazione.
Dopo aver eseguito l'analisi in Visual Studio, si vedrà comparire il collegamento al file del report sulla portabilità .NET. Se è stata usata l'[app console ApiPort](https://aka.ms/apiportdownload), il report sulla portabilità .NET è stato salvato in un file nel formato specificato. Il valore predefinito corrisponde a un file di Excel (*xlsx*) nella directory corrente.

#### <a name="portability-summary"></a>Riepilogo della portabilità

![Screenshot del Riepilogo portabilità.](./media/portability-analyzer/api-catalog-portablility-summary.png)

La sezione Portability Summary (Riepilogo della portabilità) del report indica la percentuale di portabilità per ogni assembly incluso nell'esecuzione. Nell'esempio precedente, il 71,24% delle API .NET Framework usate nell'app `svcutil` sono disponibili in .NET Core + Estensioni della piattaforma. Se si esegue lo strumento .NET Portability Analyzer per più assembly, per ognuno di questi deve essere presente una riga nel report di riepilogo della portabilità.

#### <a name="details"></a>Dettagli

![Screenshot dei dettagli della portabilità.](./media/portability-analyzer/api-catalog-portablility-details.png)

Nella sezione **Dettagli** del report sono elencate le API mancanti in una delle **piattaforme di destinazione**selezionate.

- Target type (Tipo di destinazione): per il tipo manca un'API da una piattaforma di destinazione
- Target member (Membro di destinazione): il metodo manca da una piattaforma di destinazione
- Assembly name (Nome dell'assembly): assembly .NET Framework in cui deve trovarsi l'API mancante.
- Ognuna delle piattaforme di destinazione selezionate è una colonna, ad esempio ".NET Core": il valore "Non supportato" indica che l'API non è supportata in questa piattaforma di destinazione.
- Recommended Changes (Modifiche consigliate): API o tecnologia consigliata a cui passare. Questo campo è attualmente vuoto o non aggiornato per molte API. A causa dell'elevato numero di API, è molto difficile tenerlo aggiornato. È in corso l'esame di soluzioni alternative che consentano di offrire informazioni utili ai clienti.

#### <a name="missing-assemblies"></a>Assembly mancanti

![Screenshot degli assembly mancanti.](./media/portability-analyzer/api-catalog-missing-assemblies.png)

Nel report può essere presente la sezione Missing Assemblies (Assembly mancanti). Questa sezione informa che gli assembly analizzati fanno riferimento agli assembly visualizzati nell'elenco, che non sono stati analizzati. Se si tratta di assembly di cui si ha la proprietà, includerli nell'esecuzione di API Portability Analyzer (ApiPort) per ottenere un report dettagliato sulla portabilità a livello di API. Se si tratta di una libreria di terze parti, verificare l'eventuale disponibilità una versione più recente che supporti la piattaforma di destinazione. In caso affermativo, prendere in considerazione la possibilità di passare alla versione più recente. Si prevede che alla fine questo elenco includa tutti gli assembly di terze parti da cui l'app dipende e che per questi sia confermata la disponibilità di una versione che supporti la piattaforma di destinazione.

Per altre informazioni su .NET Portability Analyzer, vedere la [documentazione di GitHub](https://github.com/Microsoft/dotnet-apiport#documentation) e il video [A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) (Panoramica rapida di .NET Portability Analyzer) in Channel 9.
