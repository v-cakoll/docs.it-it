---
title: Panoramica degli strumenti di diagnostica -.NET Core
description: Panoramica degli strumenti e delle tecniche disponibili per la diagnosi delle applicazioni .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974149"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>Quali strumenti di diagnostica sono disponibili in .NET Core?

Il software non sempre si comporta come previsto, ma .NET Core offre strumenti e API utili per diagnosticare questi problemi in modo rapido ed efficace.

Questo articolo consente di trovare i vari strumenti necessari.

## <a name="managed-debuggersmanaged-debuggersmd"></a>[Debugger gestiti](managed-debuggers.md)
I debugger gestiti consentono di interagire con il programma. La sospensione, l'esecuzione incrementale, l'analisi e la ripresa forniscono informazioni approfondite sul comportamento del codice. Un debugger è la prima scelta per la diagnosi dei problemi funzionali che possono essere facilmente riprodotti.

## <a name="logging-and-tracinglogging-tracingmd"></a>[Registrazione e traccia](logging-tracing.md)
La registrazione e la traccia sono tecniche correlate. Si riferiscono all'instrumentazione del codice per creare file di log. I file registrano i dettagli delle operazioni eseguite da un programma. Questi dettagli possono essere usati per diagnosticare i problemi più complessi. In combinazione con i timestamp, queste tecniche sono utili anche per le analisi delle prestazioni.

## <a name="unit-testingtestingindexmd"></a>[Testing unità](../testing/index.md)
Il testing unità è un componente chiave dell'integrazione e distribuzione continue di software di alta qualità. Gli unit test sono progettati per offrire avvisi in anticipo in caso di problemi funzionali.
