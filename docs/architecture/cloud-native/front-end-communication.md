---
title: Comunicazione client front-end
description: Informazioni sul modo in cui i client front-end comunicano con i sistemi nativi del cloud
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: 89f13ea1c9ecbe92e959ae63a4c21bf7775f8943
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895580"
---
# <a name="front-end-client-communication"></a>Comunicazione client front-end

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In un sistema nativo del cloud, i client front-end (applicazioni per dispositivi mobili, Web e desktop) richiedono un canale di comunicazione per interagire con i microservizi di back-end indipendenti.  

Quali sono le opzioni?

Per semplificare le operazioni, un client front-end può *comunicare direttamente* con i microservizi back-end, come illustrato nella figura 4-2.

![Comunicazione diretta da client a servizio](./media/direct-client-to-service-communication.png)

**Figura 4-2.** Comunicazione diretta da client a servizio

Con questo approccio, ogni microservizio dispone di un endpoint pubblico accessibile dai client front-end. In un ambiente di produzione è necessario posizionare un servizio di bilanciamento del carico davanti ai microservizi, indirizzando il traffico in proporzione.

Sebbene sia semplice da implementare, la comunicazione diretta dei client sarebbe accettabile solo per le semplici applicazioni di microservizi. Questo modello associa strettamente i client front-end ai servizi back-end di base, aprendo lo sportello per una serie di problemi, tra cui:

- Predisposizione dei client al refactoring del servizio back-end.
- Una superficie di attacco più ampia come servizi back-end di base vengono esposti direttamente.
- Duplicazione delle problematiche trasversali in ogni microservizio.
- Codice client eccessivamente complesso: i client devono tenere traccia di più endpoint e gestire gli errori in modo resiliente.

Un modello di progettazione cloud ampiamente accettato è invece implementare un [servizio gateway API](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) tra le applicazioni front-end e i servizi back-end. Il modello è illustrato nella figura 4-3.

![Modello del gateway API](./media/api-gateway-pattern.png)

**Figura 4-3.** Modello del gateway API

Nella figura precedente si noti il modo in cui il servizio gateway API astrae i microservizi Core back-end. Implementato come API Web, funge da *proxy inverso*, indirizzando il traffico in ingresso ai microservizi interni.

Il gateway isola il client dal partizionamento e dal refactoring del servizio interno. Se si modifica un servizio back-end, lo si adatta al gateway senza compromettere il client. È anche la prima linea di difesa per le problematiche trasversali, ad esempio l'identità, la memorizzazione nella cache, la resilienza, la misurazione e la limitazione. Molti di questi problemi trasversali possono essere disattivati dai servizi di base back-end al gateway, semplificando i servizi back-end.

È necessario prestare attenzione per semplificare e velocizzare il gateway API. In genere, la logica di business viene mantenuta fuori dal gateway. Un gateway complesso rischia di diventare un collo di bottiglia e, infine, un monolitico. I sistemi più grandi spesso espongono più gateway API segmentati in base al tipo di client (mobile, Web, desktop) o alla funzionalità back-end. Il modello [back-end per](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) front-end fornisce indicazioni per l'implementazione di più gateway. Il modello è illustrato nella figura 4-4.

![Modello del gateway API](./media/backend-for-frontend-pattern.png)

**Figura 4-4.** Back-end per modello front-end

Si noti che nella figura precedente viene inviato il traffico in ingresso a un gateway API specifico, in base al tipo di client: Web, dispositivi mobili o app desktop. Questo approccio è utile in quanto le funzionalità di ogni dispositivo differiscono in modo significativo tra il fattore di forma, le prestazioni e le limitazioni di visualizzazione. In genere, le applicazioni per dispositivi mobili espongono meno funzionalità rispetto a un browser o applicazioni desktop. Ogni gateway può essere ottimizzato in base alle funzionalità e alle funzionalità del dispositivo corrispondente.

Per iniziare, è possibile creare il proprio servizio gateway API. Una ricerca rapida di GitHub fornirà molti esempi. Sono tuttavia disponibili diversi Framework e prodotti Gateway commerciali.

## <a name="ocelot-gateway"></a>Gateway Ocelot

