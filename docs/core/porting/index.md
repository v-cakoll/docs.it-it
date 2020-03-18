---
title: Porta da .NET Framework a .NET Core
description: Informazioni sul processo di trasferimento e sugli strumenti che possono risultare utili durante il trasferimento di un progetto .NET Framework in .NET Core.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: e483bb6e48dad6c3bf71bfa81e704a137fc02094
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75937326"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a>Panoramica del porting da .NET Framework a .NET Core

Si potrebbe avere codice attualmente in esecuzione su .NET Framework che si è interessati a convertire a .NET Core. Questo articolo include:

* Panoramica del processo di porting.
* Un elenco di strumenti che possono risultare utili quando si esegue il porting del codice in .NET Core.A list of tools that you may find helpful when you're porting your code to .NET Core.

## <a name="overview-of-the-porting-process"></a>Panoramica del processo di conversione

Si consiglia di utilizzare il processo seguente quando si esegue il porting del progetto in .NET Core:

1. Retarget tutti i progetti che si desidera eseguire il porting per .NET Framework 4.7.2 o versione successiva.

   Questo passaggio garantisce che si possano usare le alternative alle API per le destinazioni specifiche di .NET Framework quando .NET Core non supporta un'API specifica.

2. Utilizzare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per analizzare gli assembly e verificare se sono portabili a .NET Core.Use the .NET Portability Analyzer to analyze your assemblies and see if they're portable to .NET Core.

   Lo strumento ANALIZZATore di portabilità API analizza gli assembly compilati e genera un report. Questo report mostra un riepilogo di portabilità di alto livello e una suddivisione di ogni API in uso che non è disponibile in NET Core.This report shows a high-level portability summary and a breakdown of each API you're using that isn't available on NET Core.

3. Installare [l'analizzatore API .NET](../../standard/analyzers/api-analyzer.md) nei progetti <xref:System.PlatformNotSupportedException> per identificare le API che generano su alcune piattaforme e altri potenziali problemi di compatibilità.

   Questo strumento è simile all'analizzatore di portabilità, ma invece di analizzare se il codice può compilare <xref:System.PlatformNotSupportedException> in .NET Core, analizza se si usa un'API in un modo che genererà un codice in fase di esecuzione. Anche se questo non è comune se si sta passando da.NET Framework 4.7.2 o versione successiva, è bene controllare. Per altre informazioni sulle API che generano eccezioni in .NET Core, vedere [API che generano sempre eccezioni in .NET Core](../compatibility/unsupported-apis.md).

4. Convertire tutte `packages.config` le dipendenze nel formato [PackageReference](/nuget/consume-packages/package-references-in-project-files) con lo strumento di [conversione in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).

   Questo passaggio comporta la conversione `packages.config` delle dipendenze dal formato legacy. `packages.config`non funziona in .NET Core, pertanto questa conversione è necessaria se si dispone di dipendenze del pacchetto.

5. Creare nuovi progetti per .NET Core e copiare i file di origine o tentare di convertire il file di progetto esistente con uno strumento.

   .NET Core utilizza un formato di file di [progetto](../tools/csproj.md) semplificato (e diverso) rispetto a .NET Framework. Per continuare, è necessario convertire i file di progetto in questo formato.

6. Eseguire il porting del codice di test.

   Poiché il porting in .NET Core è una modifica significativa alla codebase, è consigliabile eseguire il porting dei progetti di test in modo da poter eseguire test durante il porting del codice. MSTest, xUnit e NUnit funzionano tutti su .NET Core.

Inoltre, è possibile tentare di eseguire il porting di soluzioni più piccole o singoli progetti in un'unica operazione nel formato di file di progetto .NET Core con lo strumento [dotnet try-convert.](https://github.com/dotnet/try-convert) `dotnet try-convert`non è garantito che funzioni per tutti i tuoi progetti e può causare sottili cambiamenti nel comportamento da cui dipendevi. Usalo come _punto di partenza_ per automatizzare le cose di base che possono essere automatizzate. Non è una soluzione garantita per la migrazione di un progetto.

## <a name="next-steps"></a>Passaggi successivi

>[!div class="nextstepaction"]
>[Analizzare le dipendenzeAnalyze dependencies](third-party-deps.md)
