---
title: "Creazione composito dell'interfaccia utente basata su microservizi, tra cui visual forma dell'interfaccia utente e il layout generato da più microservizi"
description: "Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Creazione composito dell'interfaccia utente basata su microservizi, tra cui visual forma dell'interfaccia utente e il layout generato da più microservizi"
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4b32fed5eb0de02b01665efa4368eb83e3fda08d
ms.sourcegitcommit: e99dfadbca1992c187179b6a3b42bef44534ebb6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2017
---
# <a name="creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices"></a>Creazione composito dell'interfaccia utente basata su microservizi, tra cui visual forma dell'interfaccia utente e il layout generato da più microservizi

Architettura Microservizi è spesso inizia con la gestione di dati e logica lato server. Tuttavia, un approccio più avanzato consiste nel progettare l'applicazione che dell'interfaccia utente basata su microservizi anche. Ciò significa che un'interfaccia utente composta prodotta da di microservizi, invece di dover microservizi sul server e l'utilizzo di microservizi solo un'app client monolitico. Con questo approccio, il microservizi che compili possono essere completata con la logica e rappresentazione visiva.

Figura 4-20 viene illustrato l'approccio più semplice di utilizzo solo di microservizi da un'applicazione client monolitico. Naturalmente, è possibile che un servizio ASP.NET MVC tra che produce il codice HTML e JavaScript. Nella figura è una semplificazione che evidenzia la presenza di un singolo client (monolitico) dell'interfaccia utente di utilizzo di microservizi, che consente di concentrarsi solo su logica e i dati e non sulla forma dell'interfaccia utente (HTML e JavaScript).

![](./media/image20.png)

**Figura 4-20**. Un'applicazione dell'interfaccia utente monolitica utilizzo microservizi back-end

Al contrario, una composito dell'interfaccia utente è precisamente generata e composto da microservizi autonomamente. Alcune di microservizi guidare la forma visual di aree specifiche dell'interfaccia utente. La differenza principale è che sono componenti dell'interfaccia utente di client (classi di Servizi terminal, ad esempio) basati su modelli e ViewModel il data shaping-dell'interfaccia utente per i modelli proviene da ogni microservizio.

In fase di avvio dell'applicazione client, ciascuno dei componenti dell'interfaccia utente client (classi TypeScript, ad esempio) registra se stesso con un microservizio di infrastruttura in grado di fornire ViewModel per un determinato scenario. Se il microservizio assume la forma, viene modificato anche l'interfaccia utente.

Figura 4-21 viene illustrata una versione di questo approccio dell'interfaccia utente composta. Per semplificare questo processo, perché sono possibili altri microservizi che siano eseguendo l'aggregazione granulare parti in base a diverse tecniche, a seconda se si compila un approccio tradizionale web (ASP.NET MVC) o un SPA (applicazione a pagina singola).

![](./media/image21.png)

**Figura 4-21**. Esempio di un'applicazione dell'interfaccia utente composta modellata da microservizi back-end

Ognuno di tali microservizi di composizione dell'interfaccia utente sarà simile a un Gateway di API di piccole dimensioni. Ma in questo caso ogni è responsabile di una piccola area dell'interfaccia utente.

Un approccio dell'interfaccia utente composito che si basano sui microservizi può risultare più difficile o meno in tal caso, a seconda di quali tecnologie dell'interfaccia utente in uso. Ad esempio, non utilizzare le stesse tecniche per la creazione di un'applicazione web tradizionali utilizzati per la creazione di un SPA o App native per dispositivi mobili (come quando si sviluppano applicazioni di Xamarin, che possono essere più complessa per questo approccio).

Il [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) applicazione di esempio utilizza l'approccio monolitico di interfaccia utente per diversi motivi. Innanzitutto, si tratta di un'introduzione ai contenitori e microservizi. Una composito dell'interfaccia utente più avanzata, ma richiede anche ulteriori complessità durante la progettazione e sviluppo dell'interfaccia utente. In secondo luogo, eShopOnContainers fornisce inoltre un'app mobile nativa basata su Xamarin, che possono rendere più complessa nel client C\# lato.

Tuttavia, si consiglia di utilizzare i riferimenti seguenti per ulteriori informazioni su composito che dell'interfaccia utente in base a microservizi.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Composito dell'interfaccia utente usando ASP.NET (del particolare Workshop)**
    [*http://go.particular.net/workshop-composite-ui-demo*](http://go.particular.net/workshop-composite-ui-demo)

-   **Ruben Oostinga. Il front-end monolitico nell'architettura di Microservizi**
    [*http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/*](http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/)

-   **Mauro Servienti. Il segreto di composizione dell'interfaccia utente migliore**
    [*https://particular.net/blog/secret-of-better-ui-composition*](https://particular.net/blog/secret-of-better-ui-composition)

-   **Viktor Farcic. Inclusi i componenti front-end Web in Microservizi**
    [*https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/*](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/)

-   **Gestione dei server front-end nell'architettura di Microservizi**\
    [*http://Allegro.Tech/2016/03/Managing-Frontend-in-the-microservices-Architecture.HTML*](http://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)


>[!div class="step-by-step"]
[Precedente] (microservizi-indirizzabilità-servizio-registry.md) [Avanti] (resilienti-elevata-disponibilità-microservices.md)
