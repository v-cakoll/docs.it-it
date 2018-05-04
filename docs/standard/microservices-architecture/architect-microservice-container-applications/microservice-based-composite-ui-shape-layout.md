---
title: Creazione dell'interfaccia utente composita basata su microservizi, tra cui la forma visiva dell'interfaccia utente e il layout generato da più microservizi
description: Architettura dei microservizi .NET per le applicazioni .NET in contenitori | Creazione dell'interfaccia utente composita basata su microservizi, tra cui la forma visiva dell'interfaccia utente e il layout generato da più microservizi
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 55b643fa6f87e5e2b1f49ba201032df655195b46
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices"></a>Creazione dell'interfaccia utente composita basata su microservizi, tra cui la forma visiva dell'interfaccia utente e il layout generato da più microservizi

L'architettura dei microservizi inizia spesso con la gestione dei dati e la logica lato server. Un approccio più avanzato prevede tuttavia la progettazione dell'interfaccia utente dell'applicazione basata anche sui microservizi. Ciò significa avere un'interfaccia utente composita generata dai microservizi, invece di avere i microservizi sul server e solo un'app client monolitica che utilizza i microservizi. Con questo approccio, i microservizi creati possono essere completati con la rappresentazione sia logica che visiva.

La figura 4-20 illustra l'approccio più semplice in cui i microservizi vengono utilizzati da un'applicazione client monolitica. Nel mezzo è ovviamente possibile avere un servizio MVC ASP.NET che genera il codice HTML e JavaScript. La figura è una rappresentazione semplificata che evidenzia la presenza di una sola interfaccia utente client (monolitica) che utilizza i microservizi, concentrati solo sulla logica e sui dati e non sulla forma dell'interfaccia utente (HTML e JavaScript).

![](./media/image20.png)

**Figura 4-20**. Applicazione dell'interfaccia utente monolitica che utilizza i microservizi back-end

Un'interfaccia utente composita viene invece generata con precisione ed è composta dai microservizi stessi. Alcuni dei microservizi gestiscono la forma visiva di aree specifiche dell'interfaccia utente. La differenza principale è che si hanno componenti dell'interfaccia utente client (ad esempio, le classi TS) basati su modelli e che l'elemento ViewModel dell'interfaccia utente di data shaping di tali modelli deriva da ogni microservizio.

Durante l'avvio dell'applicazione client, ognuno dei componenti dell'interfaccia utente client (ad esempio, le classi TypeScript) si registra con un microservizio dell'infrastruttura in grado di fornire ViewModel per un determinato scenario. Se la forma del microservizio cambia, anche l'interfaccia utente cambia.

La figura 4-21 illustra una versione di questo approccio basato sull'interfaccia utente composita. La figura è semplificata, perché è possibile avere altri microservizi che aggregano parti granulari in base a tecniche diverse, a seconda del fatto che si stia creando un tradizionale approccio Web (MVC ASP.NET) o un'applicazione a pagina singola.

![](./media/image21.png)

**Figura 4-21**. Esempio di applicazione con interfaccia utente composita modellata da microservizi back-end

Ogni microservizio di composizione dell'interfaccia utente dovrebbe essere simile a un gateway API di piccole dimensioni,. ma in questo caso ognuno è responsabile di una piccola area dell'interfaccia utente.

Un approccio basato sull'interfaccia utente composita gestito dai microservizi può essere più o meno complesso a seconda delle tecnologie usate per l'interfaccia utente. Per compilare una tradizionale applicazione Web, ad esempio, non si useranno le stesse tecniche usate per compilare un'applicazione a pagina singola o per le app per dispositivi mobili native (come nello sviluppo di app Xamarin, che può essere più complesso per questo approccio).

L'applicazione di esempio [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) usa l'approccio basato sull'interfaccia utente monolitica per più motivi. Prima di tutto, è un'introduzione a microservizi e contenitori. Un'interfaccia utente composita è più avanzata, ma presenta anche un livello di complessità più elevato quando si progetta e sviluppa l'interfaccia utente. In secondo luogo, eShopOnContainers fornisce anche un'app per dispositivi mobili nativa basata su Xamarin, che ne aumenterà la complessità sul lato C\# del client.

Per altre informazioni sull'interfaccia utente composita basata sui microservizi, è consigliabile vedere i riferimenti seguenti.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Composite UI using ASP.NET (Interfaccia utente composita con ASP.NET - Workshop di Particular)**
    [*http://go.particular.net/workshop-composite-ui-demo*](http://go.particular.net/workshop-composite-ui-demo)

-   **Ruben Oostinga. The Monolithic Frontend in the Microservices Architecture**
    [*http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/*](http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/) (Front-end monolitico nell'architettura di microservizi)

-   **Mauro Servienti. The secret of better UI composition**
    [*https://particular.net/blog/secret-of-better-ui-composition*](https://particular.net/blog/secret-of-better-ui-composition) (Il segreto per una composizione ideale dell'interfaccia utente)

-   **Viktor Farcic. Including Front-End Web Components Into Microservices**
    [*https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/*](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/) (Inserimento di componenti Web front-end nei microservizi)

-   **Managing Frontend in the Microservices Architecture**\ (Gestione del front-end nell'architettura di microservizi)
    [*https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html*](https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)


>[!div class="step-by-step"]
[Indietro] (microservices-addressability-service-registry.md) [Avanti] (resilient-high-availability-microservices.md)
