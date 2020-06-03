---
title: Confronto tra schema API Gateway e comunicazione diretta da client a microservizio
description: Informazioni sulle differenze e sugli usi dello schema API Gateway e della comunicazione diretta da client a microservizio.
ms.date: 01/07/2019
ms.openlocfilehash: 089b6302132437e4bb733653b3edb401ff81a164
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306955"
---
# <a name="the-api-gateway-pattern-versus-the-direct-client-to-microservice-communication"></a>Confronto tra schema API Gateway e comunicazione diretta da client a microservizio

In un'architettura di microservizi, ogni microservizio espone in genere un set di endpoint specifici. Questo può influire sulla comunicazione da client a microservizio, come spiegato in questa sezione.

## <a name="direct-client-to-microservice-communication"></a>Comunicazione da client a microservizio diretta

Un possibile approccio prevede l'uso di un'architettura di comunicazione da client a microservizio diretta. In questo caso, un'app client può effettuare richieste direttamente ad alcuni microservizi, come illustrato nella figura 4-12.

![Diagramma che illustra l'architettura di comunicazione da client a microservizio.](./media/direct-client-to-microservice-communication.png)

**Figura 4-12**. Uso di un'architettura di comunicazione da client a microservizio diretta

In questo approccio ogni microservizio include un endpoint pubblico, talvolta con una porta TCP diversa per ogni microservizio. Un esempio di URL per un determinato servizio potrebbe essere l'URL seguente in Azure:

`http://eshoponcontainers.westus.cloudapp.azure.com:88/`

In un ambiente di produzione basato su un cluster, questo URL esegue il mapping al servizio di bilanciamento del carico usato nel cluster, che a sua volta distribuisce le richieste nei vari microservizi. Negli ambienti di produzione, tra i microservizi e Internet potrebbe esserci un controller per la distribuzione delle applicazioni (ADC, Application Delivery Controller), ad esempio il [gateway applicazione di Azure](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction). Questo controller funge da livello trasparente ed esegue non solo il bilanciamento del carico, ma anche la terminazione SSL per proteggere i servizi. In questo modo, migliora il carico degli host eliminando le operazioni di terminazione SSL che richiedono un utilizzo intensivo della CPU e altre attività di routing al gateway applicazione di Azure. In ogni caso, dal punto di vista dell'architettura dell'applicazione logica, un servizio di bilanciamento del carico e un controller per la distribuzione delle applicazioni sono trasparenti.

Un'architettura di comunicazione da client a microservizio diretta potrebbe essere sufficiente per un'applicazione basata su microservizi di piccole dimensioni, soprattutto se l'app client è un'applicazione Web sul lato server, ad esempio un'applicazione MVC ASP.NET. Questo approccio, tuttavia, presenta dei problemi quando si compilano applicazioni grandi e complesse basate su microservizi, ad esempio quando si gestiscono decine di tipi di microservizi, e sopratutto quando le app client sono app per dispositivi mobili remote o applicazioni Web SPA.

Quando si sviluppa un'applicazione di grandi dimensioni basata su microservizi, porsi le domande seguenti:

- *Come ridurre al minimo il numero di richieste per il back-end e le comunicazioni "frammentate" con più microservizi nelle app client?*

L'interazione con più microservizi per compilare una singola schermata dell'interfaccia utente aumenta il numero di round trip in Internet. In questo modo si aumenta la latenza e la complessità sul lato dell'interfaccia utente. In teoria, le risposte dovrebbero essere aggregate in modo efficiente sul lato server. Ciò consente di ridurre la latenza, perché vengono restituiti più blocchi di dati in parallelo e alcune interfacce utente possono visualizzare i dati non appena vengono resi disponibili.

- *Come si gestiscono i problemi trasversali, ad esempio le autorizzazioni, le trasformazioni dei dati e l'invio di richieste dinamiche?*

L'implementazione di soluzioni per la sicurezza e il montaggio incrociato, ad esempio la sicurezza e le autorizzazioni in ogni microservizio, possono richiedere un notevole impegno in termini di sviluppo. Un possibile approccio prevede di inserire questi servizi all'interno dell'host Docker o di un cluster interno, in modo da limitare l'accesso diretto dall'esterno e di implementare queste soluzioni di montaggio incrociato in una posizione centralizzata, ad esempio un gateway API.

- *In che modo le app client possono comunicare con i servizi che usano protocolli non adatti a Internet?*

In genere i protocolli usati sul lato server, ad esempio AMQP o i protocolli binari, non sono supportati nelle app client. Quindi, le richieste devono essere eseguite con protocolli come HTTP/HTTPS e trasferite in un secondo momento in altri protocolli. Un approccio *man-in-the-middle* può risultare utile per questa situazione.

- *Come modellare una facciata progettata specificamente per le app per dispositivi mobili?*

L'API di più microservizi potrebbe non essere progettata adeguatamente per le esigenze delle diverse applicazioni client. Ad esempio, le esigenze di un'app per dispositivi mobili potrebbero essere diverse rispetto a quelle di un'app Web. Per le app per dispositivi mobili potrebbe essere necessario un livello ancora maggiore di ottimizzazione per rendere più efficienti le risposte dei dati. Per farlo è possibile aggregare i dati di più microservizi e restituire un singolo set di dati, talvolta eliminando tutti i dati nella risposta non necessari per l'app per dispositivi mobili. E, naturalmente, si possono comprimere i dati. Anche in questo scenario può risultare utile inserire una facciata o un'API tra l'app per dispositivi mobili e i microservizi.

## <a name="why-consider-api-gateways-instead-of-direct-client-to-microservice-communication"></a>Perché prendere in considerazione i gateway API invece della comunicazione da client a microservizio diretta

In un'architettura di microservizi le app client necessitano in genere di utilizzare le funzionalità di più microservizi. Se questo utilizzo viene eseguito direttamente, il client deve gestire più chiamate agli endpoint dei microservizi. Cosa accade quando l'applicazione si evolve e vengono introdotti nuovi microservizi oppure quelli esistenti vengono aggiornati? Se l'applicazione ha molti microservizi, la gestione di un numero elevato di endpoint dalle app client può essere molto difficoltosa. Dal momento che l'app client viene associata a questi endpoint interni, l'evoluzione dei microservizi in futuro potrebbe comportare un impatto elevato per le app client.

Pertanto, può essere molto comodo per le applicazioni basate su microservizi disporre di un livello intermedio di riferimento indiretto (gateway). Se non si dispone di gateway API, le app client devono inviare le richieste direttamente ai microservizi e ciò può creare problemi, ad esempio:

- **Accoppiamento**: senza lo schema API Gateway, le app client sono associate ai microservizi interni. Le app client devono sapere in che modo le diverse aree dell'applicazione vengono scomposte in microservizi. Quando si evolvono e si effettua il refactoring dei microservizi interni, tali azioni incidono sulla manutenzione perché causano modifiche di rilievo alle app client a causa del riferimento diretto ai microservizi interni dalle app client. Le app client devono essere aggiornate frequentemente, rendendo più difficile sviluppare la soluzione.

- **Troppi round trip**: una singola pagina/schermata nell'app client potrebbe richiedere diverse chiamate a più servizi. Questo può determinare più round trip in rete tra il client e il server e causare così una latenza significativa. Con l'aggregazione gestita in un livello intermedio è stato possibile migliorare le prestazioni e l'esperienza utente per l'app client.

- **Problemi di sicurezza**: senza un gateway, tutti i microservizi devono essere esposti all'esterno, rendendo più ampia la superficie di attacco rispetto a quando si nascondono i microservizi interni non usati direttamente dalle app client. Minore è la superficie di attacco, maggiore è la sicurezza dell'applicazione.

- **Problematiche trasversali**: ogni microservizio pubblicato pubblicamente deve gestire problemi quali l'autorizzazione e SSL. In molti casi questi problemi possono essere gestiti in un livello singolo così che i microservizi interni risultino semplificati.

## <a name="what-is-the-api-gateway-pattern"></a>Definizione dello schema API Gateway

Quando si progettano e si compilano applicazioni grandi e complesse basate su microservizi con più app client, si può prendere in considerazione l'uso di un [gateway API](https://microservices.io/patterns/apigateway.html). Si tratta di un servizio che fornisce un singolo punto di ingresso per alcuni gruppi di microservizi. È simile allo [schema Facade](https://en.wikipedia.org/wiki/Facade_pattern) della progettazione orientata a oggetti, ma in questo caso fa parte di un sistema distribuito. Il modello di gateway API è anche noto come "backend per front-end" ([BFF](https://samnewman.io/patterns/architectural/bff/)), perché viene compilato pensando alle esigenze dell'app client.

Pertanto, il gateway API si trova tra le app client e i microservizi. e funge da proxy inverso, indirizzando le richieste dai client ai servizi. Può inoltre fornire altre funzionalità a montaggio incrociato, come autenticazione, terminazione SSL e cache.

La figura 4-13 mostra in che modo un gateway API personalizzato può essere inserito in un'architettura basata su microservizi semplificata, con pochi microservizi.

![Diagramma che mostra un gateway API implementato come servizio personalizzato.](./media/direct-client-to-microservice-communication-versus-the-API-Gateway-pattern/custom-service-api-gateway.png)

**Figura 4-13**. Uso di un gateway API implementato come servizio personalizzato

Le app si connettono a un singolo endpoint, il gateway API, configurato per l'invio di richieste a singoli microservizi. In questo esempio il gateway API viene implementato sotto forma di servizio WebHost ASP.NET Core personalizzato eseguito come contenitore.

È importante evidenziare che nel diagramma viene usato un solo servizio gateway API personalizzato per numerose app client di diverso tipo. Ciò può presentare dei rischi significativi perché il servizio API Gateway verrà ampliato e sviluppato in base alle diverse esigenze delle app client. Alla fine, il problema si verificherà a causa di queste diverse esigenze e in effetti potrebbe essere simile a un'applicazione monolitica o a un servizio monolitico. Ecco perché si consiglia vivamente di suddividere il gateway API in più servizi o in gateway API più piccoli, ad esempio uno per ogni tipo fattore di forma di app client.

È necessario prestare attenzione quando si implementa lo schema API Gateway. Di solito non è consigliabile lasciare che un singolo gateway API aggreghi tutti i microservizi interni dell'applicazione. Se accade, funge da aggregatore monolitico o da agente di orchestrazione e viola l'autonomia del microservizio accoppiando tutti i microservizi.

Di conseguenza, i gateway API devono essere separati in base ai limiti aziendali e alle app client e non fungere da aggregatore singolo per tutti i microservizi interni.

Quando si divide il livello API Gateway in più gateway API, se l'applicazione ha più app client può costituire un elemento pivot primario per l'identificazione dei diversi tipi di gateway API, in modo da avere una facciata differente per le esigenze di ciascuna app client. Questo caso è uno schema denominato "Backend for Frontend" ([BFF](https://samnewman.io/patterns/architectural/bff/)), in cui ogni gateway API può fornire un'API specifica per ogni tipo di app client, eventualmente anche in base al fattore di forma del client, implementando un codice dell'adattatore specifico che chiama più microservizi interni, come illustrato nell'immagine seguente:

![Diagramma che Mostra più gateway API personalizzati.](./media/direct-client-to-microservice-communication-versus-the-API-Gateway-pattern/multiple-custom-api-gateways.png)

**Figura 4-13.1**. Uso di più gateway API personalizzati

Figura 4-13.1 Mostra i gateway API che sono separati dal tipo di client; uno per i client per dispositivi mobili e uno per i client Web. Un'app Web tradizionale si connette a un microservizio MVC che usa gateway API Web. Nell'esempio viene illustrata un'architettura semplificata con più gateway API con granularità fine. In questo caso i limiti identificati per ogni gateway API si basano esclusivamente sullo schema "Backend for Frontend" ([BFF](https://samnewman.io/patterns/architectural/bff/)), pertanto sono basati solo sull'API necessaria per ciascuna app client. Ma in applicazioni di dimensioni più elevate è anche opportuno andare avanti e creare altri gateway API basati sui limiti aziendali come secondo elemento pivot di progettazione.

## <a name="main-features-in-the-api-gateway-pattern"></a>Funzionalità principali dello schema API Gateway

Lo schema API Gateway può offrire più funzionalità. A seconda del prodotto, le funzionalità possono essere più o meno avanzate, tuttavia quelle più importanti e fondamentali per qualsiasi gateway API sono gli schemi progettuali seguenti:

**Proxy inverso o routing del gateway.** Lo schema API Gateway offre un proxy inverso per reindirizzare o instradare le richieste (routing di livello 7, in genere richieste HTTP) agli endpoint dei microservizi interni. Il gateway fornisce un singolo endpoint o URL per le app client e quindi associa internamente le richieste a un gruppo di microservizi interni. Questa funzionalità di routing consente di separare le app client dai microservizi, ma è anche utile quando si modernizza un'API monolitica posizionando il gateway API tra l'API monolitica e le app client, è possibile aggiungere nuove API come nuovi microservizi continuando comunque a usare l'API monolitica legacy fino a quando non sarà suddiviso in molti microservizi in futuro. A causa del gateway API, le app client non rilevano se le API in uso sono implementate come microservizi interni o come un'API monolitica e, cosa ancora più importante, quando si sviluppa e si effettua il refactoring dell'API monolitica in microservizi, grazie al routing del gateway API le app client non sono interessate da eventuali modifiche a livello di URI.

Per altre informazioni, vedere [Modello di routing gateway](https://docs.microsoft.com/azure/architecture/patterns/gateway-routing).

**Aggregazione di richieste.** Nell'ambito dello schema del gateway è possibile aggregare più richieste client (in genere richieste HTTP) destinate a più microservizi interni in una singola richiesta client. Questo schema è particolarmente utile quando una pagina/schermata del client necessita di informazioni da svariati microservizi. Con questo approccio, l'app client invia una singola richiesta al gateway API che invia diverse richieste ai microservizi interni, per poi aggregare i risultati e inviare nuovamente tutti i dati all'app client. Il principale vantaggio e lo scopo di questo schema progettuale è quello di ridurre i chattiness tra le app client e l'API back-end, che è particolarmente importante per le app Remote fuori dal Data Center in cui si trovano i microservizi, come le app per dispositivi mobili o le richieste provenienti da app SPA che provengono da JavaScript nei browser remoti del client. Per le app Web regolari che eseguono le richieste nell'ambiente server (come un'app Web ASP.NET Core MVC), questo schema non è così importante dal momento che la latenza è molto inferiore rispetto a quella per le app client remote.

A seconda del gateway API in uso, potrebbe essere possibile eseguire questa aggregazione. Tuttavia in molti casi risulta più flessibile creare microservizi di aggregazione nell'ambito del gateway API, definendo l'aggregazione nel codice (vale a dire nel codice C#):

Per altre informazioni, vedere [Modello di aggregazione gateway](https://docs.microsoft.com/azure/architecture/patterns/gateway-aggregation).

**Problemi trasversali o offload del gateway.** A seconda delle funzionalità offerte da ogni gateway API, è possibile eseguire l'offload delle funzionalità dai singoli microservizi al gateway, semplificando l'implementazione di ogni microservizio attraverso il consolidamento dei problemi trasversali in un livello. Ciò è particolarmente utile per le funzionalità specializzate che possono essere complesse da implementare correttamente in ogni microservizio interno, ad esempio le funzionalità seguenti:

- Autenticazione e autorizzazione
- Integrazione dell'individuazione dei servizi
- Memorizzazione nella cache delle risposte
- Criteri per i tentativi, interruttore di circuito e QoS
- Limiti di velocità e limitazione delle richieste
- Bilanciamento del carico
- Registrazione, analisi, correlazione
- Intestazioni, stringhe di query e trasformazione delle attestazioni
- Inserimento nell'elenco di IP consentiti

Per altre informazioni, vedere [Modello di offload gateway](https://docs.microsoft.com/azure/architecture/patterns/gateway-offloading).

## <a name="using-products-with-api-gateway-features"></a>Uso di prodotti con funzionalità di gateway API

Possono esserci molti altri problemi trasversali generati dai gateway API a seconda dell'implementazione. Di seguito verranno esaminati:

- [Gestione API di Azure](https://azure.microsoft.com/services/api-management/)
- [Ocelot](https://github.com/ThreeMammals/Ocelot)

### <a name="azure-api-management"></a>Gestione API di Azure

[Gestione API di Azure](https://azure.microsoft.com/services/api-management/) (come illustrato nella figura 4-14) consente di risolvere le esigenze del gateway API e fornisce anche funzionalità come la raccolta di informazioni dalle API. Se si usa una soluzione per la gestione delle API, un gateway API è solo un componente della soluzione completa.

![Diagramma che illustra come usare gestione API di Azure come gateway API.](./media/direct-client-to-microservice-communication-versus-the-API-Gateway-pattern/api-gateway-azure-api-management.png)

**Figura 4-14**. Utilizzo di Gestione API di Azure per il gateway API

Gestione API di Azure risolve sia il gateway API sia le esigenze di gestione, ad esempio registrazione, sicurezza, misurazione e così via. In questo caso, quando si usa un prodotto come gestione API di Azure, il fatto che si disponga di un singolo gateway API non è così rischioso perché questi tipi di gateway API sono "più sottili", vale a dire che non si implementa codice C# personalizzato che può evolversi verso un componente monolitico.

I gateway API fungono in genere da proxy inverso per le comunicazioni in ingresso, in cui è possibile anche filtrare le API dai microservizi interni e applicare l'autorizzazione alle API pubblicate in questo livello singolo.

Le informazioni disponibili nel sistema di gestione API aiutano a capire le modalità di utilizzo e le prestazioni delle API. Questi dati vengono visualizzati in report di analisi quasi in tempo reale e codificati grazie all'identificazione di tendenze che potrebbero avere un impatto aziendale. Inoltre, possono essere forniti log sulle attività di richiesta e risposta che permettono ulteriori analisi online e offline.

Con Gestione API di Azure è possibile proteggere le API usando una chiave, un token e il filtro IP. Queste funzionalità consentono di applicare limiti di velocità e quote flessibili e specifiche, modificare la forma e il comportamento delle API usando i criteri e migliorare le prestazioni con la memorizzazione nella cache delle risposte.

In questa guida e nell'applicazione di esempio di riferimento (eShopOnContainers), l'architettura è una semplice architettura in contenitori personalizzata che consente di concentrarsi sui contenitori normali senza usare prodotti PaaS come Gestione API di Azure. Per le applicazioni di grandi dimensioni basate su microservizi distribuite in Microsoft Azure, invece, si consiglia di valutare Gestione API di Azure come base per i gateway API in produzione.

### <a name="ocelot"></a>Ocelot

[Ocelot](https://github.com/ThreeMammals/Ocelot) è un gateway API leggero, consigliato per gli approcci più semplici. Ocelot è un gateway API Open source basato su .NET Core, appositamente creato per le architetture di microservizi che necessitano di punti di ingresso unificati nei rispettivi sistemi. Si tratta di un servizio leggero, veloce e scalabile che offre routing e autenticazione tra molte altre funzionalità.

Il motivo principale per cui si sceglie Ocelot per l' [applicazione di riferimento eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) è che Ocelot è un gateway API Lightweight .NET Core che è possibile distribuire nello stesso ambiente di distribuzione dell'applicazione in cui si distribuiscono i microservizi/contenitori, ad esempio un host Docker, Kubernetes e così via. Poiché è basato su .NET Core, è multipiattaforma che ti permette di eseguire la distribuzione in Linux o Windows.

I diagrammi precedenti dei gateway API personalizzati in esecuzione nei contenitori rappresentano esattamente come è possibile eseguire anche Ocelot in un contenitore e in un'applicazione basata su microservizi.

Esistono anche molti altri prodotti sul mercato che offrono funzionalità di gateway API, ad esempio Apigee, Kong, MuleSoft, WSO2, e altri prodotti come Linkerd e Istio per funzionalità di controller in ingresso per il mesh dei servizi.

Dopo le sezioni iniziali di spiegazione degli schemi e dell'architettura, le sezioni successive illustrano come implementare gateway API con [Ocelot](https://github.com/ThreeMammals/Ocelot).

## <a name="drawbacks-of-the-api-gateway-pattern"></a>Svantaggi dello schema API Gateway

- Lo svantaggio più importante consiste nel fatto che, quando si implementa un gateway API, tale livello viene accoppiato con i microservizi interni. Un accoppiamento di questo tipo potrebbe causare gravi difficoltà per l'applicazione. Clemens Vaster, architetto del team del bus di servizio di Azure, chiama questa difficoltà potenziale "il nuovo ESB" nella sessione sulla [messaggistica e i microservizi](https://www.youtube.com/watch?v=rXi5CLjIQ9k) di GOTO 2016.

- Usando un gateway API per i microservizi, si crea un altro possibile singolo punto di guasto.

- Un gateway API può aumentare il tempo di risposta a causa della chiamata di rete aggiuntiva. Tuttavia il ritardo dovuto a questa chiamata è di solito minore del tempo perso in comunicazioni frammentate da un'interfaccia client che chiama direttamente i microservizi interni.

- Se la scalabilità orizzontale non viene eseguita correttamente, il gateway API può diventare un collo di bottiglia.

- Un gateway API richiede un costo di sviluppo aggiuntivo e ulteriori operazioni di manutenzione future se include la logica personalizzata e l'aggregazione dei dati. Gli sviluppatori devono aggiornare il gateway API per esporre gli endpoint di ogni microservizio. Inoltre, le modifiche di implementazione nei microservizi interni potrebbero causare modifiche al codice al livello del gateway API. Tuttavia, se il gateway API viene usato semplicemente per le attività di sicurezza, registrazione e controllo delle versioni, come avviene con Gestione API di Azure, il costo di sviluppo aggiuntivo potrebbe non essere applicato.

- Se il gateway API viene sviluppato da un singolo team, potrebbe verificarsi un collo di bottiglia nello sviluppo. Ecco un altro motivo per cui è preferibile avere più gateway API specifici che rispondono alle diverse esigenze dei client. È anche possibile suddividere internamente il gateway API in più aree o livelli di proprietà dei diversi team che lavorano sui microservizi interni.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Chris Richardson. Modello: gateway API/backend per front-end** \
  <https://microservices.io/patterns/apigateway.html>

- **Modello del gateway API** \
  <https://docs.microsoft.com/azure/architecture/microservices/gateway>

- **Modello di aggregazione e composizione** \
  <https://microservices.io/patterns/data/api-composition.html>

- **Gestione API di Azure** \
  <https://azure.microsoft.com/services/api-management/>

- **UDI. Composizione orientata ai servizi** \
  <https://udidahan.com/2014/07/30/service-oriented-composition-with-video/>

- **Clemens più grande. Messaggistica e microservizi in GOTO 2016 (video)** \
  <https://www.youtube.com/watch?v=rXi5CLjIQ9k>

- **Gateway API in breve** (ASP.NET Core serie di esercitazioni sul gateway API) \
  <https://www.pogsdotnet.com/2018/08/api-gateway-in-nutshell.html>

>[!div class="step-by-step"]
>[Precedente](identify-microservice-domain-model-boundaries.md) 
> [Avanti](communication-in-microservice-architecture.md)
