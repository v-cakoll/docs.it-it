---
title: Convertire il codice da .NET Framework a .NET Core
description: Informazioni sul processo di trasferimento e sugli strumenti che possono risultare utili durante il trasferimento di un progetto .NET Framework in .NET Core.
author: cartermp
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 870320c8467237e87a2675ec5cfb57647026d8ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663232"
---
# <a name="port-your-code-from-net-framework-to-net-core"></a>Convertire il codice da .NET Framework a .NET Core

Se è disponibile codice per .NET Framework, si potrebbe essere interessati a eseguirlo anche in .NET Core. Ecco una panoramica del processo di conversione e un elenco degli strumenti che possono risultare utili durante la conversione del codice a .NET Core.

## <a name="overview-of-the-porting-process"></a>Panoramica del processo di conversione

Questo è il processo che è consigliabile eseguire durante la conversione del progetto a .NET Core. Ogni passaggio del processo è descritto più dettagliatamente in altri articoli.

1. Identificare e spiegare le dipendenze di terze parti.

   Questo passaggio comporta la comprensione delle dipendenze di terze parti, della dipendenza dell'utente da queste ultime, di come controllare se vengono eseguite anche in .NET Core e dei passaggi da eseguire in caso contrario. Illustra anche come è possibile eseguire la migrazione delle dipendenze al formato [PackageReference](/nuget/consume-packages/package-references-in-project-files) usato in .NET Core.

2. Ridefinire le destinazioni di tutti i progetti che si vuole convertire a .NET Framework 4.7.2 o versione successiva.

   Questo passaggio garantisce che si possano usare le alternative alle API per le destinazioni specifiche di .NET Framework quando .NET Core non supporta un'API specifica.

3. Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per analizzare gli assembly e sviluppare un piano per eseguire il trasferimento in base ai risultati ottenuti.

   Lo strumento API Portability Analyzer analizza gli assembly compilati e genera un report che mostra un riepilogo generale della portabilità e un'analisi dettagliata di ogni API in uso non disponibile in .NET Core. È possibile usare questo report insieme a un'analisi della base di codici per sviluppare un piano per il trasferimento del codice.

4. Trasferire il codice di test.

   Poiché la portabilità in .NET Core è una modifica di rilievo per la base di codici, è consigliabile convertire i test per poterli eseguire durante la conversione del codice. MSTest, xUnit e NUnit supportano .NET Core.

5. Eseguire il piano di portabilità.

L'elenco seguente illustra gli strumenti che potrebbero risultare utili durante il processo di conversione:

* .NET Portability Analyzer: [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases) o [estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), una toolchain in grado di generare un report sulla portabilità del codice tra .NET Framework e .NET Core, con un'analisi dettagliata dei problemi basata sugli assembly. Per altre informazioni, vedere [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md).
* Analizzatore di API .NET: analizzatore Roslyn che individua potenziali rischi di compatibilità per le API C# in piattaforme diverse e rileva le chiamate alle API deprecate. Per altre informazioni, vedere [Analizzatore di API .NET](../../standard/analyzers/api-analyzer.md).
* Reverse Package Search: un [servizio Web utile](https://packagesearch.azurewebsites.net) che consente di eseguire le ricerche in base al tipo e di trovare pacchetti contenenti tale tipo.

È anche possibile provare a convertire soluzioni più piccole o singoli progetti al formato di file di progetto .NET Core con lo strumento [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).

> [!WARNING] 
> CsprojToVs2017 è uno strumento di terze parti. Non è garantito che funzioni per tutti i progetti e potrebbe causare lievi modifiche del comportamento di cui si dipende. CsprojToVs2017 deve essere usato come _punto iniziale_ che automatizza gli elementi di base che possono essere automatizzati. Non è una soluzione garantita per la migrazione dei formati di file di progetto.

>[!div class="step-by-step"]
>[avanti](net-framework-tech-unavailable.md)
