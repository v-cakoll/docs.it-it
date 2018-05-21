---
title: Quando scegliere .NET Framework per i contenitori Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Quando scegliere .NET Framework per i contenitori Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: e707c8f0e721915e829e41628891928594010b92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Quando scegliere .NET Framework per i contenitori Docker

Sebbene .NET Core offra vantaggi significativi per le nuove applicazioni e i nuovi schemi di applicazioni, .NET Framework continua a rappresentare la scelta naturale per molti scenari esistenti.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Migrazione delle applicazioni esistenti direttamente in un contenitore Windows Server

È possibile usare i contenitori Docker anche solo per semplificare la distribuzione, pur non creando microservizi. Ad esempio, se si vuole migliorare il flusso DevOps con Docker, i contenitori possono offrire ambienti di test con un isolamento migliore ed eliminare i problemi di distribuzione causati da dipendenze mancanti al momento dello spostamento in un ambiente di produzione. In questi casi, anche se si distribuisce un'applicazione monolitica, è consigliabile usare Docker e i contenitori Windows per le applicazioni .NET Framework correnti.

Nella maggior parte dei casi per questo scenario, non sarà necessario eseguire la migrazione delle applicazioni esistenti a .NET Core. È possibile usare contenitori Docker che includono .NET Framework tradizionale. Tuttavia, un approccio consigliato prevede di usare .NET Core per estendere un'applicazione esistente, ad esempio con la scrittura di un nuovo servizio in ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Utilizzo di pacchetti NuGet o di librerie .NET di terze parti non disponibili per .NET Core

Le librerie di terze parti stanno rapidamente adottando [.NET Standard](../../net-standard.md), che consente la condivisione di codice tra tutte le versioni di .NET incluso .NET Core. Con la libreria .NET Standard 2.0 e versioni successive, la compatibilità della superficie dell'API tra framework diversi è aumentata in modo significativo e nelle applicazioni .NET Core 2.0 può anche fare riferimento direttamente alle librerie .NET Framework esistenti (vedere la [compatibilità delle versioni](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).

Tuttavia, nonostante questo avanzamento eccezionale a partire da .NET Standard 2.0 e .NET Core 2.0, in determinati casi per eseguire alcuni pacchetti NuGet potrebbe essere necessario usare Windows perché questi non supportano .NET Core. Se questi pacchetti sono vitali per l'applicazione, sarà necessario usare .NET Framework in contenitori Windows.

## <a name="using-net-technologies-not-available-for-net-core"></a>Utilizzo di tecnologie .NET non disponibili per .NET Core 

Alcune tecnologie .NET Framework non sono disponibili nella versione corrente di .NET Core, ovvero la versione 2.0 al momento della stesura del presente documento. Alcune saranno disponibili in versioni future di .NET Core (.NET Core 2.x), ma altre non si applicano ai nuovi schemi di applicazioni basati su .NET Core ed è possibile che non vengano mai rese disponibili.

L'elenco seguente mostra la maggior parte delle tecnologie non disponibili in .NET Core 2.0:

-   Web Form ASP.NET. Questa tecnologia è disponibile solo in .NET Framework. Attualmente non è previsto il trasferimento di Web Form ASP.NET in .NET Core.

-   Servizi WCF. Anche quando una [libreria client WCF](https://github.com/dotnet/wcf) è disponibile per l'utilizzo di servizi WCF da .NET Core. Alla metà del 2017, l'implementazione del server WCF è disponibile solo in .NET Framework. Questo scenario potrebbe essere considerato per le versioni future di .NET Core.

-   Servizi correlati ai flussi di lavoro. Windows Workflow Foundation (WF), Servizi flusso di lavoro (WCF e WF in un unico servizio) e WCF Data Services (in precedenza "ADO.NET Data Services") sono disponibili solo in .NET Framework. Al momento non è prevista l'introduzione in .NET Core.

Oltre alle tecnologie elencate nella [roadmap per .NET Core](https://github.com/aspnet/Home/wiki/Roadmap) ufficiale, è possibile che in .NET Core vengano rese disponibili altre funzionalità. Per un elenco completo, osservare gli elementi contrassegnati come [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) nella pagina CoreFX del sito GitHub. Si noti che questo elenco non rappresenta un impegno da parte di Microsoft per rendere disponibili tali componenti in .NET Core, ma mostra solo il desiderio della community di procedere in tal senso. Se si è interessati a uno dei componenti elencati in precedenza, è consigliabile partecipare alle discussioni su GitHub per far valere la propria opinione. Inoltre, se si ritiene di dover aggiungere alcune osservazioni, è possibile [inserire un nuovo problema nel repository CoreFX](https://github.com/dotnet/corefx/issues/new).

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>Utilizzo di una piattaforma o di un'API che non supporta .NET Core

Alcune piattaforme Microsoft o di terze parti non supportano .NET Core. Ad esempio, alcuni servizi di Azure forniscono un SDK non ancora disponibile per l'utilizzo in .NET Core. Si tratta di un problema temporaneo, perché alla fine tutti i servizi di Azure useranno .NET Core. Ad esempio, [Azure DocumentDB SDK per .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) è stato rilasciato in anteprima il 16 novembre 2016 e ora è disponibile a livello generale come versione stabile.

Nel frattempo, se una piattaforma o un servizio in Azure ancora non supporta .NET Core tramite l'API client, è possibile usare l'API REST equivalente del servizio di Azure o l'SDK client in .NET Framework.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **.NET Core Guide**
    [*https://docs.microsoft.com/dotnet/core/index*](../../../core/index.md) (Guida a .NET Core)

-   **Porting from .NET Framework to .NET Core**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](../../../core/porting/index.md) (Portabilità da .NET Framework a .NET Core)

-   **.NET Framework on Docker Guide**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](../../../framework/docker/index.md) (Guida a .NET Framework su Docker)

-   **.NET Components Overview**
    [*https://docs.microsoft.com/dotnet/standard/components*](../../components.md) (Panoramica dei componenti .NET)




>[!div class="step-by-step"]
[Indietro] (net-core-container-scenarios.md) [Avanti] (container-framework-choice-factors.md)
