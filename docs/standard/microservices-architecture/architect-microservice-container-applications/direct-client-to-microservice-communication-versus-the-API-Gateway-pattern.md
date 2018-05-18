---
title: Confronto tra comunicazione da client a microservizio diretta e schema API Gateway
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Confronto tra comunicazione da client a microservizio diretta e schema API Gateway
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 40accd8e881c9667f69a61c98da1d013d28e7da6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="direct-client-to-microservice-communication-versus-the-api-gateway-pattern"></a>Confronto tra comunicazione da client a microservizio diretta e schema API Gateway

In un'architettura di microservizi, ogni microservizio espone un set di endpoint (generalmente) specifici. Ciò può influire sulla comunicazione da client a microservizio, come spiegato in questa sezione.

## <a name="direct-client-to-microservice-communication"></a>Comunicazione da client a microservizio diretta

Un possibile approccio prevede l'uso di un'architettura di comunicazione da client a microservizio diretta. In questo caso, un'app client può effettuare richieste direttamente ad alcuni microservizi, come illustrato nella figura 4-12.

![](./media/image12.png)

**Figura 4-12**. Uso di un'architettura di comunicazione da client a microservizio diretta

In questo approccio ogni microservizio include un endpoint pubblico, talvolta con una porta TCP diversa per ogni microservizio. Un esempio di URL per un determinato servizio potrebbe essere l'URL seguente in Azure:

<http://eshoponcontainers.westus.cloudapp.azure.com:88/>

In un ambiente di produzione basato su un cluster, questo URL esegue il mapping al servizio di bilanciamento del carico usato nel cluster, che a sua volta distribuisce le richieste nei vari microservizi. Negli ambienti di produzione, tra i microservizi e Internet potrebbe esserci un controller per la distribuzione delle applicazioni (ADC, Application Delivery Controller), ad esempio il [gateway applicazione di Azure](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction). Questo controller funge da livello trasparente ed esegue non solo il bilanciamento del carico, ma anche la terminazione SSL per proteggere i servizi. In questo modo, migliora il carico degli host eliminando le operazioni di terminazione SSL che richiedono un utilizzo intensivo della CPU e altre attività di routing al gateway applicazione di Azure. In ogni caso, dal punto di vista dell'architettura dell'applicazione logica, un servizio di bilanciamento del carico e un controller per la distribuzione delle applicazioni sono trasparenti.

Un'architettura di comunicazione da client a microservizio diretta potrebbe essere sufficiente per un'applicazione basata su microservizi di piccole dimensioni, soprattutto se l'app client è un'applicazione Web sul lato server, ad esempio un'applicazione MVC ASP.NET. Questo approccio, tuttavia, presenta dei problemi quando si compilano applicazioni grandi e complesse basate su microservizi, ad esempio quando si gestiscono decine di tipi di microservizi, e sopratutto quando le app client sono app per dispositivi mobili remote o applicazioni Web SPA.

Quando si sviluppa un'applicazione di grandi dimensioni basata su microservizi, porsi le domande seguenti:

-   *Come si può ridurre al minimo il numero di richieste per il back-end e le comunicazioni "frammentate" con più microservizi nelle app client?*

L'interazione con più microservizi per compilare una singola schermata dell'interfaccia utente aumenta il numero di round trip in Internet. In questo modo si aumenta la latenza e la complessità sul lato dell'interfaccia utente. In teoria, le risposte dovrebbero essere aggregate in modo efficiente sul lato server: ciò consente di ridurre la latenza, perché vengono restituiti più blocchi di dati in parallelo e alcune interfacce utente possono visualizzare i dati appena vengono resi disponibili.

-   *Come si gestiscono i problemi di montaggio incrociato, ad esempio le autorizzazioni, le trasformazioni dei dati e l'invio di richieste dinamiche?*

L'implementazione di soluzioni per la sicurezza e il montaggio incrociato, ad esempio la sicurezza e le autorizzazioni in ogni microservizio, possono richiedere un notevole impegno in termini di sviluppo. Un possibile approccio prevede di inserire questi servizi all'interno dell'host Docker o di un cluster interno, allo scopo di limitare l'accesso diretto dall'esterno, e di implementare queste soluzioni di montaggio incrociato in una posizione centralizzata, ad esempio un gateway API.

-   *In che modo le app client possono comunicare con i servizi che usano protocolli non adatti a Internet?*

In genere i protocolli usati sul lato server, ad esempio AMQP o i protocolli binari, non sono supportati nelle app client. Quindi, le richieste devono essere eseguite con protocolli come HTTP/HTTPS e trasferite in un secondo momento in altri protocolli. Un approccio *man-in-the-middle* può risultare utile per questa situazione.

