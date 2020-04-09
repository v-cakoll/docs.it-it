---
title: Comunicazione client front-end
description: Scopri come i client front-end comunicano con i sistemi cloud native
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: af26873381509df7807db6ecb37a7d73669adb37
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989077"
---
# <a name="front-end-client-communication"></a>Comunicazione client front-end

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In un sistema cloud-native, i client front-end (applicazioni per dispositivi mobili, Web e desktop) richiedono un canale di comunicazione per interagire con microservizi back-end indipendenti.  

Quali sono le opzioni?

Per semplificare le cose, un client front-end potrebbe *comunicare direttamente* con i microservizi back-end, illustrato nella Figura 4-2.

![Comunicazione diretta da client a servizio](./media/direct-client-to-service-communication.png)

**Come grafico 4-2.** Comunicazione diretta da client a servizio

Con questo approccio, ogni microservizio dispone di un endpoint pubblico accessibile dai client front-end. In un ambiente di produzione, è necessario inserire un servizio di bilanciamento del carico davanti ai microservizi, instradando il traffico in modo proporzionale.

Sebbene semplice da implementare, la comunicazione diretta del client sarebbe accettabile solo per le semplici applicazioni di microservizio. Questo modello accoppia strettamente i client front-end ai servizi back-end principali, aprendo la porta a una serie di problemi, tra cui:

- Suscettibilità del client al refactoring del servizio back-end.
- Una superficie di attacco più ampia come servizi back-end di base sono direttamente esposti.
- Duplicazione di problemi trasversali in ogni microservizio.
- Codice client eccessivamente complesso: i client devono tenere traccia di più endpoint e gestire gli errori in modo resiliente.

Al contrario, un modello di progettazione cloud ampiamente accettato consiste nell'implementare un [servizio gateway API](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) tra le applicazioni front-end e i servizi back-end. Il modello è illustrato nella Figura 4-3.

![Modello di gateway API](./media/api-gateway-pattern.png)

**Figura 4-3.** Modello di gateway API

Nella figura precedente, notare come il servizio Gateway API astrae i microservizi core back-end. Implementato come un'API web, funge da *proxy inverso,* instradando il traffico in ingresso ai microservizi interni.

Il gateway isola il client dal partizionamento e dal refactoring del servizio interno. Se si modifica un servizio back-end, è necessario per esso nel gateway senza interrompere il client. È anche la prima linea di difesa per i problemi trasversali, ad esempio identità, memorizzazione nella cache, resilienza, misurazione e limitazione delle richieste. Molti di questi problemi trasversali possono essere scaricati dai servizi di base back-end al gateway, semplificando i servizi back-end.

È necessario prestare attenzione per mantenere il gateway API semplice e veloce. In genere, la logica di business viene mantenuta all'esterno del gateway. Un gateway complesso rischia di diventare un collo di bottiglia e alla fine un monolite stesso. I sistemi più grandi spesso espongono più gateway API segmentati per tipo di client (mobile, web, desktop) o funzionalità back-end. Il modello [Backend for Frontends](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) fornisce la direzione per l'implementazione di più gateway. Il modello è illustrato nella Figura 4-4.

![Modello di gateway API](./media/backend-for-frontend-pattern.png)

**Figura 4-4.** Backend per il modello front-end

Nota nella figura precedente come il traffico in ingresso viene inviato a un gateway API specifico, in base al tipo di client: web, mobile o app desktop. Questo approccio ha senso in quanto le funzionalità di ogni dispositivo differiscono in modo significativo tra il fattore di forma, le prestazioni e le limitazioni di visualizzazione. In genere le applicazioni per dispositivi mobili espongono meno funzionalità rispetto a un browser o applicazioni desktop. Ogni gateway può essere ottimizzato in base alle funzionalità e alle funzionalità del dispositivo corrispondente.

Per iniziare, è possibile creare il proprio servizio gateway API. Una rapida ricerca di GitHub fornirà molti esempi. Tuttavia, sono disponibili diversi framework e prodotti gateway commerciali.

## <a name="ocelot-gateway"></a>Ocelot Gateway

