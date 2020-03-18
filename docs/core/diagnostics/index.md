---
title: Panoramica degli strumenti di diagnostica -.NET Core
description: Panoramica degli strumenti e delle tecniche disponibili per la diagnosi delle applicazioni .NET Core.
ms.date: 12/17/2019
ms.topic: overview
ms.openlocfilehash: 0a78ec6c88f5323104277cddea4480a5e13b4e41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79399049"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>Quali strumenti di diagnostica sono disponibili in .NET Core?

Il software non sempre si comporta come previsto, ma .NET Core offre strumenti e API utili per diagnosticare questi problemi in modo rapido ed efficace.

Questo articolo consente di trovare i vari strumenti necessari.

## <a name="managed-debuggers"></a>Debugger gestiti

[I debugger gestiti](managed-debuggers.md) consentono di interagire con il programma. La sospensione, l'esecuzione incrementale, l'analisi e la ripresa forniscono informazioni approfondite sul comportamento del codice. Un debugger è la prima scelta per la diagnosi dei problemi funzionali che possono essere facilmente riprodotti.

## <a name="logging-and-tracing"></a>Registrazione e traccia

[La registrazione e la traccia](logging-tracing.md) sono tecniche correlate. Si riferiscono all'instrumentazione del codice per creare file di log. I file registrano i dettagli delle operazioni eseguite da un programma. Questi dettagli possono essere usati per diagnosticare i problemi più complessi. In combinazione con i timestamp, queste tecniche sono utili anche per le analisi delle prestazioni.

## <a name="unit-testing"></a>Testing unità

[Gli unit test](../testing/index.md) sono un componente chiave della continua integrazione e distribuzione di software di alta qualità. Gli unit test sono progettati per offrire avvisi in anticipo in caso di problemi funzionali.

## <a name="net-core-dotnet-diagnostic-global-tools"></a>Strumenti globali di diagnostica dotnet .NET Core

### <a name="dotnet-counters"></a>dotnet-counters

[dotnet-counters](dotnet-counters.md) è uno strumento di monitoraggio delle prestazioni per il monitoraggio dello stato di primo livello e l'analisi delle prestazioni.dotnet-counters is a performance monitoring tool for first-level health monitoring and performance investigation. Osserva i valori dei contatori delle prestazioni pubblicati tramite l'API. <xref:System.Diagnostics.Tracing.EventCounter> Ad esempio, è possibile monitorare rapidamente elementi quali l'utilizzo della CPU o la frequenza delle eccezioni generate nell'applicazione .NET Core.For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.

### <a name="dotnet-dump"></a>dotnet-dump

Lo strumento [dotnet-dump](dotnet-dump.md) è un modo per raccogliere e analizzare i dump principali di Windows e Linux senza un debugger nativo.

### <a name="dotnet-trace"></a>dotnet-trace

.NET Core include ciò che viene chiamato tramite il quale vengono esposti i `EventPipe` dati di diagnostica. Lo strumento [dotnet-trace](dotnet-trace.md) consente di usare dati di profilatura interessanti dall'app che possono essere utili negli scenari in cui è necessario eseguire il root causa l'esecuzione lenta delle app.

## <a name="net-core-diagnostics-tutorials"></a>Esercitazioni di diagnostica .NET Core

### <a name="debug-a-memory-leak"></a>Eseguire il debug di una perdita di memoria

[Esercitazione: Eseguire il debug](debug-memory-leak.md) di una perdita di memoria illustra come individuare una perdita di memoria. Lo strumento [dotnet-counters](dotnet-counters.md) viene utilizzato per confermare la perdita e lo strumento [dotnet-dump](dotnet-dump.md) viene utilizzato per diagnosticare la perdita.
