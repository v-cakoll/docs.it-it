---
title: Creazione dell'interfaccia utente composita basata su microservizi
description: L'architettura di microservizi non è destinata solo al back-end. Di seguito se ne analizza brevemente l'uso nei contesti front-end.
ms.date: 09/20/2018
ms.openlocfilehash: 1861d3bb6e5d4a0226aa8f3f72a2e0d3e83be56f
ms.sourcegitcommit: 992f80328b51b165051c42ff5330788627abe973
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2019
ms.locfileid: "72275735"
---
# <a name="creating-composite-ui-based-on-microservices"></a>Creazione dell'interfaccia utente composita basata su microservizi

L'architettura di microservizi spesso inizia con la gestione dei dati e della logica sul lato server, ma in molti casi l'interfaccia utente viene ancora gestita come Monolith. Tuttavia, un approccio più avanzato, denominato [micro](https://martinfowler.com/articles/micro-frontends.html)-front-end, consiste nel progettare l'interfaccia utente dell'applicazione in base ai microservizi. Ciò significa avere un'interfaccia utente composita generata dai microservizi, invece di avere i microservizi sul server e solo un'app client monolitica che utilizza i microservizi. Con questo approccio, i microservizi creati possono essere completati con la rappresentazione sia logica che visiva.

La figura 4-20 illustra l'approccio più semplice in cui i microservizi vengono utilizzati da un'applicazione client monolitica. Nel mezzo è ovviamente possibile avere un servizio MVC ASP.NET che genera il codice HTML e JavaScript. La figura è una rappresentazione semplificata che evidenzia la presenza di una sola interfaccia utente client (monolitica) che utilizza i microservizi, concentrati solo sulla logica e sui dati e non sulla forma dell'interfaccia utente (HTML e JavaScript).

![Diagramma di un'app di interfaccia utente monolitica che si connette ai microservizi.](./media/microservice-based-composite-ui-shape-layout/monolith-ui-consume-microservices.png)

**Figura 4-20**. Applicazione dell'interfaccia utente monolitica che utilizza i microservizi back-end

Un'interfaccia utente composita viene invece generata con precisione ed è composta dai microservizi stessi. Alcuni dei microservizi gestiscono la forma visiva di aree specifiche dell'interfaccia utente. La differenza principale è che sono presenti componenti dell'interfaccia utente client (ad esempio, le classi TypeScript) basati su modelli e che l'elemento dell'interfaccia utente di data shaping ViewModel di tali modelli deriva da ogni microservizio.

Durante l'avvio dell'applicazione client, ognuno dei componenti dell'interfaccia utente client (ad esempio, le classi TypeScript) si registra con un microservizio dell'infrastruttura in grado di fornire ViewModel per un determinato scenario. Se la forma del microservizio cambia, anche l'interfaccia utente cambia.

La figura 4-21 illustra una versione di questo approccio basato sull'interfaccia utente composita. La visualizzazione è semplificata, perché si potrebbe disporre di altri microservizi che aggregano parti granulari basate su tecniche diverse. Questo dipende dal fatto che si stia creando un approccio Web tradizionale (MVC ASP.NET) o un'applicazione a pagina singola (SPA, Single Page Application).

![Diagramma di un'interfaccia utente composita costituita da molti modelli di visualizzazione.](./media/microservice-based-composite-ui-shape-layout/microservice-generate-composite-ui.png)

**Figura 4-21**. Esempio di applicazione con interfaccia utente composita modellata da microservizi back-end

Ogni microservizio di composizione dell'interfaccia utente dovrebbe essere simile a un gateway API di piccole dimensioni,. Ma in questo caso ognuno è responsabile di una piccola area dell'interfaccia utente.

Un approccio basato sull'interfaccia utente composita gestito dai microservizi può essere più o meno complesso a seconda delle tecnologie usate per l'interfaccia utente. Per compilare un' applicazione Web tradizionale, ad esempio, non si usano le stesse tecniche usate per compilare un'applicazione a pagina singola o per le app per dispositivi mobili native (come nello sviluppo di app Xamarin, che può essere più complesso con questo approccio).

L'applicazione di esempio [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) usa l'approccio basato sull'interfaccia utente monolitica per più motivi. Prima di tutto è un'introduzione a microservizi e contenitori. Un'interfaccia utente composita è più avanzata, ma presenta anche un livello di complessità più elevato quando si progetta e sviluppa l'interfaccia utente. In secondo luogo, eShopOnContainers fornisce anche un'app per dispositivi mobili nativa basata su Xamarin, che ne aumenterà la complessità sul lato C\# del client.

Per altre informazioni sull'interfaccia utente composita basata sui microservizi, è consigliabile vedere i riferimenti seguenti.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Micro front-end (Blog di Martin Fowler)**  
  <https://martinfowler.com/articles/micro-frontends.html>
  
- **Micro-front-end (sito Michael Geers)**  
  <https://micro-frontends.org/>
  
- **Interfaccia utente composita con ASP.NET (officina particolare)**  
  <https://github.com/Particular/Workshop/tree/master/demos/asp-net-core>

- **Ruben Oostinga. Front-end monolitico nell'architettura di microservizi @ no__t-0  
  <https://xebia.com/blog/the-monolithic-frontend-in-the-microservices-architecture/>

- **Mauro Servienti. Il segreto di una migliore composizione dell'interfaccia utente @ no__t-0  
  <https://particular.net/blog/secret-of-better-ui-composition>

- **Viktor Farcic. Inclusione di componenti Web front-end in microservizi @ no__t-0  
  <https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/>

- **Gestione di front-end nell'architettura di microservizi**  
  <https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html>

>[!div class="step-by-step"]
>[Precedente](microservices-addressability-service-registry.md)
>[Successivo](resilient-high-availability-microservices.md)