-   *Come si può modellare una facciata progettata specificamente per le app per dispositivi mobili?*

L'API di più microservizi potrebbe non essere progettata adeguatamente per le esigenze delle diverse applicazioni client. Ad esempio, le esigenze di un'app per dispositivi mobili potrebbero essere diverse rispetto a quelle di un'app Web. Per le app per dispositivi mobili potrebbe essere necessario un livello ancora maggiore di ottimizzazione per rendere più efficienti le risposte dei dati. Per farlo, è possibile aggregare i dati di più microservizi e restituire un singolo set di dati, eliminando talvolta tutti i dati nella risposta non necessari per l'app per dispositivi mobili. E, naturalmente, si possono comprimere i dati. Anche in questo scenario può risultare utile inserire una facciata o un'API tra le app per dispositivi mobili e i microservizi.

## <a name="using-an-api-gateway"></a>Utilizzo di un gateway API

Quando si progettano e si compilano applicazioni grandi e complesse basate su microservizi con più app client, si può prendere in considerazione l'uso di un [gateway API](https://microservices.io/patterns/apigateway.html). Si tratta di un servizio che fornisce un singolo punto di ingresso per alcuni gruppi di microservizi. È simile allo [schema Facade](https://en.wikipedia.org/wiki/Facade_pattern) della progettazione orientata a oggetti, ma, in questo caso, fa parte di un sistema distribuito. Lo schema API Gateway è noto anche come "backend for frontend" [(BFF)](https://samnewman.io/patterns/architectural/bff/) perché viene compilato pensando alle esigenze dell'app client.

La figura 4-13 mostra in che modo un gateway API personalizzato può essere inserito in un'architettura basata su microservizi.
È importante evidenziare che nel diagramma viene usato un solo servizio di gateway API personalizzato per numerose app client di diverso tipo. Ciò può presentare dei rischi significativi perché il servizio API Gateway verrà ampliato e sviluppato in base alle diverse esigenze delle app client. Alla fine, per soddisfare tutte le esigenze, il servizio potrebbe diventare talmente esteso da sembrare un'unica applicazione o servizio monolitico. Ecco perché si consiglia vivamente di suddividere il gateway API in più servizi o in gateway API più piccoli, uno per ogni tipo di fattore di forma, ad esempio.

![](./media/image13.png)

**Figura 4-13**. Utilizzo di un gateway API implementato come servizio Web API personalizzato

In questo esempio, il gateway API viene implementato sotto forma di servizio Web API personalizzato eseguito come contenitore.

Come accennato, è necessario implementare diversi gateway API per avere più facciate distinte dedicate alle esigenze di ciascuna app client. Ogni gateway API può fornire un'API specifica per ogni app client, eventualmente anche basata sul fattore di forma del client, mediante l'implementazione di un codice dell'adattatore specifico che chiama più microservizi interni.

Un gateway API personalizzato in genere è un aggregatore di dati, quindi è necessario procedere con cautela. Di solito non è consigliabile lasciare che un singolo gateway API aggreghi tutti i microservizi interni dell'applicazione. Se accade, funge da aggregatore monolitico o da agente di orchestrazione e viola l'autonomia del microservizio accoppiando tutti i microservizi. Di conseguenza, i gateway API devono essere separati in base ai limiti aziendali e non fungere da aggregatori per l'intera applicazione.

Talvolta, un gateway API granulare può essere un microservizio e può anche avere un nome di dominio o aziendale, oltre a tutti i dati correlati. Se per il gateway API si usano limiti stabiliti dall'azienda o dal dominio, si avrà una progettazione migliore.

