---
title: .NET Portability Analyzer - .NET | Microsoft Docs
description: "Informazioni su come usare lo strumento .NET Portability Analyzer per valutare la portabilità del codice tra le diverse implementazioni di .NET."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 07/26/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: adb1971c14c8ff8c147dba378ae0e9a5bc0fb5ad
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---

# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

È possibile fare in modo che le librerie in uso siano multi-piattaforma e vedere quanto lavoro è necessario per rendere l'applicazione compatibile con altre implementazioni di .NET. [.NET Portability Analyzer](http://go.microsoft.com/fwlink/?LinkID=507467) è uno strumento che crea un report dettagliato sulla flessibilità del programma in tutte le implementazioni di .NET analizzando gli assembly. Portability Analyzer è offerto come estensione di Visual Studio e come applicazione della console.

## <a name="new-targets"></a>Nuove destinazioni

* [.NET Core](https://dotnetfoundation.org/net-core): ha una struttura modulare, con assembly affiancato ed è destinato a scenari multi-piattaforma. La modalità affiancata consente di adottare le nuove versioni di .NET Core senza interrompere le altre applicazioni.
* [ASP.NET Core](https://dotnetfoundation.org/asp-net-core): è un framework Web moderno basato su .NET Core che offre agli sviluppatori gli stessi vantaggi.
* [Piattaforma UWP (Universal Windows Platform)](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): offre una compilazione statica di .NET Native che consente di migliorare le prestazioni delle app Windows Store eseguite su computer ARM e x64. 
* .NET Core + Estensioni di piattaforma: incluse le API .NET Core oltre ad altre API nell'ecosistema .NET, ad esempio WCF, ASP.NET Core, FSharp e Azure.
* .NET Standard + Estensioni di piattaforma: include le API .NET Standard oltre ad altre API nell'ecosistema .NET, ad esempio WCF, ASP.NET Core, FSharp e Azure.

## <a name="how-to-use-portability-analyzer"></a>Come usare Portability Analyzer

Per iniziare a usare .NET Portability Analyzer, scaricare l'estensione da [Visual Studio Gallery](http://go.microsoft.com/fwlink/?LinkID=507467) e installarla. Funziona in Visual Studio 2015 e Visual Studio 2017. È possibile configurarlo in Visual Studio scegliendo **Analyze** > **Portability Analyzer Settings** (Analizza - Impostazioni di Portability Analyzer ) e selezionando le piattaforme di destinazione.

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

