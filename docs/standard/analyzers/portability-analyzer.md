---
title: .NET Portability Analyzer | .NET
description: Informazioni su come usare lo strumento .NET Portability Analyzer per valutare la portabilità del codice tra le diverse implementazioni di .NET, inclusi .NET Core, .NET Standard, UWP e Xamarin.
ms.date: 07/10/2019
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: f05d4f4a2fce8fa9a4d2e334f44190ea37335038
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859748"
---
# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

È possibile fare in modo che le librerie in uso supportino architetture multi-piattaforma e valutare la quantità di lavoro necessario per rendere l'applicazione compatibile con altri profili e implementazioni di .NET, tra cui .NET Core, .NET Standard, UWP e Xamarin per iOS, Android e Mac. [.NET Portability Analyzer](https://github.com/microsoft/dotnet-apiport) è uno strumento che crea un report dettagliato sulla flessibilità del programma in tutte le implementazioni di .NET analizzando gli assembly. Portability Analyzer viene offerto come [estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) che consente di analizzare gli assembly per progetto e come [app console ApiPort](https://aka.ms/apiportdownload) che consente di analizzare gli assembly in base a file o directory specificati.

## <a name="common-targets"></a>Destinazioni comuni

* [.NET Core](../../core/index.md): ha una struttura modulare, con assembly affiancato ed è destinato a scenari multi-piattaforma. La modalità affiancata consente di adottare le nuove versioni di .NET Core senza interrompere le altre applicazioni. Se l'obiettivo è di convertire l'app in una versione di .NET Core che supporta architetture multipiattaforma, questa è la destinazione consigliata. 
* .[NET Standard](../../standard/net-standard.md): include le API .NET Standard disponibili in tutte le implementazioni .NET. Se l'obiettivo è poter eseguire la libreria in tutte le piattaforme supportate da .NET, questa è la destinazione consigliata.  
* [ASP.NET Core](/aspnet/core): un framework Web moderno basato su .NET Core. Se l'obiettivo è di convertire l'app Web in .NET Core per supportare più piattaforme, questa è la destinazione consigliata.
* .NET Core + [Platform Extensions](../../core/porting/windows-compat-pack.md) (.NET Core + estensioni di piattaforma): include le API .NET Core, oltre a Windows Compatibility Pack, che offre molte delle tecnologie disponibili in .NET Framework. Questa è una destinazione consigliata per la conversione dell'app da .NET Framework a .NET Core in Windows.
* .NET Standard + [Platform Extensions](../../core/porting/windows-compat-pack.md) (.NET Standard + estensioni di piattaforma): include le API .NET Standard, oltre a Windows Compatibility Pack, che offre molte delle tecnologie disponibili in .NET Framework. Questa è una destinazione consigliata per la conversione della libreria da .NET Framework a .NET Core in Windows.

## <a name="how-to-use-the-net-portability-analyzer"></a>Come usare .NET Portability Analyzer

Per iniziare a usare .NET Portability Analyzer in Visual Studio, è prima necessario scaricare l'estensione da [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) e installarla. Funziona in Visual Studio 2017 e versioni successive. È possibile configurare Portability Analyzer in Visual Studio tramite **Analizza** > **Impostazioni Portability Analyzer** e selezionare le piattaforme di destinazione, ovvero le piattaforme o le versioni di .NET di cui si vogliono valutare i gap di portabilità rispetto alla piattaforma o alla versione con cui è compilato l'assembly corrente.

![Schermata della portabilità](./media/portability-analyzer/portability-screenshot.png)

È anche possibile usare l'applicazione console ApiPort, scaricandola dal [repository ApiPort](http://aka.ms/apiportdownload). È possibile usare l'opzione di comando `listTargets` per visualizzare l'elenco di destinazioni disponibili e quindi selezionare le piattaforme di destinazione specificando l'opzione di comando `-t` o `--target`. 

### <a name="analyze-portability"></a>Analizzare la portabilità
Per analizzare l'intero progetto in Visual Studio, fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionare **Analyze Assembly Portability** (Analizza portabilità dell'assembly). In caso contrario, accedere al menu **Analizza** e selezionare **Analyze Assembly Portability** (Analizza portabilità assembly). Da qui selezionare il file eseguibile o DLL del progetto.

