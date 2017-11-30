---
title: Comunicazione client-a-microservizio diretta e il modello API Gateway
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Comunicazione client-a-microservizio diretta e il modello API Gateway
keywords: Docker, Microservizi, ASP.NET, contenitore, il Gateway API
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8227ec47888c7cf361f34c4c85a09c0666f886e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="direct-client-to-microservice-communication-versus-the-api-gateway-pattern"></a>Comunicazione client-a-microservizio diretta e il modello API Gateway

In un'architettura di microservizi, ogni microservizio espone un set di endpoint di fine‑grained (in genere). Ciò può influire sulla comunicazione client‑to‑microservice, come illustrato in questa sezione.

## <a name="direct-client-to-microservice-communication"></a>Comunicazione client-a-microservizio diretta

Un possibile approccio consiste nell'utilizzare un'architettura di comunicazione client-a-microservizio diretta. In questo caso, un'app client può effettuare richieste direttamente ad alcune delle microservizi, come illustrato nella figura 4-12.

![](./media/image12.png)

**Figura 4-12**. Utilizzo di un'architettura di comunicazione client-a-microservizio diretta

In questo approccio. ogni microservizio dispone di un endpoint pubblico, talvolta con una porta TCP diversa per ogni microservizio. Un esempio di un URL per un determinato servizio potrebbe essere l'URL seguente in Azure:

<http://eshoponcontainers.westus.cloudapp.Azure.com:88 />

In un ambiente di produzione in base a un cluster, che consente il mapping di URL per il bilanciamento del carico utilizzato nel cluster, che a sua volta consente di distribuire le richieste di microservizi. In ambienti di produzione, è possibile disporre di un Controller di recapito dell'applicazione (ADC) come [Gateway applicazione Azure](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction) tra il microservizi e Internet. Questa funzione agisce come un livello trasparente che non solo consente di eseguire il bilanciamento del carico, ma consente di proteggere i servizi tramite l'offerta di terminazione SSL. Ciò migliora il carico degli host tramite l'offload della terminazione SSL con utilizzo intensivo della CPU e altre funzioni di routing al Gateway applicazione Azure. In ogni caso, un servizio di bilanciamento del carico e il servizio ADC sono trasparenti da un punto di vista di logica dell'applicazione architettura.

Un'architettura di comunicazione client-a-microservizio diretta potrebbe essere sufficiente una piccola applicazione basata su microservizio, soprattutto se l'applicazione client è un'applicazione web sul lato server come un'applicazione MVC ASP.NET. Tuttavia, quando si compilano grandi e complesse applicazioni basate su microservizio (ad esempio, durante la gestione di decine di tipi microservizio) e in particolare quando le applicazioni client sono remota App per dispositivi mobili o le applicazioni web SPA, tale approccio deve affrontare alcuni problemi.

Quando si sviluppa un'applicazione di grandi dimensioni in base a microservizi, considerare le domande seguenti:

-   *Come possono ridurre al minimo il numero di richieste per il back-end e ridurre le comunicazioni "frammentate" per microservizi più applicazioni client?*

L'interazione con più microservizi per compilare una singola schermata dell'interfaccia utente aumenta il numero di round trip in Internet. In questo modo si aumenta la latenza e la complessità sul lato dell'interfaccia utente. In teoria, le risposte devono essere aggregate in modo efficiente sul lato server, ciò riduce la latenza, poiché più blocchi di dati in parallelo per poi un'interfaccia utente consente di visualizzare dati non appena è pronto.

-   *Per gestire la possibilità a montaggio incrociato problemi, ad esempio l'autorizzazione, le trasformazioni dei dati e dell'invio della richiesta dinamico?*

Implementazione di problemi di sicurezza e a montaggio incrociato ad esempio sicurezza e l'autorizzazione ogni microservizio possono richiedere notevole impegno di sviluppo. Un possibile approccio è che i servizi all'interno dell'host Docker o interne al cluster, allo scopo di limitare l'accesso diretto dall'esterno e implementare tali problemi di montaggio incrociato in una posizione centralizzata, ad esempio un API Gateway.

-   *Modo le applicazioni client possono comunicare con i servizi che utilizzano i protocolli di facile integrazione Internet?*

In genere i protocolli utilizzati sul lato server (ad esempio AMQP o i protocolli binari) non sono supportati nelle App client. Pertanto, le richieste devono essere eseguite tramite protocolli quali HTTP/HTTPS e convertite in un secondo momento gli altri protocolli. Oggetto *man-in-the-middle* approccio è utile per questa situazione.

-   *Come è possibile modellare un aspetto particolarmente apportato App per dispositivi mobili?*

