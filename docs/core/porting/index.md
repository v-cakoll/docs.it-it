---
title: Porta da .NET Framework a .NET Core
description: Informazioni sul processo di trasferimento e sugli strumenti che possono risultare utili durante il trasferimento di un progetto .NET Framework in .NET Core.
author: cartermp
ms.date: 10/22/2019
ms.custom: seodec18
ms.openlocfilehash: 89f00e5c6ce7f3cea7a3135c9b2856c54a70da40
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73038524"
---
# <a name="overview-of-the-porting-process-from-net-framework-to-net-core"></a>Panoramica del processo di porting da .NET Framework a .NET Core

È possibile che si disponga di codice attualmente in esecuzione sul .NET Framework che si desidera trasferire a .NET Core. Questo articolo fornisce le seguenti funzionalità:

* Panoramica del processo di porting.
* Un elenco degli strumenti che possono risultare utili quando si trasferisce il codice a .NET Core.

## <a name="overview-of-the-porting-process"></a>Panoramica del processo di conversione

È consigliabile usare la procedura seguente per trasferire il progetto a .NET Core:

1. Ridefinire le destinazioni di tutti i progetti che si vuole convertire a .NET Framework 4.7.2 o versione successiva.

   Questo passaggio garantisce che si possano usare le alternative alle API per le destinazioni specifiche di .NET Framework quando .NET Core non supporta un'API specifica.

2. Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per analizzare gli assembly e verificare se sono portabili a .NET Core.

   Lo strumento API Portability Analyzer analizza gli assembly compilati e genera un report. Questo report Mostra un riepilogo della portabilità di alto livello e una suddivisione di ogni API in uso non disponibile in .NET Core.

3. Installare l' [analizzatore di API .NET](../../standard/analyzers/api-analyzer.md) nei progetti per identificare le API che generano <xref:System.PlatformNotSupportedException> in alcune piattaforme e altri potenziali problemi di compatibilità.

   Questo strumento è simile a Portability Analyzer, ma invece di analizzare gli elementi che possono essere creati in .NET Core, analizza se si usa un'API in modo da generare la <xref:System.PlatformNotSupportedException> in fase di esecuzione. Sebbene questo non sia comune se si passa da .NET Framework 4.7.2 o versione successiva, è opportuno verificare.

4. Convertire tutte le dipendenze `packages.config` nel formato [PackageReference](/nuget/consume-packages/package-references-in-project-files) con lo [strumento di conversione in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).

   Questo passaggio prevede la conversione delle dipendenze dal formato legacy `packages.config`. `packages.config` non funziona in .NET Core, quindi questa conversione è necessaria se sono presenti dipendenze del pacchetto.

5. Creare nuovi progetti per .NET Core e copiare i file di origine oppure provare a convertire il file di progetto esistente con uno strumento.

   .NET Core usa un [formato di file di progetto](../tools/csproj.md) semplificato (e diverso) rispetto a .NET Framework. Per continuare è necessario convertire i file di progetto in questo formato.

6. Trasferire il codice di test.

   Poiché la portabilità in .NET Core è una modifica di rilievo per la base di codici, è consigliabile convertire i test per poterli eseguire durante la conversione del codice. MSTest, xUnit e NUnit funzionano in .NET Core.

Inoltre, è possibile provare a trasferire le soluzioni più piccole o i singoli progetti al formato di file di progetto .NET Core con lo strumento [DotNet try-Convert](https://github.com/dotnet/try-convert) in un'unica operazione. `dotnet try-convert` non è garantito che funzioni per tutti i progetti e potrebbe causare modifiche minime nel comportamento che è possibile riscontrare. Deve essere usato come punto di _partenza_ per automatizzare gli elementi di base che possono essere automatizzati. Non si tratta di una soluzione garantita per la migrazione di un progetto.

>[!div class="step-by-step"]
>[avanti](net-framework-tech-unavailable.md)