![Portability Analyzer da Esplora soluzioni](./media/portability-analyzer/portability-solution-explorer.png)

È anche possibile usare l'[app console ApiPort](https://aka.ms/apiportdownload). 

* Digitare il comando seguente per analizzare la directory corrente: `ApiPort.exe analyze -f .`
* Per analizzare un elenco specifico di file con estensione dll, digitare il comando seguente: `ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`
* Per altre informazioni, eseguire il comando `ApiPort.exe -?`

È consigliabile includere tutti i file con estensione exe e dll correlati disponibili che si vogliono convertire, escludendo i file da cui l'app dipende, ma di cui non si ha la proprietà e che non si è in grado di convertire. Questa operazione consentirà di ottenere il report di portabilità più pertinente possibile.  

### <a name="view-and-interpret-portability-result"></a>Visualizzare e interpretare i risultati di portabilità

Nel report sono visualizzate solo le API non supportate da una piattaforma di destinazione. Dopo aver eseguito l'analisi in Visual Studio, si vedrà comparire il collegamento al file del report sulla portabilità .NET. Se è stata usata l'[app console ApiPort](https://aka.ms/apiportdownload), il report sulla portabilità .NET è stato salvato in un file nel formato specificato. Il valore predefinito corrisponde a un file di Excel (*xlsx*) nella directory corrente.

#### <a name="portability-summary"></a>Riepilogo della portabilità 

![Riepilogo della portabilità](./media/portability-analyzer/portabilitysummary.png)

La sezione Portability Summary (Riepilogo della portabilità) del report indica la percentuale di portabilità per ogni assembly interessato dall'esecuzione. Nell'esempio precedente, l'89,74% delle API .NET Framework usate nell'app `ConsoleAppFramework` sono disponibili in .NET Core + Platform Extensions v2.2 (.NET Core + estensioni di piattaforma versione 2.2). Se si esegue lo strumento .NET Portability Analyzer per più assembly, per ognuno di questi deve essere presente una riga nel report di riepilogo della portabilità.

#### <a name="details"></a>Dettagli

![Dettagli di portabilità](./media/portability-analyzer/portabilitydetails.png)

La sezione Details (Dettagli) del report elenca le API mancanti da una delle piattaforme di destinazione. 

 - Target type (Tipo di destinazione): per il tipo manca un'API da una piattaforma di destinazione 
 - Target member (Membro di destinazione): il metodo manca da una piattaforma di destinazione 
 - Assembly name (Nome dell'assembly): assembly .NET Framework in cui deve trovarsi l'API mancante. 
 - Ognuna delle piattaforme di destinazione selezionate corrisponde a una colonna, ad esempio ".NET Core". Il valore "Not supported" (Non supportata) indica che l'API non è supportata nella piattaforma di destinazione corrispondente. 
 - Recommended Changes (Modifiche consigliate): API o tecnologia consigliata a cui passare. Questo campo è attualmente vuoto o non aggiornato per molte API. A causa dell'elevato numero di API, è molto difficile tenerlo aggiornato. È in corso l'esame di soluzioni alternative che consentano di offrire informazioni utili ai clienti.

#### <a name="missing-assemblies"></a>Assembly mancanti

![Dettagli di portabilità](./media/portability-analyzer/missingassemblies.png)

Nel report può essere presente la sezione Missing Assemblies (Assembly mancanti). Questa sezione informa che gli assembly analizzati fanno riferimento agli assembly visualizzati nell'elenco, che non sono stati analizzati. Se si tratta di assembly di cui si ha la proprietà, includerli nell'esecuzione di API Portability Analyzer (ApiPort) per ottenere un report dettagliato sulla portabilità a livello di API. Se si tratta di una libreria di terze parti, verificare l'eventuale disponibilità una versione più recente che supporti la piattaforma di destinazione. In caso affermativo, prendere in considerazione la possibilità di passare alla versione più recente. Si prevede che alla fine questo elenco includa tutti gli assembly di terze parti da cui l'app dipende e che per questi sia confermata la disponibilità di una versione che supporti la piattaforma di destinazione.  

Per altre informazioni su .NET Portability Analyzer, vedere la [documentazione di GitHub](https://github.com/Microsoft/dotnet-apiport#documentation) e il video [A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) (Panoramica rapida di .NET Portability Analyzer) in Channel 9.


