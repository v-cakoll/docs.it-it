---
title: Mapping di eShopOnContainers a Servizi di Azure
description: Mapping di eShopOnContainers ai servizi di Azure come il servizio Azure Kubernetes, il gateway API e il bus di servizio di Azure.
ms.date: 04/20/2020
ms.openlocfilehash: 26fce71ba71f7da643b669396ab59affe592649a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895505"
---
# <a name="mapping-eshoponcontainers-to-azure-services"></a>Mapping di eShopOnContainers a Servizi di Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Sebbene non sia necessario, Azure è particolarmente adatto per supportare il eShopOnContainers perché il progetto è stato creato come applicazione nativa del cloud. L'applicazione viene compilata con .NET Core, quindi può essere eseguita in contenitori Linux o Windows a seconda dell'host docker. L'applicazione è costituita da più microservizi autonomi, ognuno con i propri dati. I diversi microservizi presentano approcci diversi, da semplici operazioni CRUD a modelli DDD e CQRS più complessi. I microservizi comunicano con i client tramite HTTP e tra loro tramite la comunicazione basata su messaggi. L'applicazione supporta più piattaforme anche per i client, poiché adotta HTTP come protocollo di comunicazione standard e include ASP.NET Core e app per dispositivi mobili Novell in esecuzione su piattaforme Android, iOS e Windows.

L'architettura dell'applicazione è illustrata nella figura 2-5. A sinistra si trovano le app client, suddivise in versioni per dispositivi mobili, Web tradizionali e applicazioni a pagina singola (SPA). A destra sono disponibili i componenti lato server che costituiscono il sistema, ognuno dei quali può essere ospitato in contenitori Docker e cluster Kubernetes. L'app Web tradizionale è basata sull'applicazione ASP.NET Core MVC visualizzata in giallo. Questa app e le applicazioni per dispositivi mobili e Web SPA comunicano con i singoli microservizi tramite uno o più gateway API. Il gateway API segue il modello "backend per front-end" (BFF), che significa che ogni gateway è progettato per supportare un client front-end specifico. I singoli microservizi sono elencati a destra dei gateway API e includono sia la logica di business che un tipo di archivio di persistenza. I diversi servizi usano i database SQL Server, le istanze di cache Redis e gli archivi MongoDB/CosmosDB. All'estrema destra è il bus di eventi del sistema usato per la comunicazione tra i microservizi.

![architettura](./media/eshoponcontainers-architecture.png)
eShopOnContainers**Figura 2-5**. Architettura eShopOnContainers.

I componenti lato server di questa architettura vengono mappati facilmente ai servizi di Azure.

## <a name="container-orchestration-and-clustering"></a>Orchestrazione e clustering del contenitore

I servizi ospitati da contenitori dell'applicazione, da ASP.NET Core app MVC a singoli cataloghi e ordini di microservizi, possono essere ospitati e gestiti in Azure Kubernetes Service (AKS). L'applicazione può essere eseguita localmente in Docker e Kubernetes e gli stessi contenitori possono quindi essere distribuiti negli ambienti di gestione temporanea e di produzione ospitati in AKS. Questo processo può essere automatizzato come si vedrà nella sezione successiva.

AKS fornisce servizi di gestione per singoli cluster di contenitori. Tramite l'applicazione vengono distribuiti cluster AKS distinti per ogni microservizio illustrato nel diagramma dell'architettura precedente. Questo approccio consente a ogni singolo servizio di ridimensionarsi in modo indipendente in base alle richieste di risorse. Ogni microservizio può anche essere distribuito in modo indipendente e, idealmente, le distribuzioni non dovrebbero subire alcun tempo di inattività del sistema.

## <a name="api-gateway"></a>API Gateway

L'applicazione eShopOnContainers ha più client front-end e più servizi back-end diversi. Non esiste una corrispondenza uno-a-uno tra le applicazioni client e i microservizi che li supportano. In uno scenario di questo tipo, è possibile che si verifichi una grande complessità quando si scrive il software client per interfacciarsi con i vari servizi back-end in modo sicuro. Ogni client deve affrontare questa complessità in modo autonomo, causando la duplicazione e molte posizioni in cui apportare aggiornamenti quando vengono modificati i servizi o se vengono implementati nuovi criteri.

Gestione API di Azure (gestione API) consente alle organizzazioni di pubblicare le API in modo coerente e gestibile. GESTIONE API è costituito da tre componenti: il gateway API, il portale di amministrazione (il portale di Azure) e un portale per sviluppatori.

Il gateway API accetta le chiamate API e le instrada all'API back-end appropriata. Può anche fornire servizi aggiuntivi come la verifica di chiavi API o token JWT e la trasformazione API in tempo reale senza modifiche al codice, ad esempio per gestire i client che prevedono un'interfaccia precedente.

Il portale di Azure è il punto in cui si definisce lo schema dell'API e si impacchettano API diverse in prodotti. È anche possibile configurare l'accesso utente, visualizzare i report e configurare i criteri per le quote o le trasformazioni.

Il portale per sviluppatori funge da risorsa principale per gli sviluppatori. Fornisce agli sviluppatori la documentazione delle API, una console di test interattiva e segnala il proprio utilizzo. Gli sviluppatori usano anche il portale per creare e gestire i propri account, inclusi il supporto per la sottoscrizione e la chiave API.