La granularità nel livello del gateway API può essere particolarmente utile per le applicazioni dell'interfaccia utente composita più avanzate basate su microservizi, perché il concetto di gateway API specifici è analogo a quello del servizio di composizione dell'interfaccia utente. Questo argomento viene illustrato più avanti in [Creazione dell'interfaccia utente composita basata su microservizi](#creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices).

Per molte applicazioni di medie e grandi dimensioni, quindi, l'uso di un gateway API personalizzato rappresenta in genere una buona soluzione, tranne quando viene usato come unico aggregatore monolitico o come gateway API personalizzato univoco centrale.

Un altro approccio consiste nell'usare un prodotto come [Gestione API di Azure](https://azure.microsoft.com/services/api-management/) come illustrato nella figura 4-14. Questo approccio non solo risolvere le esigenze del gateway API, ma fornisce anche funzionalità come la raccolta di informazioni dalle API. Se si usa una soluzione per la gestione delle API, un gateway API è semplicemente un componente all'interno della soluzione completa.

![](./media/image14.png)

**Figura 4-14**. Utilizzo di Gestione API di Azure per il gateway API

In questo caso, quando si usa un prodotto come Gestione API di Azure, la presenza di un solo gateway API non è così rischiosa perché questi tipi di gateway API sono più "sottili", in altre parole non comportano l'implementazione di codice C# personalizzato che potrebbe diventare un componente monolitico. 

Questo tipo di prodotto funge più da proxy inverso per le comunicazioni in ingresso, in cui è possibile anche filtrare le API dai microservizi interni e applicare l'autorizzazione alle API pubblicate in questo singolo livello.

Le informazioni disponibili nel sistema di gestione API aiutano a capire le modalità di utilizzo e le prestazioni delle API. Questi dati vengono visualizzati in report di analisi quasi in tempo reale e codificati grazie all'identificazione di tendenze che potrebbero avere un impatto aziendale. Inoltre, possono essere forniti log sulle attività di richiesta e risposta che permettono ulteriori analisi online e offline.

Con Gestione API di Azure è possibile proteggere le API usando una chiave, un token e il filtro IP. Queste funzionalità consentono di applicare limiti di velocità e quote flessibili e specifiche, modificare la forma e il comportamento delle API usando i criteri e migliorare le prestazioni con la memorizzazione nella cache delle risposte.

In questa guida e nell'applicazione di esempio di riferimento (eShopOnContainers), l'architettura è una semplice architettura in contenitori personalizzata che consente di concentrarsi sui contenitori normali senza usare prodotti PaaS come Gestione API di Azure. Per le applicazioni di grandi dimensioni basate su microservizi distribuite in Microsoft Azure, invece, si consiglia di esaminare e adottare Gestione API di Azure come base per i gateway API.

## <a name="drawbacks-of-the-api-gateway-pattern"></a>Svantaggi dello schema API Gateway

-   Lo svantaggio più importante consiste nel fatto che, quando si implementa un gateway API, tale livello viene accoppiato con i microservizi interni. Un accoppiamento di questo tipo potrebbe causare gravi difficoltà per l'applicazione. Clemens Vaster, architetto del team del bus di servizio di Azure, chiama questa difficoltà potenziale "il nuovo ESB" nella sua sessione sulla [messaggistica e i microservizi](https://www.youtube.com/watch?v=rXi5CLjIQ9k) di GOTO 2016.

-   Usando un gateway API per i microservizi, si crea un altro possibile singolo punto di guasto.

-   Un gateway API può aumentare il tempo di risposta a causa della chiamata di rete aggiuntiva. Tuttavia, il ritardo dovuto a questa chiamata di solito è minore del tempo perso in comunicazioni frammentate da un'interfaccia client che chiama direttamente i microservizi interni.

-   Se la scalabilità orizzontale non viene eseguita correttamente, il gateway API può diventare un collo di bottiglia.

-   Un gateway API richiede un costo di sviluppo aggiuntivo e ulteriori operazioni di manutenzione future se include la logica personalizzata e l'aggregazione dei dati. Gli sviluppatori devono aggiornare il gateway API per esporre gli endpoint di ogni microservizio. Inoltre, le modifiche di implementazione nei microservizi interni potrebbero causare modifiche al codice al livello del gateway API. Tuttavia, se il gateway API viene usato semplicemente per le attività di sicurezza, registrazione e controllo delle versioni, come avviene con Gestione API di Azure, il costo di sviluppo aggiuntivo potrebbe non essere applicato.

-   Se il gateway API viene sviluppato da un singolo team, potrebbe verificarsi un collo di bottiglia nello sviluppo. Ecco un altro motivo per cui è preferibile avere più gateway API specifici che rispondono alle diverse esigenze dei client. È anche possibile suddividere internamente il gateway API in più aree o livelli di proprietà dei diversi team che lavorano sui microservizi interni.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Charles Richardson. Pattern: API Gateway / Backend for Front-End**
    [*https://microservices.io/patterns/apigateway.html*](https://microservices.io/patterns/apigateway.html) (Modello: Gateway API/Back.end per front-end)

-   **Gestione API di Azure**
    [*https://azure.microsoft.com/services/api-management/*](https://azure.microsoft.com/services/api-management/)

-   **Udi Dahan. Service Oriented Composition (Composizione orientata ai servizi)**\
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)

-   **Clemens Vasters. Messaging and Microservices at GOTO 2016 (Messaggistica e microservizi a GOTO 2016)**  (video) [*https://www.youtube.com/watch?v=rXi5CLjIQ9k*](https://www.youtube.com/watch?v=rXi5CLjIQ9k)


>[!div class="step-by-step"]
[Indietro] (identify-microservice-domain-model-boundaries.md) [Avanti] (communication-in-microservice-architecture.md)
