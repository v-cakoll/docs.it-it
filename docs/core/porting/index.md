---
title: Porta da .NET Framework a .NET Core
description: Informazioni sul processo di trasferimento e sugli strumenti che possono risultare utili durante il trasferimento di un progetto .NET Framework in .NET Core.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: e483bb6e48dad6c3bf71bfa81e704a137fc02094
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937326"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a>Panoramica del porting da .NET Framework a .NET Core

È possibile che si disponga di codice attualmente in esecuzione sul .NET Framework che si desidera trasferire a .NET Core. Questo articolo include:

* Panoramica del processo di porting.
* Un elenco di strumenti che possono risultare utili quando si trasferisce il codice a .NET Core.

## <a name="overview-of-the-porting-process"></a>Panoramica del processo di conversione

Quando si trasferisce il progetto a .NET Core, è consigliabile usare il processo seguente:

1. Ridestinare tutti i progetti che si desidera trasferire alla destinazione .NET Framework 4.7.2 o versione successiva.

   Questo passaggio garantisce che si possano usare le alternative alle API per le destinazioni specifiche di .NET Framework quando .NET Core non supporta un'API specifica.

2. Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per analizzare gli assembly e verificare se sono portabili a .NET Core.

   Lo strumento API Portability Analyzer analizza gli assembly compilati e genera un report. Questo report Mostra un riepilogo della portabilità di alto livello e una suddivisione di ogni API in uso non disponibile in .NET Core.

3. Installare l' [analizzatore di API .NET](../../standard/analyzers/api-analyzer.md) nei progetti per identificare le API che generano <xref:System.PlatformNotSupportedException> in alcune piattaforme e altri potenziali problemi di compatibilità.

   Questo strumento è simile a Portability Analyzer, ma invece di analizzare se il codice può essere compilato in .NET Core, analizza se si sta usando un'API in modo da generare un <xref:System.PlatformNotSupportedException> in fase di esecuzione. Sebbene questo non sia comune se si passa da .NET Framework 4.7.2 o versione successiva, è opportuno verificare. Per altre informazioni sulle API che generano eccezioni in .NET Core, vedere [API che generano sempre eccezioni in .NET Core](../compatibility/unsupported-apis.md).

4. Convertire tutte le dipendenze `packages.config` nel formato [PackageReference](/nuget/consume-packages/package-references-in-project-files) con lo [strumento di conversione in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).

   Questo passaggio prevede la conversione delle dipendenze dal formato legacy `packages.config`. `packages.config` non funziona in .NET Core, quindi questa conversione è necessaria se sono presenti dipendenze del pacchetto.

5. Creare nuovi progetti per .NET Core e copiare i file di origine oppure provare a convertire il file di progetto esistente con uno strumento.

   .NET Core usa un [formato di file di progetto](../tools/csproj.md) semplificato (e diverso) rispetto a .NET Framework. Per continuare è necessario convertire i file di progetto in questo formato.

6. Trasferire il codice di test.

   Poiché la portabilità in .NET Core è una modifica significativa nella codebase, è consigliabile trasferire i progetti di test in modo da poter eseguire i test quando si trasferisce il codice. MSTest, xUnit e NUnit funzionano in .NET Core.

Inoltre, è possibile tentare di trasferire le soluzioni più piccole o i singoli progetti in un'unica operazione al formato di file di progetto .NET Core con lo strumento [DotNet try-Convert](https://github.com/dotnet/try-convert) . `dotnet try-convert` non è garantito che funzioni per tutti i progetti e potrebbe causare modifiche minime al comportamento da cui dipende. Utilizzarlo come _punto di partenza_ per automatizzare gli elementi di base che possono essere automatizzati. Non si tratta di una soluzione garantita per la migrazione di un progetto.

## <a name="next-steps"></a>Passaggi successivi

>[!div class="nextstepaction"]
>[Analizzare le dipendenze](third-party-deps.md)