Per le semplici applicazioni native del cloud .NET, è possibile prendere in considerazione il [gateway Ocelot](https://github.com/ThreeMammals/Ocelot). Ocelot è un gateway API Open source creato per i microservizi .NET che richiedono un punto di ingresso unificato nel sistema. È leggero, veloce e scalabile.

Come qualsiasi gateway API, la funzionalità principale è quella di inviare le richieste HTTP in ingresso ai servizi downstream. Supporta inoltre un'ampia gamma di funzionalità che possono essere configurate in una pipeline middleware di .NET Core. Il set di funzionalità è illustrato nella tabella seguente.

|Funzionalità di Ocelot  | |
| :-------- | :-------- |
| Routing | Authentication |
| Aggregazione delle richieste | Autorizzazione |
| Individuazione dei servizi (con Consul e Eureka) | Limitazione |
| Bilanciamento del carico. | Registrazione, traccia |
| Memorizzazione nella cache | Intestazioni/trasformazione stringa di query |
| Pass-through correlazione | Middleware personalizzato |
| QoS (Quality of Service) | Criteri di ripetizione |

Ogni gateway Ocelot specifica gli indirizzi upstream e downstream e le funzionalità configurabili in un file di configurazione JSON. Il client invia una richiesta HTTP al gateway Ocelot. Una volta ricevuta, Ocelot passa l'oggetto HttpRequest attraverso la relativa pipeline e lo modifica nello stato specificato dalla relativa configurazione. Alla fine della pipeline, Ocelot crea una nuova HTTPResponseObject e la passa al servizio downstream. Per la risposta, Ocelot inverte la pipeline e Invia la risposta al client.

Ocelot è disponibile come pacchetto NuGet. È destinato allo standard NET 2,0, rendendolo compatibile sia con .NET Core 2.0 che con .NET Framework 4.6.1 + Runtime. Ocelot si integra con qualsiasi elemento che parla HTTP ed eseguito sulle piattaforme supportate da .NET Core: Linux, macOS e Windows. Ocelot è estendibile e supporta molte piattaforme moderne, tra cui contenitori Docker, servizi Kubernetes di Azure o altri cloud pubblici.  Ocelot si integra con pacchetti open source come [console](https://www.consul.io), [GraphQL](https://graphql.org)e [Eureka](https://github.com/Netflix/eureka)di Netflix.

Si consideri Ocelot per semplici applicazioni native del cloud che non richiedono il set completo di funzionalità di un gateway API commerciale.

## <a name="azure-application-gateway"></a>Gateway applicazione di Azure

Per i requisiti del gateway semplice, è possibile prendere in considerazione [applicazione Azure gateway](https://docs.microsoft.com/azure/application-gateway/overview). Disponibile come servizio Azure [PaaS](https://azure.microsoft.com/overview/what-is-paas/), include funzionalità gateway di base, ad esempio il routing degli URL, la terminazione SSL e un Web Application Firewall. Il servizio supporta le funzionalità [di bilanciamento del carico di livello 7](https://www.nginx.com/resources/glossary/layer-7-load-balancing/) . Con il livello 7, è possibile indirizzare le richieste in base al contenuto effettivo di un messaggio HTTP, non solo ai pacchetti di rete TCP di basso livello.

In questo libro si evangelizzano i sistemi nativi che ospitano il cloud in [Kubernetes](https://www.infoworld.com/article/3268073/what-is-kubernetes-your-next-application-platform.html). Un agente di orchestrazione dei contenitori, Kubernetes automatizza la distribuzione, il ridimensionamento e le problematiche operative dei carichi di lavoro in contenitori. Applicazione Azure gateway può essere configurato come gateway API per il cluster del [servizio Azure Kubernetes](https://azure.microsoft.com/services/kubernetes-service/) .

Il controller di ingresso del [gateway applicazione](https://azure.github.io/application-gateway-kubernetes-ingress/) consente a applicazione Azure gateway di funzionare direttamente con il [servizio Azure Kubernetes](https://azure.microsoft.com/services/kubernetes-service/). La figura 4,5 illustra l'architettura.

![Controller di ingresso del gateway applicazione](./media/application-gateway-ingress-controller.png)

**Figura 4-5.** Controller di ingresso del gateway applicazione

Kubernetes include una funzionalità incorporata che supporta il bilanciamento del carico HTTP (livello 7), denominato [ingresso](https://kubernetes.io/docs/concepts/services-networking/ingress/). Il traffico in ingresso definisce un set di regole per il modo in cui le istanze del microservizio all'interno di AKS possono essere esposte al mondo esterno. Nell'immagine precedente il controller di ingresso interpreta le regole di ingresso configurate per il cluster e configura automaticamente il gateway applicazione Azure. In base a queste regole, il gateway applicazione instrada il traffico ai microservizi in esecuzione all'interno di AKS. Il controller di ingresso è in ascolto delle modifiche alle regole di ingresso e apporta le modifiche appropriate al gateway applicazione Azure.

## <a name="azure-api-management"></a>Gestione API di Azure

Per i sistemi nativi basati su cloud da moderato a larga scala, è possibile prendere in considerazione [gestione API di Azure](https://azure.microsoft.com/services/api-management/). Si tratta di un servizio basato su cloud che non solo risolve le esigenze del gateway API, ma offre un'esperienza di sviluppo e amministrazione completa. Gestione API è illustrato nella figura 4-6.

![Gestione API di Azure](./media/azure-api-management.png)

**Figura 4-6.** Gestione API di Azure

Per iniziare, gestione API espone un server gateway che consente l'accesso controllato ai servizi back-end in base a regole e criteri configurabili. Questi servizi possono trovarsi nel cloud di Azure, nella data center locale o in altri cloud pubblici. Le chiavi API e i token JWT determinano chi può eseguire le operazioni. Tutto il traffico viene registrato a scopo analitico.

Per gli sviluppatori, gestione API offre un portale per sviluppatori che fornisce l'accesso a servizi, documentazione e codice di esempio per richiamarli. Gli sviluppatori possono usare l'API spavalderia/Open per esaminare gli endpoint di servizio e analizzarne l'utilizzo. Il servizio funziona nelle principali piattaforme di sviluppo: .NET, Java, Golang e altro ancora.

Il portale di pubblicazione espone un dashboard di gestione in cui gli amministratori espongono le API e ne gestiscono il comportamento. È possibile concedere l'accesso al servizio, il monitoraggio dell'integrità del servizio e la telemetria del servizio raccolti. Gli amministratori applicano i *criteri* a ogni endpoint per influire sul comportamento. I [criteri](https://docs.microsoft.com/azure/api-management/api-management-howto-policies) sono istruzioni predefinite che vengono eseguite in sequenza per ogni chiamata al servizio.  I criteri sono configurati per una chiamata in ingresso, una chiamata in uscita o richiamati su un errore. I criteri possono essere applicati in diversi ambiti del servizio come per abilitare l'ordinamento deterministico quando si combinano i criteri. Il prodotto viene fornito con un numero elevato di [criteri](https://docs.microsoft.com/azure/api-management/api-management-policies)predefiniti.

Di seguito sono riportati alcuni esempi di come i criteri possono influire sul comportamento dei servizi nativi del cloud:  

- Limitare l'accesso al servizio.
- Applicare l'autenticazione.  
- Limitare le chiamate da un'unica origine, se necessario.
- Abilitare il caching.
- Blocca le chiamate da indirizzi IP specifici.
- Controllare il flusso del servizio.
- Converte le richieste da SOAP a REST o tra formati di dati diversi, ad esempio da XML a JSON.

Gestione API di Azure può esporre servizi back-end ospitati ovunque, nel cloud o nel data center. Per i servizi legacy che è possibile esporre nei sistemi nativi del cloud, supporta API REST e SOAP. Anche altri servizi di Azure possono essere esposti tramite gestione API. È possibile inserire un'API gestita in un servizio di backup di Azure, ad esempio il [bus di servizio di Azure](https://azure.microsoft.com/services/service-bus/) o app per la logica di [Azure](https://azure.microsoft.com/services/logic-apps/). Gestione API di Azure non include il supporto predefinito per il bilanciamento del carico e deve essere usato insieme a un servizio di bilanciamento del carico.

Gestione API di Azure è disponibile in [quattro livelli diversi](https://azure.microsoft.com/pricing/details/api-management/):

- Sviluppatore
- Basic
- Standard
- Premium

Il livello Developer è destinato ai carichi di lavoro e alla valutazione non di produzione. Gli altri livelli offrono una potenza progressiva, funzionalità e contratti di servizio (SLA) di livello superiore. Il livello Premium fornisce la [rete virtuale di Azure](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) e il supporto per più [aree](https://docs.microsoft.com/azure/api-management/api-management-howto-deploy-multi-region). Tutti i livelli prevedono un prezzo fisso all'ora.

Il cloud di Azure offre anche un [livello senza server](https://azure.microsoft.com/blog/announcing-azure-api-management-for-serverless-architectures/) per gestione API di Azure. Denominato piano *tariffario a consumo*, il servizio è una variante di gestione API progettata intorno al modello di elaborazione senza server. A differenza dei piani tariffari "pre-allocati" indicati in precedenza, il livello di consumo fornisce il provisioning istantaneo e i prezzi con pagamento in base all'azione.

Abilita le funzionalità del gateway API per i casi d'uso seguenti:

- Microservizi implementati usando tecnologie senza server come [funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-overview) e [app](https://azure.microsoft.com/services/logic-apps/)per la logica di Azure.
- Risorse del servizio di backup di Azure, ad esempio code e argomenti del bus di servizio, archiviazione di Azure e altro ancora.
- Microservizi in cui il traffico presenta picchi di grandi dimensioni, ma rimane basso la maggior parte del tempo.

Il livello consumo usa gli stessi componenti di gestione API del servizio sottostanti, ma usa un'architettura completamente diversa basata su risorse allocate in modo dinamico. Si allinea perfettamente al modello di elaborazione senza server:

- Nessuna infrastruttura da gestire.
- Nessuna capacità inattiva.
- Disponibilità elevata.
- Ridimensionamento automatico.
- Il costo è basato sull'utilizzo effettivo.
  
Il nuovo livello di consumo è un'ottima scelta per i sistemi nativi del cloud che espongono risorse senza server come API.

## <a name="real-time-communication"></a>Comunicazione in tempo reale

La comunicazione in tempo reale o push è un'altra opzione per le applicazioni front-end che comunicano con i sistemi nativi del cloud back-end tramite HTTP. Le applicazioni, ad esempio i puntatori finanziari, la formazione online, i giochi e gli aggiornamenti di avanzamento dei processi, richiedono risposte istantanee e in tempo reale dal back-end. Con la normale comunicazione HTTP, il client non è in grado di stabilire quando sono disponibili nuovi dati. Il client deve eseguire continuamente il *polling* o inviare richieste al server. Con la comunicazione in *tempo reale* , il server può effettuare il push dei nuovi dati al client in qualsiasi momento.

I sistemi in tempo reale sono spesso caratterizzati da flussi di dati ad alta frequenza e da un numero elevato di connessioni client simultanee. L'implementazione manuale della connettività in tempo reale può diventare rapidamente complessa, richiedendo un'infrastruttura non semplice per garantire la scalabilità e la messaggistica affidabile ai client connessi. È possibile trovare la gestione di un'istanza di cache Redis di Azure e di un set di bilanciamento del carico configurato con sessioni permanenti per l'affinità client.

Il [servizio Azure SignalR](https://azure.microsoft.com/services/signalr-service/) è un servizio di Azure completamente gestito che semplifica la comunicazione in tempo reale per le applicazioni native del cloud. I dettagli di implementazione tecnica, ad esempio il provisioning della capacità, il ridimensionamento e le connessioni permanenti, vengono estratti. Sono gestite per l'utente con un contratto di servizio del 99,9%. È possibile concentrarsi sulle funzionalità dell'applicazione, non sul Plumbing dell'infrastruttura.

Una volta abilitata, un servizio HTTP basato sul cloud può effettuare il push degli aggiornamenti del contenuto direttamente ai client connessi, incluse le applicazioni browser, per dispositivi mobili e desktop. I client vengono aggiornati senza la necessità di eseguire il polling del server. Azure SignalR astrae le tecnologie di trasporto che creano connettività in tempo reale, inclusi WebSocket, eventi sul lato server e polling prolungato. Gli sviluppatori si concentrano sull'invio di messaggi a tutti o a subset specifici di client connessi.

La figura 4-7 Mostra un set di client HTTP che si connettono a un'applicazione nativa del cloud con Azure SignalR abilitato.

![Servizio Azure SignalR](./media/azure-signalr-service.png)

**Figura 4-7.** Servizio Azure SignalR

Un altro vantaggio del servizio Azure SignalR è costituito dall'implementazione di servizi nativi del cloud senza server. È probabile che il codice venga eseguito su richiesta con i trigger di funzioni di Azure. Questo scenario può risultare complesso perché il codice non mantiene connessioni lunghe con i client. Il servizio Azure SignalR può gestire questa situazione dal momento che il servizio gestisce già automaticamente le connessioni.

Il servizio Azure SignalR si integra strettamente con altri servizi di Azure, ad esempio il database SQL di Azure, il bus di servizio o cache Redis, aprendo molte possibilità per le applicazioni native del cloud.

>[!div class="step-by-step"]
>[Precedente](communication-patterns.md)
>[successivo](service-to-service-communication.md)