Per applicazioni native cloud .NET semplici, è possibile prendere in considerazione il [gateway Ocelot](https://github.com/ThreeMammals/Ocelot). Ocelot è un gateway API Open Source creato per i microservizi .NET che richiedono un punto di ingresso unificato nel proprio sistema. È leggero, veloce, scalabile.

Come qualsiasi gateway API, la sua funzionalità principale consiste nell'inoltrare le richieste HTTP in ingresso ai servizi downstream. Inoltre, supporta un'ampia gamma di funzionalità configurabili in una pipeline middleware di .NET Core. Il set di funzionalità è presentato nella tabella seguente.

|Ocelot Caratteristiche  | |
| :-------- | :-------- |
| Routing. | Authentication |
| Aggregazione delle richieste | Autorizzazione |
| Individuazione dei servizi (con console ed Eureka) | Limitazione |
| Bilanciamento del carico. | Registrazione, Traccia |
| Memorizzazione nella cache | Trasformazione Intestazioni/Stringhe di query |
| Trasmissione di correlazione | Middleware personalizzato |
| QoS (Quality of Service) | Criteri di ripetizione dei tentativiRetry Policies |

Ogni gateway Ocelot specifica gli indirizzi upstream e downstream e le funzionalità configurabili in un file di configurazione JSON. Il client invia una richiesta HTTP al gateway Ocelot. Una volta ricevuto, Ocelot passa l'oggetto HttpRequest attraverso la pipeline manipolandolo nello stato specificato dalla relativa configurazione. Alla fine della pipeline, Ocelot crea un nuovo HTTPResponseObject e lo passa al servizio downstream. Per la risposta, Ocelot inverte la pipeline, inviando la risposta al client.

Ocelot è disponibile come pacchetto NuGet. È destinato al NET Standard 2.0, rendendolo compatibile con entrambi i runtime di .NET Core 2.0 e .NET Framework 4.6.1. Ocelot si integra con tutto ciò che parla HTTP e viene eseguito sulle piattaforme che .NET Core supporta: Linux, macOS e Windows. Ocelot è estensibile e supporta molte piattaforme moderne, tra cui contenitori Docker, servizi di Azure Kubernetes o altri cloud pubblici.  Ocelot si integra con pacchetti open source come [Consul,](https://www.consul.io) [GraphQL](https://graphql.org)e [Eureka](https://github.com/Netflix/eureka)di Netflix.

Considerare Ocelot per le applicazioni semplici native nel cloud che non richiedono il ricco set di funzionalità di un gateway API commerciale.

## <a name="azure-application-gateway"></a>Gateway applicazione di Azure

Per i requisiti di gateway semplici, è possibile prendere in considerazione il gateway applicazione di [Azure.For](https://docs.microsoft.com/azure/application-gateway/overview)simple gateway requirements, you may consider Azure Application Gateway . Disponibile come servizio Di Azure [PaaS,](https://azure.microsoft.com/overview/what-is-paas/)include funzionalità di gateway di base, ad esempio il routing degli URL, la terminazione SSL e un firewall applicazione Web. Il servizio supporta le funzionalità di [bilanciamento del carico layer-7.](https://www.nginx.com/resources/glossary/layer-7-load-balancing/) Con il livello 7, è possibile instradare le richieste in base al contenuto effettivo di un messaggio HTTP, non solo ai pacchetti di rete TCP di basso livello.

In tutto questo libro, evangelizziamo l'hosting di sistemi cloud-nativi in [Kubernetes](https://www.infoworld.com/article/3268073/what-is-kubernetes-your-next-application-platform.html). Un orchestratore contenitore, Kubernetes automatizza i problemi di distribuzione, scalabilità e operativi dei carichi di lavoro containerizzati. Il gateway applicazione di Azure può essere configurato come gateway API per il cluster di servizi [Azure Kubernetes.Azure Application](https://azure.microsoft.com/services/kubernetes-service/) Gateway can be configured as an API gateway for Azure Kubernetes Service cluster.

Il controller di [ingresso del gateway applicazione](https://azure.github.io/application-gateway-kubernetes-ingress/) consente al gateway applicazione di Azure di funzionare direttamente con il servizio Azure [Kubernetes.](https://azure.microsoft.com/services/kubernetes-service/) Figura 4.5 Mostra l'architettura.

![Controller di ingresso del gateway applicazione](./media/application-gateway-ingress-controller.png)

**Figura 4-5.** Controller di ingresso del gateway applicazione

Kubernetes include una funzionalità incorporata che supporta il bilanciamento del carico HTTP (livello 7), denominato [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/). Ingress definisce un set di regole per il modo in cui le istanze di microservizio all'interno di AKS possono essere esposte al mondo esterno. In the previous image, the ingress controller interprets the ingress rules configured for the cluster and automatically configures the Azure Application Gateway. In base a tali regole, il gateway applicazione indirizza il traffico ai microservizi in esecuzione all'interno di AKS. The ingress controller listens for changes to ingress rules and makes the appropriate changes to the Azure Application Gateway.

## <a name="azure-api-management"></a>Gestione API di Azure

Per i sistemi nativi cloud da moderati a su larga scala, è possibile prendere in considerazione Gestione API di Azure.For moderate to large-scale cloud-native systems, you may consider [Azure API Management](https://azure.microsoft.com/services/api-management/). Si tratta di un servizio basato su cloud che non solo risolve le esigenze di Gateway API, ma offre anche un'esperienza amministrativa e per sviluppatori completa. Gestione API è illustrato nella figura 4-6.

![Gestione API di Azure](./media/azure-api-management.png)

**Figura 4-6.** Gestione API di Azure

Per iniziare, Gestione API espone un server gateway che consente l'accesso controllato ai servizi back-end in base a regole e criteri configurabili. Questi servizi possono trovarsi nel cloud di Azure, nel data center puntuale o in altri cloud pubblici. Le chiavi API e i token JWT determinano chi può fare cosa. Tutto il traffico viene registrato per scopi analitici.

Per gli sviluppatori, Gestione API offre un portale per sviluppatori che fornisce l'accesso a servizi, documentazione e codice di esempio per richiamarli. Gli sviluppatori possono usare Swagger/Open API per esaminare gli endpoint del servizio e analizzarne l'utilizzo. Il servizio funziona su tutte le principali piattaforme di sviluppo: .NET, Java, Golang e altro ancora.

Il portale dell'editore espone un dashboard di gestione in cui gli amministratori espongono le API e ne gestiscono il comportamento. È possibile concedere l'accesso al servizio, monitorare l'integrità del servizio e raccogliere dati di telemetria del servizio. Gli amministratori applicano *criteri* a ogni endpoint per influire sul comportamento. [I criteri](https://docs.microsoft.com/azure/api-management/api-management-howto-policies) sono istruzioni predefinite che vengono eseguite in sequenza per ogni chiamata al servizio.  I criteri sono configurati per una chiamata in ingresso, una chiamata in uscita o richiamati in caso di errore. I criteri possono essere applicati in ambiti di servizio diversi per consentire l'ordinamento deterministico quando si combinano i criteri. Il prodotto viene fornito con un gran numero di [politiche](https://docs.microsoft.com/azure/api-management/api-management-policies)predefinite.

Ecco alcuni esempi di come i criteri possono influire sul comportamento dei servizi nativi cloud:Here are examples of how policies can affect the behavior of your cloud-native services:  

- Limitare l'accesso al servizio.
- Applicare l'autenticazione.  
- Limitare le chiamate da una singola origine, se necessario.
- Abilitare il caching.
- Bloccare le chiamate da indirizzi IP specifici.
- Controllare il flusso del servizio.
- Convertire le richieste da SOAP a REST o tra formati di dati diversi, ad esempio da XML a JSON.

Gestione API di Azure può esporre servizi back-end ospitati ovunque, nel cloud o nel data center. Per i servizi legacy che è possibile esporre nei sistemi nativi cloud, supporta entrambe le API REST e SOAP. Anche altri servizi di Azure possono essere esposti tramite Gestione API. È possibile posizionare un'API gestita in un servizio di backup di Azure come Bus di servizio di Azure o App per la logica di Azure.You could place a managed API on top of an Azure backing service like [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) or Azure Logic [Apps](https://azure.microsoft.com/services/logic-apps/). Gestione API di Azure non include il supporto per il bilanciamento del carico incorporato e deve essere usato insieme a un servizio di bilanciamento del carico.

Gestione API di Azure è disponibile in quattro livelli diversi:Azure API Management is available across [four different tiers:](https://azure.microsoft.com/pricing/details/api-management/)

- Developer
- Basic
- Standard
- Premium

Il livello Developer è destinato ai carichi di lavoro e alla valutazione non di produzione. Gli altri livelli offrono progressivamente più potenza, funzionalità e contratti di servizio superiori.The other tiers offerly more power, features, and higher service level agreements (SLa). Il livello Premium offre la [rete virtuale](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) di Azure e il supporto per [più aree.](https://docs.microsoft.com/azure/api-management/api-management-howto-deploy-multi-region) Tutti i livelli hanno un prezzo fisso all'ora.

Recentemente, Microsoft ha annunciato un livello senza server di Gestione API per Gestione API di Azure.Recently, Microsoft announced a [API Management serverless tier](https://azure.microsoft.com/blog/announcing-azure-api-management-for-serverless-architectures/) for Azure API Management. Denominato livello di determinazione dei prezzi di *consumo,* il servizio è una variante di Gestione API progettato intorno al modello di elaborazione senza server. A differenza dei piani tariffari "preallocati" indicati in precedenza, il livello di consumo fornisce il provisioning immediato e i prezzi pay-per-action.

Abilita le funzionalità del gateway API per i casi d'uso seguenti:It enables API Gateway features for the following use cases:

- Microservizi implementati utilizzando tecnologie senza server come [Funzioni](https://docs.microsoft.com/azure/azure-functions/functions-overview) di Azure e [App per la logica](https://azure.microsoft.com/services/logic-apps/)di Azure .
- Risorse del servizio di backup di Azure, ad esempio code e argomenti del bus di servizio, Archiviazione di Azure e altri.
- Microservizi in cui il traffico presenta picchi di grandi dimensioni occasionali ma la maggior parte del tempo è basso.

Il livello di consumo utilizza gli stessi componenti di gestione API del servizio sottostante, ma utilizza un'architettura completamente diversa basata sulle risorse allocate dinamicamente. Si allinea perfettamente con il modello di calcolo senza server:

- Nessuna infrastruttura da gestire.
- Nessuna capacità di inattività.
- Alta disponibilità.
- Ridimensionamento automatico.
- Il costo si basa sull'utilizzo effettivo.
  
Il nuovo livello di consumo è un'ottima scelta per i sistemi nativi cloud che espongono le risorse senza server come API.

> Al momento della scrittura, il livello di consumo è in anteprima nel cloud di Azure.At the time writing, the consumption tier is in preview in the Azure cloud.

## <a name="real-time-communication"></a>Comunicazione in tempo reale

La comunicazione in tempo reale, o push, è un'altra opzione per le applicazioni front-end che comunicano con i sistemi cloud-native back-end su HTTP. Le applicazioni, come i ticker finanziari, l'istruzione online, i giochi e gli aggiornamenti sullo stato di lavoro, richiedono risposte istantanee e in tempo reale dal back-end. Con la normale comunicazione HTTP, non è possibile per il client sapere quando sono disponibili nuovi dati. Il client deve eseguire continuamente *il polling* o l'invio di richieste al server. Con la comunicazione *in tempo reale,* il server può eseguire il push di nuovi dati al client in qualsiasi momento.

I sistemi in tempo reale sono spesso caratterizzati da flussi di dati ad alta frequenza e da un numero elevato di connessioni client simultanee. L'implementazione manuale della connettività in tempo reale può diventare rapidamente complessa, richiedendo un'infrastruttura non banale per garantire scalabilità e messaggistica affidabile ai client connessi. È possibile trovare la gestione di un'istanza della cache Redis di Azure e di un set di servizi di bilanciamento del carico configurati con sessioni permanenti per l'affinità client.

[Il servizio SignalR](https://azure.microsoft.com/services/signalr-service/) di Azure è un servizio di Azure completamente gestito che semplifica la comunicazione in tempo reale per le applicazioni native del cloud. I dettagli di implementazione tecnica, ad esempio il provisioning della capacità, la scalabilità e le connessioni permanenti, vengono astratti. Sono gestiti per te con un contratto di servizio del 99,9%. L'utente si concentra sulle funzionalità dell'applicazione, non sull'impianto idraulico dell'infrastruttura.

Una volta abilitato, un servizio HTTP basato su cloud può eseguire il push degli aggiornamenti del contenuto direttamente ai client connessi, incluse le applicazioni browser, per dispositivi mobili e desktop. I client vengono aggiornati senza la necessità di eseguire il polling del server. Azure SignalR astrae le tecnologie di trasporto che creano connettività in tempo reale, tra cui WebSockets, eventi sul lato Server e polling lungo. Gli sviluppatori si concentrano sull'invio di messaggi a tutti o sottoinsiemi specifici di client connessi.

Nella figura 4-7 viene illustrato un set di client HTTP che si connettono a un'applicazione nativa del cloud con SignalR di Azure abilitato.

![Servizio Azure SignalR](./media/azure-signalr-service.png)

**Figura 4-7.** Servizio Azure SignalR

Un altro vantaggio del servizio SignalR di Azure deriva dall'implementazione di servizi nativi cloud senza server. Forse il codice viene eseguito su richiesta con trigger di Funzioni di Azure.Perhaps your code is executed on demand with Azure Functions triggers. Questo scenario può essere difficile perché il codice non mantiene lunghe connessioni con i client. Il servizio Azure SignalR può gestire questa situazione dal momento che il servizio gestisce già automaticamente le connessioni.

Il servizio SignalR di Azure si integra strettamente con altri servizi di Azure, ad esempio il database SQL di Azure, il bus di servizio o la cache Redis, aprendo molte possibilità per le applicazioni native del cloud.

>[!div class="step-by-step"]
>[Successivo](communication-patterns.md)
>[precedente](service-to-service-communication.md)
