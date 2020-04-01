---
title: gRPC (informazioni in base al t
description: Informazioni su gRPC, il suo ruolo nelle applicazioni native cloud e su come differisce dalla comunicazione HTTP RESTful.
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 28a07ad5ec105d3fc5b65e4cf0ac0cd85eb16627
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524173"
---
# <a name="grpc"></a>gRPC (informazioni in base al t

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Finora, in questo libro, ci siamo concentrati sulla comunicazione basata su [REST.](https://docs.microsoft.com/azure/architecture/best-practices/api-design) Abbiamo visto che REST è uno stile architettonico flessibile che definisce le operazioni basate su CRUD sulle risorse dell'entità. I client interagiscono con le risorse tramite HTTP con un modello di comunicazione richiesta/risposta. Mentre REST è ampiamente implementato, una tecnologia di comunicazione più recente, gRPC, ha guadagnato enorme slancio in tutta la comunità cloud-nativa.

## <a name="what-is-grpc"></a>Che cos'è gRPC?

gRPC è un framework moderno e ad alte prestazioni che evolve il protocollo [RPC (Remote Procedure Call)](https://en.wikipedia.org/wiki/Remote_procedure_call) secolare. A livello di applicazione, gRPC semplifica la messaggistica tra client e servizi back-end. Originario di Google, gRPC è open source e fa parte dell'ecosistema [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) delle offerte cloud native. CNCF considera gRPC un [progetto di incubazione](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc). L'incubazione significa che gli utenti finali utilizzano la tecnologia nelle applicazioni di produzione e il progetto ha un numero sano di contributori.

Una tipica applicazione client gRPC esporrà una funzione locale in-process che implementa un'operazione aziendale. Sotto le coperte, tale funzione locale richiama un'altra funzione su un computer remoto. Quella che sembra essere una chiamata locale diventa essenzialmente una chiamata out-of-process trasparente a un servizio remoto. L'impianto idraulico RPC astrae la comunicazione di rete point-to-point, la serializzazione e l'esecuzione tra i computer.

Nelle applicazioni native del cloud, gli sviluppatori spesso lavorano tra linguaggi di programmazione, framework e tecnologie. Questa *interoperabilità* complica i contratti di messaggio e l'impianto idraulico necessario per la comunicazione multipiattaforma.  gRPC fornisce uno "strato orizzontale uniforme" che astrae questi problemi. Il codice degli sviluppatori nella loro piattaforma nativa si concentra sulle funzionalità aziendali, mentre gRPC gestisce l'impianto idraulico di comunicazione.

gRPC offre un supporto completo per la maggior parte degli stack di sviluppo più diffusi, tra cui Java, JavaScript, C,, Go, Swift e NodeJS.

## <a name="grpc-benefits"></a>Vantaggi gRPC

gRPC utilizza HTTP/2 per il protocollo di trasporto. Sebbene sia compatibile con HTTP 1.1, HTTP/2 offre molte funzionalità avanzate:

- Protocollo binario per il trasporto dei dati, a differenza di HTTP 1.1, che invia i dati come testo non crittografato.
- Supporto multiplexing per l'invio di più richieste parallele sulla stessa connessione - HTTP 1.1 limita l'elaborazione a un messaggio di richiesta/risposta alla volta.
- Comunicazione full-duplex bidirezionale per l'invio simultaneo di richieste client e risposte del server.
- Streaming integrato che consente richieste e risposte per trasmettere in modo asincrono set di dati di grandi dimensioni.

gRPC è leggero e altamente performante. Può essere fino a 8 volte più veloce della serializzazione JSON con messaggi di dimensioni inferiori del 60-80%. Nel linguaggio di linguaggio Microsoft [Windows Communication Foundation (WCF),](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) le prestazioni gRPC superano la velocità e l'efficienza delle associazioni NetTCP altamente [ottimizzate.](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8) A differenza di NetTCP, che favorisce lo stack Microsoft, gRPC è multipiattaforma.

## <a name="protocol-buffers"></a>Buffer di protocollo

gRPC adotta una tecnologia open source denominata [Protocol Buffers](https://developers.google.com/protocol-buffers/docs/overview). Forniscono un formato di serializzazione altamente efficiente e indipendente dalla piattaforma per la serializzazione di messaggi strutturati che i servizi vengono inviati tra loro. Utilizzando un IDL (Interface Definition Language) multipiattaforma, gli sviluppatori definiscono un contratto di servizio per ogni microservizio. Il contratto, implementato come `.proto` file basato su testo, descrive i metodi, gli input e gli output per ogni servizio. Lo stesso file di contratto può essere utilizzato per client e servizi gRPC basati su piattaforme di sviluppo diverse.

Utilizzando il file proto, il compilatore Protobuf, `protoc`, genera codice client e servizio per la piattaforma di destinazione. Il codice include i seguenti componenti:

- Oggetti fortemente tipizzati, condivisi dal client e dal servizio, che rappresentano le operazioni del servizio e gli elementi di dati per un messaggio.
- Classe base fortemente tipizzata con l'impianto idraulico di rete richiesto che il servizio gRPC remoto può ereditare ed estendere.
- Uno stub client che contiene l'impianto idraulico necessario per richiamare il servizio gRPC remoto.

In fase di esecuzione, ogni messaggio viene serializzato come rappresentazione Protobuf standard e scambiato tra il client e il servizio remoto. A differenza di JSON o XML, i messaggi Protobuf vengono serializzati come byte binari compilati.

Il libro, [gRPC per gli sviluppatori WCF](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/), disponibile nel sito Microsoft Architecture , fornisce una copertura approfondita dei buffer gRPC e protocollo.

## <a name="grpc-support-in-net"></a>Supporto gRPC in .NET

gRPC è integrato in .NET Core 3.0 SDK o versione successiva. I seguenti strumenti lo supportano:

- Visual Studio 2019, versione 16.3 o successiva, con il carico di lavoro di sviluppo Web installato.
- Visual Studio Code
- il dotnet CLI

L'SDK include strumenti per il routing degli endpoint, l'IoC incorporato e la registrazione. Il server Web Kestrel open-source supporta le connessioni HTTP/2. Figura 4-20 Mostra un modello di Visual Studio 2019 che esegue lo scaffolding di un progetto di scheletro per un servizio gRPC. Tieni presente che .NET Core supporta completamente Windows, Linux e macOS.

![Supporto gRPC in Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Figura 4-20**. Supporto gRPC in Visual Studio 2019
  
Figura 4-21 Mostra lo scheletro servizio gRPC generato dallo scaffolding incorporato incluso in Visual Studio 2019.  

![Progetto gRPC in Visual Studio 2019](./media/grpc-project.png  )

**Figura 4-21**. Progetto gRPC in Visual Studio 2019

Nella figura precedente, prendere nota del file di descrizione proto e del codice del servizio. Come si vedrà a breve, Visual Studio genera una configurazione aggiuntiva sia nella classe Startup e nel file di progetto sottostante.

## <a name="grpc-usage"></a>Utilizzo gRPC

Favor gRPC per i seguenti scenari:

- Comunicazione sincrona tra microservizi di back-end e microservizio in cui è necessaria una risposta immediata per continuare l'elaborazione.
- Ambienti poliglotta che devono supportare piattaforme di programmazione miste.
- Bassa latenza e comunicazione ad alta velocità effettiva in cui le prestazioni sono critiche.
- Comunicazione point-to-point in tempo reale - gRPC può spingere i messaggi in tempo reale senza polling e ha un eccellente supporto per lo streaming bidirezionale.
- Ambienti vincolati di rete: i messaggi gRPC binari sono sempre più piccoli di un messaggio JSON basato su testo equivalente.

Al momento, di questa scrittura, gRPC viene utilizzato principalmente con i servizi back-end. La maggior parte dei browser moderni non è in grado di fornire il livello di controllo HTTP/2 necessario per supportare un client gRPC front-end. Detto questo, c'è una [prima iniziativa](https://devblogs.microsoft.com/aspnet/grpc-web-experiment/) che consente la comunicazione gRPC da applicazioni basate su browser create con JavaScript o Blazor WebAssembly tecnologie. [Il gRPC-Web per .NET](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md) consente a un'app gRPC ASP.NET Core di supportare le funzionalità gRPC nelle app browser:

- Client generati codice fortemente tipizzato
- Messaggi Protobuf compatti
- Streaming server

## <a name="grpc-implementation"></a>Implementazione gRPC

L'architettura di riferimento dei microservizi, [eShop su container](https://github.com/dotnet-architecture/eShopOnContainers), di Microsoft, mostra come implementare i servizi gRPC nelle applicazioni .NET Core. La figura 4-22 presenta l'architettura back-end.

![Architettura back-end per eShop nei contenitoriBackend architecture for eShop on Containers](./media/eshop-with-aggregators.png)

**Figura 4-22**. Architettura back-end per eShop nei contenitoriBackend architecture for eShop on Containers

Nella figura precedente, notare come eShop abbraccia il [modello Backend for Frontends](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) (BFF) esponendo più gateway API. Abbiamo discusso il modello BFF in precedenza in questo capitolo. Prestare particolare attenzione al microservizio Aggregator (in grigio) che si trova tra il gateway API Web-Shopping e i microservizi di shopping back-end. L'aggregatore riceve una singola richiesta da un client, la invia a vari microservizi, li aggrega i risultati e li invia al client richiedente. Tali operazioni richiedono in genere una comunicazione sincrona per produrre una risposta immediata. In eShop, le chiamate back-end dall'aggregatore vengono eseguite utilizzando gRPC come illustrato nella Figura 4-23.

![gRPC in eShop su contenitori](./media/grpc-implementation.png)

**Figura 4-23**. gRPC in eShop su contenitori

La comunicazione gRPC richiede componenti client e server. Nella figura precedente, si noti come l'aggregatore shopping implementa un client gRPC. Il client effettua chiamate gRPC sincrone (in rosso) ai microservizi back-end, ognuna delle quali implementa un server gRPC. Sia il client che il server sfruttano l'impianto idraulico gRPC incorporato di .NET Core 3.0 SDK. Gli *stub* lato client forniscono l'impianto idraulico per richiamare chiamate gRPC remote. I componenti lato server forniscono l'impianto idraulico gRPC che le classi di servizi personalizzate possono ereditare e utilizzare.

I microservizi che espongono sia un'API RESTful che una comunicazione gRPC richiedono più endpoint per gestire il traffico. Si aprirebbe un endpoint in ascolto del traffico HTTP per le chiamate RESTful e un altro per le chiamate gRPC. L'endpoint gRPC deve essere configurato per il protocollo HTTP/2 necessario per la comunicazione gRPC.

Mentre ci sforziamo di disaccoppiare i microservizi con modelli di comunicazione asincrona, alcune operazioni richiedono chiamate dirette. gRPC dovrebbe essere la scelta principale per la comunicazione sincrona diretta tra microservizi. Il suo protocollo di comunicazione ad alte prestazioni, basato su HTTP/2 e buffer di protocollo, lo rendono una scelta perfetta.

## <a name="looking-ahead"></a>Guardare al futuro

Guardando al futuro, gRPC continuerà a guadagnare trazione per i sistemi cloud-native. I vantaggi in termini di prestazioni e la facilità di sviluppo sono convincenti. Tuttavia, REST sarà probabilmente in giro per un lungo periodo di tempo. Eccellente per le API esposte pubblicamente e per motivi di compatibilità con le versioni precedenti.

>[!div class="step-by-step"]
>[Successivo](service-to-service-communication.md)
>[precedente](service-mesh-communication-infrastructure.md)