L'API di microservizi più potrebbe non essere progettata anche per le esigenze di diverse applicazioni client. Le esigenze di un'app per dispositivi mobili, ad esempio, potrebbero essere diverse rispetto alle esigenze di un'app web. App per dispositivi mobili, potrebbe essere necessario ottimizzare ulteriormente in modo che le risposte di dati possono essere più efficiente. È possibile farlo l'aggregazione dei dati da più microservizi e restituzione di un singolo set di dati e talvolta eliminando tutti i dati nella risposta non è necessario per l'app per dispositivi mobili. E, naturalmente, si potrebbero comprimere i dati. Nuovamente, un'API tra le app per dispositivi mobili e di microservizi facciata può risultare utile per questo scenario.

## <a name="using-an-api-gateway"></a>Utilizzo di un Gateway API

Quando si progettano e creare app di grandi dimensioni o complesse microservizio applicazioni con più client, può essere un buon approccio per prendere in considerazione un [API Gateway](http://microservices.io/patterns/apigateway.html). Si tratta di un servizio che fornisce un singolo punto di ingresso per alcuni gruppi di microservizi. È simile al [modello facciata](https://en.wikipedia.org/wiki/Facade_pattern) dalla progettazione object‑oriented, ma in questo caso, fa parte di un sistema distribuito. Il modello API Gateway è noto anche come "back-end per i server front-end" [(BFF)](http://samnewman.io/patterns/architectural/bff/) perché compili durante considerare le esigenze dell'applicazione client.

Figura 4-13 viene illustrato come un Gateway di API personalizzata è possibile inserire in un'architettura basata su microservizio.
È importante che evidenziare nel diagramma, si utilizzassero un singolo servizio Gateway di API personalizzato rivolta a più e le applicazioni client diversi. Di fatto può essere un rischio significativo perché il servizio API Gateway verrà aumento delle dimensioni e in continua evoluzione dipende dalle esigenze diverse dalle App client. Infine, sarà troppo grandi a causa di tali requisiti diversi e in modo efficace potrebbe essere abbastanza simile a qualsiasi applicazione o un servizio monolitico. Che è molto è consigliabile suddividere il API Gateway in più servizi o più gateway API più piccoli, uno per ogni tipo di fattore di forma, ad esempio.

![](./media/image13.png)

**Figura 4-13**. Utilizzando un API Gateway implementato come un servizio Web API personalizzato

In questo esempio, il API Gateway potrebbe essere implementato come un servizio Web API personalizzato in esecuzione come un contenitore.

Come accennato, è necessario implementare diverse API gateway in modo che è possibile avere un aspetto diverso per le esigenze di ciascuna applicazione client. Ogni API Gateway può fornire un diverso API personalizzate per ogni app client, eventualmente anche in base al fattore di forma client mediante l'implementazione di codice specifico adapter quali sotto chiama più microservizi interno.

Poiché un Gateway di API personalizzata è in genere un aggregatore di dati, è necessario prestare attenzione con esso. In genere non è consigliabile disporre di un singolo API Gateway l'aggregazione di tutte le microservizi interne dell'applicazione. In caso affermativo, funge da aggregator monolitico o orchestrator e viola l'autonomia microservizio accoppiando tutti di microservizi. Di conseguenza, i gateway API devono essere separati in base ai limiti di business e di non agire come un aggregatore per l'intera applicazione.

Talvolta un Gateway di API granulare possono anche essere un microservizio autonomamente e dispone inoltre di un dominio o nome dell'azienda e i dati correlati. Con i limiti del API Gateway stabiliti dall'azienda o dominio consentirà di ottenere una progettazione migliore.

Granularità nel livello API Gateway può essere particolarmente utile per applicazioni composite più avanzate dell'interfaccia utente in base a microservizi, poiché il concetto di un API Gateway con granularità fine è simile a un servizio di composizione dell'interfaccia utente. Viene illustrato questo più avanti nel [creazione composito dell'interfaccia utente basata su microservizi](#creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices).

Pertanto, per molte applicazioni di medie e grandi dimensioni, dimensioni, tramite un Gateway di API personalizzata è in genere un buon approccio, ma non come un singolo aggregator monolitico o univoco Gateway centrale API personalizzata.

Un altro approccio consiste nell'utilizzare un prodotto come [gestione API di Azure](https://azure.microsoft.com/services/api-management/) come illustrato nella figura 4-14. Questo approccio non solo le proprie esigenze API Gateway è stato risolto, ma fornisce funzionalità come la raccolta di informazioni dalle API. Se si utilizza una soluzione di gestione API, un API Gateway è solo un componente all'interno di tale completa soluzione di gestione API.

![](./media/image14.png)

**Figura 4-14**. Tramite Gestione API di Azure per il Gateway API

In questo caso, quando si utilizza un prodotto come gestione API di Azure, il fatto che potrebbe essere un singolo API Gateway non è così rischiosa perché questi tipi di gateway API sono "sottili", vale a dire non implementare c# codice personalizzato che può evolversi verso un monolitico componente. 

Questo tipo di prodotto è più un proxy inverso per le comunicazioni in ingresso, in cui è possibile anche filtrare le API da di microservizi interno nonché applicare l'autorizzazione per le API pubblicate di questo singolo livello.

Le informazioni disponibili da una Guida di sistema di gestione API comprendere come vengono utilizzate le API e come sono in esecuzione. Tale scopo, consentendo di visualizzare quasi in tempo reale analitica report e identificare le tendenze che potrebbero avere un impatto aziendale. Inoltre, è possibile avere log sull'attività di richiesta e risposta per un'ulteriore analisi offline e online.

Con gestione API di Azure, è possibile proteggere le API mediante una chiave, un token e il filtro IP. Queste funzionalità consentono di applicare quote flessibili e con granularità fine e limiti di velocità, modificare la forma e il comportamento delle API usando i criteri e migliorare le prestazioni con la memorizzazione nella cache di risposta.

In questa Guida e l'applicazione di esempio di riferimento (eShopOnContainers), ci stiamo limitando l'architettura a un'architettura più semplice e personalizzata nei contenitori per concentrarsi sui contenitori normali senza l'utilizzo di prodotti PaaS come gestione API di Azure. Ma microservizio basato su applicazioni di grandi dimensioni che vengono distribuiti in Microsoft Azure, si consiglia di esaminare e adottare gestione API di Azure come base per il gateway API.

## <a name="drawbacks-of-the-api-gateway-pattern"></a>Svantaggi della serie API Gateway

-   Lo svantaggio più importante è che quando si implementa un API Gateway, si è accoppiamento tale livello con il microservizi interno. Accoppiamento questo potrebbe comportare gravi difficoltà per l'applicazione. Vaster Clemens architect team di Azure Service Bus, fa riferimento a questa difficoltà potenziali come "nuovo ESB" nel suo "[messaggistica e Microservizi](https://www.youtube.com/watch?v=rXi5CLjIQ9k)" sessione GOTO 2016.

-   Usando un API Gateway microservizi crea un aggiuntivo possibile singolo punto di errore.

-   Un API Gateway può introdurre il tempo di risposta maggiore a causa della chiamata di rete aggiuntiva. Tuttavia, questa chiamata aggiuntiva presenta in genere un impatto minore rispetto a quelle con un client di interfaccia che troppo "frammentate" chiamare direttamente il microservizi interno.

-   Se non scalabilità correttamente, il API Gateway può diventare un collo di bottiglia.

-   Un API Gateway richiede il costo di sviluppo aggiuntive e manutenzione future se include la logica personalizzata e aggregazione dei dati. Gli sviluppatori devono aggiornare il Gateway di API per esporre gli endpoint di ogni del microservizio. Inoltre, le modifiche implementazione di microservizi interno potrebbero provocare modifiche al codice a livello di API Gateway. Tuttavia, se il API Gateway semplicemente l'applicazione di sicurezza, la registrazione e controllo delle versioni (come avviene quando si utilizza Gestione API di Azure), il costo di sviluppo aggiuntive potrebbe non essere applicabili.

-   Se il API Gateway sviluppato da un singolo gruppo, è possibile che un collo di bottiglia di sviluppo. Si tratta di un altro motivo un approccio migliore per diversi specifico API gateway che rispondono alle esigenze del client diversi. È anche possibile isolare internamente il API Gateway in più aree o i livelli di proprietà di diversi team lavorando di microservizi interno.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Charles Richardson. Modello: API Gateway / back-end per front-end**
    [*http://microservices.io/patterns/apigateway.html*](http://microservices.io/patterns/apigateway.html)

-   **Gestione API di Azure**
    [*https://azure.microsoft.com/services/api-management/*](https://azure.microsoft.com/services/api-management/)

-   **udi Dahan. Composizione orientato ai servizi**\
    [*http://UdiDahan.com/2014/07/30/Service-Oriented-Composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)

-   **Clemens Vasters. Messaggistica e Microservizi a GOTO 2016** (video) [ *https://www.youtube.com/watch?v=rXi5CLjIQ9k*](https://www.youtube.com/watch?v=rXi5CLjIQ9k)


>[!div class="step-by-step"]
[Precedente] (identificare-microservizio-dominio-modello-boundaries.md) [Avanti] (comunicazione-in-microservizio-architecture.md)
