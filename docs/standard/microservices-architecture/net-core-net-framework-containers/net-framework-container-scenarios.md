---
title: Quando scegliere .NET Framework per contenitori di Docker
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Quando scegliere .NET Framework per contenitori di Docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1bf1f055f040e7f3dc575b7a04140ebf0c599f98
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Quando scegliere .NET Framework per contenitori di Docker

.NET Core offre vantaggi significativi per i modelli di applicazione e le nuove applicazioni, .NET Framework continueranno a essere una buona scelta per molti scenari esistenti.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Migrazione delle applicazioni esistenti direttamente a un contenitore di Windows Server

Si potrebbe voler usare i contenitori di Docker per semplificare la distribuzione, anche se non si siano creando microservizi. Ad esempio, ad esempio si desidera migliorare il flusso di lavoro di DevOps con Docker, contenitori può fornire migliori prova isolata ambienti e può anche eliminare i problemi di distribuzione causati da dipendenze mancanti quando si sposta in un ambiente di produzione. In questi casi anche se si distribuisce un'applicazione monolitica, è consigliabile usare Docker e i contenitori di Windows per le applicazioni .NET Framework corrente.

Nella maggior parte dei casi per questo scenario, non è necessario eseguire la migrazione delle applicazioni esistenti a .NET Core; è possibile utilizzare i contenitori di Docker che includono il tradizionale di .NET Framework. Tuttavia, un approccio consigliato è utilizzare .NET Core come si estende un'applicazione esistente, ad esempio la scrittura di un nuovo servizio in ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Utilizzo di librerie .NET di terze parti o pacchetti di NuGet non è disponibili per .NET Core

Librerie di terze parti sono rapidamente l'adozione di [.NET Standard](https://docs.microsoft.com/dotnet/standard/net-standard), che consente la condivisione tra tutte le versioni di .NET, tra cui .NET Core del codice. Con la libreria Standard .NET 2.0 e versioni successive la superficie dell'API compatibilità tra diversi Framework è diventato significativamente più grande e 2.0 di .NET Core applicazioni possono anche fare riferimento alle librerie .NET Framework esistente (vedere [compat shim](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).

Tuttavia, anche con tale progressione eccezionali rispetto a .NET Standard 2.0 e .NET Core 2.0, potrebbe esserci casi in cui è necessario eseguire alcuni pacchetti NuGet e potrebbero non supportare .NET Core. Se i pacchetti sono fondamentali per l'applicazione, è necessario utilizzare .NET Framework per contenitori di Windows.

## <a name="usingnet-technologies-not-available-for-net-core"></a>Tecnologie.NET non è disponibile per .NET Core 

Alcune tecnologie .NET Framework non sono disponibili nella versione corrente di .NET Core (versione 2.0 redazione del presente documento). Alcuni dei quali sarà disponibile nelle versioni successive di .NET Core (Core .NET 2. x), ma non altri si applicano alla nuova applicazione di modelli di destinazione di .NET Core e potrebbero non essere disponibili.

L'elenco seguente mostra la maggior parte delle tecnologie che non sono disponibili in .NET Core 2.0:

-   Web Form ASP.NET. Questa tecnologia è disponibile solo in .NET Framework. Attualmente non è previsto il trasferimento di Web Form ASP.NET in .NET Core.

-   Servizi WCF. Anche quando un [libreria Client WCF](https://github.com/dotnet/wcf) è in grado di utilizzare servizi WCF di .NET Core. a partire da mid 2017, l'implementazione WCF del server è disponibile solo in .NET Framework. Questo scenario può essere considerato per le versioni future di .NET Core.

-   Servizi correlati al flusso di lavoro. Windows Workflow Foundation (WF), servizi flussi di lavoro (WCF + WF in un singolo servizio) e WCF Data Services (precedentemente noto come ADO.NET Data Services) sono disponibili solo in .NET Framework. Non è attualmente previsto assegnarli a .NET Core.

Oltre alle tecnologie elencate nella ufficiali [roadmap .NET Core](https://github.com/aspnet/Home/wiki/Roadmap), altre funzionalità può essere trasferita a .NET Core. Per un elenco completo, esaminare gli elementi contrassegnati come [porta-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) sul sito CoreFX GitHub. Si noti che questo elenco non rappresenta un impegno di Microsoft per portare tali componenti .NET Core, le voci acquisiscono semplicemente richieste dalla community. Se si desidera uno qualsiasi dei componenti elencati sopra, prendere in considerazione che fanno parte le discussioni su GitHub in modo che la voce può essere ascoltata. Inoltre, se si ritiene di dover aggiungere alcune osservazioni, è possibile [inserire un nuovo problema nel repository CoreFX](https://github.com/dotnet/corefx/issues/new).

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>Utilizzo di una piattaforma o l'API che non supporta .NET Core

Alcuni Microsoft o le piattaforme di terze parti non supportano .NET Core. Ad esempio, alcuni servizi di Azure forniscono un SDK che non è ancora disponibile per l'utilizzo su .NET Core. Questo è temporaneo, perché tutti i servizi di Azure verranno usati .NET Core. Ad esempio, il [DocumentDB di Azure SDK per .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) è stato rilasciato come un'anteprima del 16 novembre 2016, ma ora è disponibile a livello generale (GA) come una versione stabile.

Nel frattempo, se tutte le piattaforme o servizio in Azure non supporta ancora .NET Core con l'API client, è possibile utilizzare l'API REST equivalente dal servizio di Azure o il client SDK in .NET Framework.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Guida di .NET core**
    [*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)

-   **Porting da .NET Framework a .NET Core**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)

-   **.NET framework nella Guida di Docker**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)

-   **Panoramica dei componenti .NET**
    [*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)




>[!div class="step-by-step"]
[Precedente] (net-core-contenitore-scenarios.md) [Avanti] (contenitore framework-scelta factors.md)
