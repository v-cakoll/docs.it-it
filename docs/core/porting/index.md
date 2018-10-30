---
title: Portabilità in .NET Core da .NET Framework
description: Informazioni sul processo di trasferimento e sugli strumenti che possono risultare utili durante il trasferimento di un progetto .NET Framework in .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 10/23/2018
ms.openlocfilehash: 0c0ec3d8ab09e34e8dae24623903ca571f2cca6c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50192772"
---
# <a name="porting-to-net-core-from-net-framework"></a>Portabilità in .NET Core da .NET Framework

Se è disponibile codice per .NET Framework, si potrebbe essere interessati a eseguirlo in .NET Core.  Questo articolo illustra una panoramica del processo di trasferimento e un elenco degli strumenti che possono risultare utili durante il trasferimento in .NET Core.

## <a name="overview-of-the-porting-process"></a>Panoramica del processo di trasferimento

Il processo consigliato per la portabilità fa riferimento alla serie di passaggi seguenti.  Ogni parte del processo è descritta più dettagliatamente in ulteriori articoli.

1. Identificare e spiegare le dipendenze di terze parti.

   Questo passaggio comporterà la comprensione delle dipendenze di terze parti, della dipendenza dell'utente da queste ultime, di come verificare se vengono eseguite anche su .NET Core e dei passaggi da eseguire in caso contrario.
   
2. Ridestinare tutti i progetti che si desidera trasferire alla versione più recente di .NET Framework.

   Questo passaggio garantisce che si possano usare le alternative di API per le destinazioni specifiche di .NET Framework nei casi in cui .NET Core non supporta un'API specifica.
   
3. Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per analizzare gli assembly e sviluppare un piano per eseguire il trasferimento in base ai risultati ottenuti.

   Lo strumento API Portability Analyzer analizza gli assembly compilati e genera un report che mostra un riepilogo a elevato livello di portabilità e un'analisi dettagliata di ogni API in uso non disponibile in .NET Core.  È possibile usare questo report insieme a un'analisi della base di codici per sviluppare un piano per il trasferimento del codice.
   
4. Trasferire il codice di test.

   Poiché la portabilità in .NET Core è una modifica di rilievo per la base di codici, è consigliabile effettuare la portabilità dei test in modo da eseguirli durante il trasferimento del codice.  Attualmente MSTest, xUnit e NUnit supportano .NET Core.
   
6. Eseguire il piano di portabilità.

## <a name="tools-to-help"></a>Strumenti utili

Di seguito è riportato un breve elenco degli strumenti che possono risultare utili:

* NuGet: [Nuget Client](https://dist.nuget.org/index.html) o [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), gestione di pacchetti Microsoft per le implementazioni di .NET.
* API Portability Analyzer: [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases) o [estensione di Visual Studio](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), una toolchain in grado di generare un report sulla portabilità del codice tra .NET Framework e .NET Core, con un'analisi dettagliata dei problemi basata sugli assembly.  Per altre informazioni, vedere [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) (Strumenti utili per il processo).
* Reverse Package Search: un [servizio Web utile](https://packagesearch.azurewebsites.net) che consente di eseguire le ricerche in base al tipo e di trovare pacchetti contenenti tale tipo.

## <a name="next-steps"></a>Passaggi successivi

[Analyzing your third-party dependencies](third-party-deps.md) (Analisi delle dipendenze di terze parti)
   
