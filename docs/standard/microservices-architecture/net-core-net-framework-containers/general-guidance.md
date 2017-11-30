---
title: Indicazioni generali
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Indicazioni generali
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a>Indicazioni generali

In questa sezione fornisce un riepilogo del momento in cui scegliere .NET Framework o .NET Core. Sono forniti ulteriori dettagli su queste opzioni nelle sezioni che seguono.

Utilizzare .NET Core, con i contenitori di Windows, o Linux per l'applicazione nei contenitori di Docker server quando:

-   Si hanno esigenze multipiattaforma. Ad esempio, si desidera utilizzare i contenitori di Windows e Linux.

-   L'architettura dell'applicazione si basa su microservizi.

-   È necessario avviare fast contenitori e desidera un footprint ridotto per ogni contenitore per ottenere una migliore densità o più contenitori per unità di hardware, per ridurre i costi.

In breve, quando si creano nuove applicazioni .NET nei contenitori, è necessario considerare .NET Core come scelta predefinita. Dispone di numerosi vantaggi e più appropriato per la filosofia di contenitori e lo stile di lavoro.

Un ulteriore vantaggio dell'utilizzo di .NET Core è possibile eseguire side-by versioni di .NET per le applicazioni all'interno della macchina stessa. Questo vantaggio è più importante per i server o le macchine virtuali che non utilizzano contenitori, perché le versioni di .NET che l'app è necessario isolare i contenitori. (Purché siano compatibili con il sistema operativo sottostante).

Utilizzare .NET Framework, i contenitori di Windows per l'applicazione nei contenitori di Docker server quando:

-   L'applicazione attualmente Usa .NET Framework e è associate dipendenze complesse in Windows.

-   È necessario usare le API di Windows che non sono supportati da .NET Core.

-   È necessario utilizzare le librerie .NET di terze parti o pacchetti NuGet che non sono disponibili per .NET Core.

L'utilizzo di .NET Framework in Docker può migliorare le esperienze di distribuzione riducendo al minimo i problemi di distribuzione. Questo [ *"sollevare e spostare" scenario* ](https://aka.ms/liftandshiftwithcontainersebook) è importante per le applicazioni legacy che sono stati originariamente sviluppate con .NET Framework tradizionale, quali Web Form ASP.NET, MVC web App o WCF (containerizing Servizi Windows Communication Foundation).

### <a name="additional-resources"></a>Risorse aggiuntive

-   **e-book: modernizzare le applicazioni .NET Framework esistenti e i contenitori di Windows Azure**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)

-   **App di esempio: moderna del App web ASP.NET legacy usando i contenitori di Windows**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)


>[!div class="step-by-step"]
[Precedente] [Avanti] (net core-contenitore scenarios.md) (index.md)