Utilizzando Gestione API, le applicazioni possono esporre diversi gruppi di servizi, ognuno dei quali fornisce un back-end per un particolare client front-end. GESTIONE API è consigliato per scenari complessi. Per le esigenze più semplici, è possibile usare l'Ocelot del gateway API Lightweight. L'app eShopOnContainers USA Ocelot per semplicità e perché può essere distribuita nello stesso ambiente dell'applicazione dell'applicazione stessa. [Scopri di più su eShopOnContainers, gestione API e Ocelot.](https://docs.microsoft.com/dotnet/architecture/microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern#azure-api-management)

Un'altra opzione se l'applicazione usa AKS consiste nel distribuire il controller di ingresso del gateway di Azure come Pod nel cluster AKS. In questo modo il cluster si integra con un gateway applicazione Azure, consentendo al gateway di bilanciare il carico del traffico ai pod AKS. [Altre informazioni sul controller di ingresso del gateway di Azure per AKS](https://github.com/Azure/application-gateway-kubernetes-ingress).

## <a name="data"></a>Data

I vari servizi back-end usati da eShopOnContainers hanno requisiti di archiviazione diversi. Diversi microservizi utilizzano database SQL Server. Il microservizio basket si avvale di una cache Redis per la relativa persistenza. Il microservizio località prevede un'API MongoDB per i dati. Azure supporta ognuno di questi formati di dati.

Per il supporto di SQL Server database, Azure offre prodotti per tutto, da database singoli fino a pool elastici di database SQL altamente scalabili. I singoli microservizi possono essere configurati per comunicare con i propri singoli database di SQL Server in modo rapido e semplice. Questi database possono essere ridimensionati in base alle esigenze per supportare ogni microservizio separato in base alle esigenze.

L'applicazione eShopOnContainers archivia il carrello acquisti corrente dell'utente tra le richieste. Questa operazione viene gestita dal microservizio basket che archivia i dati in una cache Redis. In fase di sviluppo, questa cache può essere distribuita in un contenitore, mentre in produzione può usare cache di Azure per Redis. Cache di Azure per Redis è un servizio completamente gestito che offre prestazioni e affidabilità elevate senza la necessità di distribuire e gestire le istanze o i contenitori di redis autonomamente.

Il microservizio locations usa un database NoSQL di MongoDB per la relativa persistenza. Durante lo sviluppo, il database può essere distribuito nel proprio contenitore, mentre in produzione il servizio può sfruttare l' [API Azure Cosmos DB per MongoDB](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction). Uno dei vantaggi di Azure Cosmos DB è la possibilità di sfruttare diversi protocolli di comunicazione, tra cui un'API SQL e API NoSQL comuni, tra cui MongoDB, Cassandra, Gremlin e archiviazione tabelle di Azure. Azure Cosmos DB offre un database distribuito completamente gestito e distribuito a livello globale come servizio che può essere ridimensionato per soddisfare le esigenze dei servizi che la usano.

I dati distribuiti nelle applicazioni native del cloud sono trattati in modo più dettagliato nel [capitolo 5](distributed-data.md).

## <a name="event-bus"></a>Bus di eventi

L'applicazione utilizza gli eventi per comunicare le modifiche tra servizi diversi. Questa funzionalità può essere implementata con un'ampia gamma di implementazioni e localmente l'applicazione eShopOnContainers USA [RabbitMQ](https://www.rabbitmq.com/). Quando è ospitato in Azure, l'applicazione usa il [bus di servizio di Azure](https://docs.microsoft.com/azure/service-bus/) per la messaggistica. Il bus di servizio di Azure è un broker di messaggi di integrazione completamente gestito che consente alle applicazioni e ai servizi di comunicare tra loro in modo separato, affidabile e asincrono. Il bus di servizio di Azure supporta le singole code, nonché *argomenti* distinti per supportare gli scenari del sottoscrittore del server di pubblicazione. L'applicazione eShopOnContainers utilizzerebbe gli argomenti con il bus di servizio di Azure per supportare la distribuzione dei messaggi da un microservizio a qualsiasi altro microservizio necessario per rispondere a un determinato messaggio.

## <a name="resiliency"></a>Resilienza

Una volta distribuita nell'ambiente di produzione, l'applicazione eShopOnContainers sarà in grado di sfruttare i vantaggi di diversi servizi di Azure disponibili per migliorare la resilienza. L'applicazione pubblica i controlli di integrità, che possono essere integrati con Application Insights per fornire report e avvisi in base alla disponibilità dell'app. Le risorse di Azure forniscono anche log di diagnostica che possono essere usati per identificare e correggere i bug e i problemi di prestazioni. I log delle risorse forniscono informazioni dettagliate su quando e come vengono usate le diverse risorse di Azure dall'applicazione. Per altre informazioni sulle funzionalità di resilienza nativa del cloud, vedere il [capitolo 6](resiliency.md).

>[!div class="step-by-step"]
>[Precedente](introduce-eshoponcontainers-reference-app.md)
>[successivo](deploy-eshoponcontainers-azure.md)
