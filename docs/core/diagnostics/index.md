---
title: Panoramica degli strumenti di diagnostica -.NET Core
description: Panoramica degli strumenti e delle tecniche disponibili per la diagnosi delle applicazioni .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: dc64c03ee9c8cee6a5b3c5cc089b4a1a2c27f84a
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924782"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>Quali strumenti di diagnostica sono disponibili in .NET Core?

Il software non sempre si comporta come previsto, ma .NET Core offre strumenti e API utili per diagnosticare questi problemi in modo rapido ed efficace.

Questo articolo consente di trovare i vari strumenti necessari.

## <a name="managed-debuggers"></a>Debugger gestiti

I [debugger gestiti](managed-debuggers.md) consentono di interagire con il programma. La sospensione, l'esecuzione incrementale, l'analisi e la ripresa forniscono informazioni approfondite sul comportamento del codice. Un debugger è la prima scelta per la diagnosi dei problemi funzionali che possono essere facilmente riprodotti.

## <a name="logging-and-tracing"></a>Registrazione e traccia

La [registrazione e la traccia](logging-tracing.md) sono tecniche correlate. Si riferiscono all'instrumentazione del codice per creare file di log. I file registrano i dettagli delle operazioni eseguite da un programma. Questi dettagli possono essere usati per diagnosticare i problemi più complessi. In combinazione con i timestamp, queste tecniche sono utili anche per le analisi delle prestazioni.

## <a name="unit-testing"></a>Testing unità

[Unit test](../testing/index.md) è un componente chiave dell'integrazione continua e della distribuzione di software di alta qualità. Gli unit test sono progettati per offrire avvisi in anticipo in caso di problemi funzionali.

## <a name="net-core-dotnet-diagnostic-global-tools"></a>Strumenti globali di diagnostica DotNet di .NET Core

### <a name="dotnet-counters"></a>dotnet-counters

[DotNet-Counters](dotnet-counters.md) è uno strumento di monitoraggio delle prestazioni per il monitoraggio dell'integrità di primo livello e l'analisi delle prestazioni. Osserva i valori dei contatori delle prestazioni pubblicati tramite l' <xref:System.Diagnostics.Tracing.EventCounter> API. Ad esempio, è possibile monitorare rapidamente elementi come l'utilizzo della CPU o la frequenza delle eccezioni generate nell'applicazione .NET Core.

### <a name="dotnet-dump"></a>dotnet-dump

Lo strumento [DotNet-dump](dotnet-dump.md) consente di raccogliere e analizzare i dump di base di Windows e Linux senza un debugger nativo.

### <a name="dotnet-trace"></a>dotnet-trace

.NET Core include ciò che viene chiamato `EventPipe` tramite il quale vengono esposti i dati di diagnostica. Lo strumento [DotNet-Trace](dotnet-trace.md) consente di usare i dati di profilatura interessanti dall'app che possono risultare utili negli scenari in cui è necessario causare la lentezza delle app.

## <a name="net-core-diagnostics-tutorials"></a>Esercitazioni di diagnostica .NET Core

### <a name="debug-a-memory-leak"></a>Eseguire il debug di una perdita di memoria

[Esercitazione: eseguire il debug di una perdita di memoria](debug-memory-leak.md) per trovare una perdita di memoria. Lo strumento [DotNet-counts](dotnet-counters.md) viene usato per confermare la perdita e lo strumento [DotNet-dump](dotnet-dump.md) viene usato per diagnosticare la perdita.

### <a name="debug-high-cpu-usage"></a>Eseguire il debug di un utilizzo elevato della CPU

[Esercitazione: eseguire il debug di un utilizzo elevato della CPU](debug-highcpu.md) per esaminare l'utilizzo elevato della CPU. USA lo strumento [DotNet-Counters](dotnet-counters.md) per verificare l'utilizzo elevato della CPU. Viene quindi illustrato come utilizzare [Trace for Performance Analysis Utility ( `dotnet-trace` )](dotnet-trace.md) o Linux `perf` per raccogliere e visualizzare il profilo di utilizzo della CPU.

### <a name="debug-deadlock"></a>Deadlock di debug

[Esercitazione: deadlock di debug](debug-deadlock.md) Mostra come usare lo strumento [DotNet-dump](dotnet-dump.md) per analizzare i thread e i blocchi.
