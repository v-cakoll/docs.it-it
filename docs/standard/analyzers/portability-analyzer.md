---
title: .NET Portability Analyzer | .NET
description: Informazioni su come usare lo strumento .NET Portability Analyzer per valutare la portabilità del codice tra le diverse implementazioni di .NET, inclusi .NET Core, .NET Standard, UWP e Xamarin.
author: blackdwarf
ms.author: mairaw
ms.date: 07/26/2017
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: f310e5fe45315dfa41d596c92d9412dc6b3bc125
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

È possibile fare in modo che le librerie in uso siano multi-piattaforma e valutare la quantità di lavoro necessario per rendere l'applicazione compatibile con altri profili e implementazioni di .NET, tra cui .NET Core, .NET Standard, UWP e Xamarin per iOS, Android e Mac. [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) è uno strumento che crea un report dettagliato sulla flessibilità del programma in tutte le implementazioni di .NET analizzando gli assembly. Portability Analyzer è offerto come estensione di Visual Studio e come applicazione della console.

## <a name="new-targets"></a>Nuove destinazioni

* [.NET Core](../../core/index.md): ha una struttura modulare, con assembly affiancato ed è destinato a scenari multi-piattaforma. La modalità affiancata consente di adottare le nuove versioni di .NET Core senza interrompere le altre applicazioni.
* [ASP.NET Core](/aspnet/core): è un framework Web moderno basato su .NET Core che offre agli sviluppatori gli stessi vantaggi.
* [Piattaforma UWP (Universal Windows Platform)](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): offre una compilazione statica di .NET Native che consente di migliorare le prestazioni delle app Windows Store eseguite su computer ARM e x64. 
* .NET Core + Estensioni di piattaforma: incluse le API .NET Core oltre ad altre API nell'ecosistema .NET, ad esempio WCF, ASP.NET Core, FSharp e Azure.
* .NET Standard + Estensioni di piattaforma: include le API .NET Standard oltre ad altre API nell'ecosistema .NET, ad esempio WCF, ASP.NET Core, FSharp e Azure.

## <a name="how-to-use-portability-analyzer"></a>Come usare Portability Analyzer

Per iniziare a usare .NET Portability Analyzer, scaricare l'estensione da [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) e installarla. Funziona in Visual Studio 2015 e Visual Studio 2017. È possibile configurarlo in Visual Studio scegliendo **Analyze** > **Portability Analyzer Settings** (Analizza - Impostazioni di Portability Analyzer ) e selezionando le piattaforme di destinazione.

![Schermata della portabilità](./media/portability-analyzer/portability-screenshot.png)

Per analizzare l'intero progetto, fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionare **Analyze Assembly Portability** (Analizza portabilità dell'assembly). In caso contrario, accedere al menu **Analizza** e selezionare **Analyze Assembly Portability** (Analizza portabilità assembly). Da qui selezionare il file eseguibile o DLL del progetto.

![Esplora soluzioni per la portabilità](./media/portability-analyzer/portability-solution-explorer.png)

Dopo aver eseguito l'analisi, verrà visualizzato il report sulla portabilità di .NET. Solo i tipi non supportati da una piattaforma di destinazione vengono visualizzati nell'elenco ed è possibile esaminare i suggerimenti nella scheda **Messaggi** in **Elenco errori**. È anche possibile passare alle aree problematiche direttamente dalla scheda **Messaggi**.

![Report sulla portabilità](./media/portability-analyzer/portability-report.png)

Si vuole evitare di usare Visual Studio? È possibile usare Portability Analyzer anche dal prompt dei comandi. Scaricare solo [API Portability Analyzer](http://www.microsoft.com/download/details.aspx?id=42678).

*   Digitare il comando seguente per analizzare la directory corrente: `\...\ApiPort.exe analyze -f .`
*   Per analizzare un elenco specifico di file con estensione dll, digitare il comando seguente: `\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`

Il report sulla portabilità di .NET viene salvato come file di Excel con *estensione xlsx* nella directory corrente. Altre informazioni sono disponibili nella scheda **Dettagli** della cartella di lavoro di Excel.

Per altre informazioni su .NET Portability Analyzer, vedere la [documentazione di GitHub](https://github.com/Microsoft/dotnet-apiport#documentation) e il video [A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) (Panoramica rapida di .NET Portability Analyzer) in Channel 9.
