---
title: Quando scegliere .NET Framework per i contenitori Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Quando scegliere .NET Framework per i contenitori Docker
ms.date: 01/30/2020
ms.openlocfilehash: dfb1e8883fc9c3d9235672bc2885858bfb64afa5
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501968"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Quando scegliere .NET Framework per i contenitori Docker

Sebbene .NET Core offra vantaggi significativi per le nuove applicazioni e i nuovi schemi di applicazioni, .NET Framework continua a rappresentare la scelta naturale per molti scenari esistenti.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Migrazione delle applicazioni esistenti direttamente in un contenitore Windows Server

È possibile usare i contenitori Docker anche solo per semplificare la distribuzione, pur non creando microservizi. Ad esempio, se si vuole migliorare il flusso DevOps con Docker, i contenitori possono offrire ambienti di test con un isolamento migliore ed eliminare i problemi di distribuzione causati da dipendenze mancanti al momento dello spostamento in un ambiente di produzione. In questi casi, anche se si distribuisce un'applicazione monolitica, è consigliabile usare Docker e i contenitori Windows per le applicazioni .NET Framework correnti.

Nella maggior parte dei casi per questo scenario, non sarà necessario eseguire la migrazione delle applicazioni esistenti a .NET Core. È possibile usare contenitori Docker che includono .NET Framework tradizionale. Tuttavia, un approccio consigliato prevede di usare .NET Core per estendere un'applicazione esistente, ad esempio con la scrittura di un nuovo servizio in ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Utilizzo di pacchetti NuGet o di librerie .NET di terze parti non disponibili per .NET Core

Le librerie di terze parti stanno rapidamente adottando [.NET standard](../../../standard/net-standard.md), che consente la condivisione del codice tra tutte le versioni di .NET, incluso .NET Core. Con .NET Standard 2,0 e versioni successive, la compatibilità della superficie dell'API nei diversi Framework è diventata significativamente più grande. Ancora più, .NET Core 2. x e le applicazioni più recenti possono anche fare riferimento direttamente alle librerie di .NET Framework esistenti (vedere [.NET Framework 4.6.1 che supporta .NET Standard 2,0](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#net-framework-461-supporting-net-standard-20)).

Inoltre, [Windows Compatibility Pack](../../../core/porting/windows-compat-pack.md) estende la superficie dell'API disponibile per .NET standard 2,0 in Windows. Questo pacchetto consente di ricompilare la maggior parte del codice esistente per .NET Standard 2.x con modifiche minime o nulle, da eseguire in Windows.

Tuttavia, nonostante questo avanzamento eccezionale a partire da .NET Standard 2.0 e .NET Core 2.1, in determinati casi per eseguire alcuni pacchetti NuGet potrebbe essere necessario usare Windows perché questi non supportano .NET Core. Se questi pacchetti sono vitali per l'applicazione, sarà necessario usare .NET Framework in contenitori Windows.

## <a name="using-net-technologies-not-available-for-net-core"></a>Utilizzo di tecnologie .NET non disponibili per .NET Core

Alcune tecnologie di .NET Framework non sono disponibili nella versione corrente di .NET Core (versione 3,1 al momento della stesura di questo articolo). Alcune di esse potrebbero diventare disponibili nelle versioni successive, ma altre non rientrano nei nuovi modelli di applicazione di destinazione di .NET Core e potrebbero non essere mai disponibili.

L'elenco seguente mostra la maggior parte delle tecnologie non disponibili in .NET Core 3,1:

- Web Form ASP.NET. Questa tecnologia è disponibile solo in .NET Framework. Attualmente non è previsto il trasferimento di Web Form ASP.NET in .NET Core.

- Servizi WCF. Anche quando una [libreria client WCF](https://github.com/dotnet/wcf) è disponibile per l'utilizzo di servizi WCF da .NET Core, a partire da Feb-2020, l'implementazione del server WCF è disponibile solo in .NET Framework. Questo scenario potrebbe essere considerato per le versioni future di .NET Core. Anche alcune API sono considerate per l'inclusione in [Windows Compatibility Pack](../../../core/porting/windows-compat-pack.md).

- Servizi correlati ai flussi di lavoro. Windows Workflow Foundation (WF), Servizi flusso di lavoro (WCF e WF in un unico servizio) e WCF Data Services (in precedenza "ADO.NET Data Services") sono disponibili solo in .NET Framework. Al momento non è prevista l'introduzione in .NET Core.

Oltre alle tecnologie elencate nella [Roadmap di .NET Core](https://github.com/dotnet/core/blob/master/roadmap.md)ufficiale, altre funzionalità possono essere trasferite a .NET Core o alla nuova [piattaforma .NET unificata](https://devblogs.microsoft.com/dotnet/introducing-net-5/). È possibile prendere in considerazione la partecipazione alle discussioni su GitHub in modo che sia possibile ascoltare la voce. Se si ritiene che qualcosa non sia presente, archiviare un nuovo problema nel repository GitHub [DotNet/Runtime](https://github.com/dotnet/runtime/issues/new) .

## <a name="using-a-platform-or-api-that-doesnt-support-net-core"></a>Uso di una piattaforma o di un'API che non supporta .NET Core

Alcune piattaforme Microsoft e di terze parti non supportano .NET Core. Alcuni servizi di Azure, ad esempio, forniscono un SDK che non è ancora disponibile per l'utilizzo in .NET Core. La maggior parte di Azure SDK dovrebbe essere successivamente trasferita a .NET Core/standard, ma alcune potrebbero non per diversi motivi. È possibile visualizzare gli SDK di Azure disponibili nella pagina delle [versioni più recenti di Azure SDK](https://azure.github.io/azure-sdk/releases/latest/index.html) .

Nel frattempo, se una piattaforma o un servizio in Azure ancora non supporta .NET Core tramite l'API client, è possibile usare l'API REST equivalente del servizio di Azure o l'SDK client in .NET Framework.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Guida a .NET Core** \
  [https://docs.microsoft.com/dotnet/core/index](../../../core/index.md)

- **Porting from .NET Framework to .NET Core** \ (Portabilità da .NET Framework a .NET Core)
  [https://docs.microsoft.com/dotnet/core/porting/index](../../../core/porting/index.md)

- **Guida a .NET Core in docker** \
  [https://docs.microsoft.com/dotnet/core/docker/introduction](../../../core/docker/introduction.md)

- **Componenti dell'architettura .NET** \
  [https://docs.microsoft.com/dotnet/standard/components](../../../standard/components.md)

>[!div class="step-by-step"]
>[Precedente](net-core-container-scenarios.md)
>[Successivo](container-framework-choice-factors.md)
