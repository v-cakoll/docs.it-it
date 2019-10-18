---
title: Convertire il codice da .NET Framework a .NET Core
description: Informazioni sul processo di trasferimento e sugli strumenti che possono risultare utili durante il trasferimento di un progetto .NET Framework in .NET Core.
author: cartermp
ms.date: 09/13/2019
ms.custom: seodec18
ms.openlocfilehash: c349f7df3726e7a9814e5ad5e738742ab1bb9ff8
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522994"
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

   Lo strumento API Portability Analyzer analizza gli assembly compilati e genera un report che mostra un riepilogo di portabilità di alto livello e una suddivisione di ogni API in uso che non è disponibile nell'area pubblica della piattaforma .NET Core di destinazione. È possibile usare questo report insieme a un'analisi della base di codici per sviluppare un piano per il trasferimento del codice.

4. Una volta che il file di progetto è stato convertito nella versione di .NET Core di destinazione, è possibile usare l' [analizzatore di API .NET](../../standard/analyzers/api-analyzer.md) basato su Roslyn per identificare le API che generano <xref:System.PlatformNotSupportedException> in alcune piattaforme e altri potenziali problemi di compatibilità.

5. Trasferire il codice di test.

   Poiché la portabilità in .NET Core è una modifica di rilievo per la base di codici, è consigliabile convertire i test per poterli eseguire durante la conversione del codice. MSTest, xUnit e NUnit supportano .NET Core.

6. Eseguire il piano di portabilità.

L'elenco seguente illustra gli strumenti che potrebbero risultare utili durante il processo di conversione:

- .NET Portability Analyzer: [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases) o estensione di [Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), uno strumento che consente di generare un report del modo in cui il codice è portabile tra .NET Framework e la piattaforma .NET Core di destinazione. Il report contiene una scomposizione per assembly del tipo e le API mancanti nella piattaforma .NET Core di destinazione. Per altre informazioni, vedere [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md). È consigliabile eseguire lo strumento .NET Portability Analyzer prima di iniziare il porting, in quanto consente di identificare eventuali gap nelle API mancanti in una specifica area pubblica della piattaforma .NET di destinazione.
- Analizzatore di API .NET: analizzatore Roslyn che rileva le API .NET Standard che producono <xref:System.PlatformNotSupportedException> in determinate piattaforme, rileva chiamate ad API deprecate e individua altri potenziali rischi di compatibilità per le API C# in piattaforme diverse. Per altre informazioni, vedere [Analizzatore di API .NET](../../standard/analyzers/api-analyzer.md). Questo analizzatore è utile dopo che già stato creato il progetto .NET Core per identificare le differenze di comportamento di runtime su piattaforme diverse.
- Reverse Package Search: un [servizio Web utile](https://packagesearch.azurewebsites.net) che consente di eseguire le ricerche in base al tipo e di trovare pacchetti contenenti tale tipo.

È anche possibile provare a convertire soluzioni più piccole o singoli progetti al formato di file di progetto .NET Core con lo strumento [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).

> [!WARNING]
> CsprojToVs2017 è uno strumento di terze parti. Non è garantito che funzioni per tutti i progetti e potrebbe causare lievi modifiche del comportamento di cui si dipende. CsprojToVs2017 deve essere usato come _punto iniziale_ che automatizza gli elementi di base che possono essere automatizzati. Non è una soluzione garantita per la migrazione dei formati di file di progetto.

>[!div class="step-by-step"]
>[avanti](net-framework-tech-unavailable.md)
