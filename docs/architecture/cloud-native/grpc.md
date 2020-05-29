---
title: gRPC
description: Informazioni su gRPC, il suo ruolo in applicazioni native del cloud e su come si differenzia dalla comunicazione RESTful HTTP.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 35a8325dd82e946d88b09b223287e2871be88ffa
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201326"
---
# <a name="grpc"></a>gRPC

Fino a questo libro abbiamo incentrato sulla comunicazione [basata su REST](https://docs.microsoft.com/azure/architecture/best-practices/api-design) . Abbiamo visto che REST è uno stile di architettura flessibile che definisce le operazioni basate su CRUD sulle risorse di entità. I client interagiscono con le risorse su HTTP con un modello di comunicazione di tipo richiesta/risposta. Mentre REST è ampiamente implementato, una tecnologia di comunicazione più recente, gRPC, ha raggiunto un notevole slancio nella community nativa del cloud.

## <a name="what-is-grpc"></a>Che cos'è gRPC?

gRPC è un Framework moderno e a prestazioni elevate che evolve il protocollo [RPC (Remote Procedure Call)](https://en.wikipedia.org/wiki/Remote_procedure_call) obsoleto. A livello di applicazione, gRPC semplifica la messaggistica tra i client e i servizi back-end. Originato da Google, gRPC è open source e fa parte dell'ecosistema [cloud native Computing Foundation (CNCF)](https://www.cncf.io/) delle offerte native del cloud. CNCF considera gRPC un [progetto di incubazione](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc). L'incubazione significa che gli utenti finali usano la tecnologia nelle applicazioni di produzione e il progetto ha un numero integro di collaboratori.

Una tipica app client gRPC esporrà una funzione locale in-process che implementa un'operazione aziendale. Dietro le quinte, tale funzione locale richiama un'altra funzione in un computer remoto. Ciò che sembra essere una chiamata locale essenzialmente diventa una chiamata out-of-process trasparente a un servizio remoto. Il plumbing RPC astrae la comunicazione, la serializzazione e l'esecuzione di rete da punto a punto tra i computer.

Nelle applicazioni native del cloud, gli sviluppatori spesso lavorano in linguaggi di programmazione, Framework e tecnologie. Questa *interoperabilità* complica i contratti di messaggio e il plumbing necessario per le comunicazioni tra piattaforme.  gRPC fornisce un "livello orizzontale uniforme" che astrae questi problemi. Gli sviluppatori codificano nella propria piattaforma nativa incentrata sulle funzionalità aziendali, mentre gRPC gestisce il plumbing delle comunicazioni.

gRPC offre supporto completo tra gli stack di sviluppo più diffusi, tra cui Java, JavaScript, C#, go, Swift e NodeJS.

## <a name="grpc-benefits"></a>Vantaggi di gRPC

gRPC Usa HTTP/2 per il protocollo di trasporto. Sebbene compatibile con HTTP 1,1, HTTP/2 presenta numerose funzionalità avanzate:

- Protocollo binario per il trasporto di dati, a differenza di HTTP 1,1, che invia dati come testo non crittografato.
- Supporto del multiplexing per l'invio di più richieste parallele sulla stessa connessione-HTTP 1,1 limita l'elaborazione a un messaggio di richiesta/risposta alla volta.
- Comunicazione bidirezionale full duplex per l'invio simultaneo di richieste client e risposte al server.
- Il flusso predefinito consente le richieste e le risposte per trasmettere in modo asincrono set di dati di grandi dimensioni.

gRPC è leggero ed efficiente. Può essere fino a 8x più veloce rispetto alla serializzazione JSON con messaggi 60-80% inferiori. Nel gergo di Microsoft [Windows Communication Foundation (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) , le prestazioni gRPC superano la velocità e l'efficienza delle [associazioni NetTcp](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8)altamente ottimizzate. Diversamente da NetTCP, che predilige Microsoft stack, gRPC è multipiattaforma.

## <a name="protocol-buffers"></a>Buffer di protocollo

gRPC adotta una tecnologia open source denominata buffer del [protocollo](https://developers.google.com/protocol-buffers/docs/overview). Forniscono un formato di serializzazione estremamente efficiente e indipendente dalla piattaforma per la serializzazione di messaggi strutturati che i servizi inviano tra loro. Usando un linguaggio IDL (Multi-Platform Interface Definition Language), gli sviluppatori definiscono un contratto di servizio per ogni microservizio. Il contratto, implementato come file basato su testo `.proto` , descrive i metodi, gli input e gli output per ogni servizio. Lo stesso file di contratto può essere usato per i client e i servizi gRPC basati su diverse piattaforme di sviluppo.

Usando il file proto, il compilatore protobuf `protoc` genera il codice client e del servizio per la piattaforma di destinazione. Il codice include i componenti seguenti:

- Oggetti fortemente tipizzati, condivisi dal client e dal servizio, che rappresentano le operazioni del servizio e gli elementi dati per un messaggio.
- Classe base fortemente tipizzata con il plumbing di rete necessario che il servizio gRPC remoto può ereditare ed estendere.
- Stub client che contiene il plumbing necessario per richiamare il servizio gRPC remoto.

In fase di esecuzione, ogni messaggio viene serializzato come rappresentazione protobuf standard ed è scambiato tra il client e il servizio remoto. Diversamente da JSON o XML, i messaggi protobuf vengono serializzati come byte binari compilati.

Il libro [gRPC per sviluppatori WCF](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/), disponibile nel sito dell'architettura Microsoft, fornisce una copertura approfondita dei buffer di gRPC e del protocollo.

## <a name="grpc-support-in-net"></a>supporto di gRPC in .NET

gRPC è integrato in .NET Core 3,0 SDK e versioni successive. Gli strumenti seguenti lo supportano:

- Visual Studio 2019, versione 16,3 o successiva, con il carico di lavoro sviluppo Web installato.
- Visual Studio Code
- INTERFACCIA della riga di comando DotNet

L'SDK include strumenti per il routing degli endpoint, IoC incorporato e la registrazione. Il server Web gheppio open source supporta le connessioni HTTP/2. La figura 4-20 Mostra un modello di Visual Studio 2019 che include un progetto Skeleton per un servizio gRPC. Si noti che .NET Core supporta completamente Windows, Linux e macOS.

![Supporto di gRPC in Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Figura 4-20**. supporto di gRPC in Visual Studio 2019
  
La figura 4-21 illustra il servizio Skeleton gRPC generato dall'impalcatura incorporata inclusa in Visual Studio 2019.  

![progetto gRPC in Visual Studio 2019](./media/grpc-project.png  )

**Figura 4-21**. progetto gRPC in Visual Studio 2019

Nella figura precedente si noti il file di descrizione proto e il codice del servizio. Come si vedrà a breve, Visual Studio genera una configurazione aggiuntiva sia nella classe di avvio che nel file di progetto sottostante.

## <a name="grpc-usage"></a>utilizzo di gRPC

Preferire gRPC per gli scenari seguenti:

- Comunicazione da microservizi back-end sincrona a microservizi in cui è necessaria una risposta immediata per continuare l'elaborazione.
- Ambienti poliglotti che devono supportare piattaforme di programmazione miste.
- Comunicazione con bassa latenza e velocità effettiva elevata in cui le prestazioni sono critiche.
- Comunicazione in tempo reale da punto a punto: gRPC è in grado di eseguire il push dei messaggi in tempo reale senza polling e offre un supporto eccellente per lo streaming bidirezionale.
- Ambienti vincolati alla rete: i messaggi gRPC binari sono sempre più piccoli di un messaggio JSON equivalente basato su testo.

Al momento, in questo articolo, gRPC viene usato principalmente con i servizi back-end. La maggior parte dei browser moderni non è in grado di fornire il livello di controllo HTTP/2 richiesto per supportare un client gRPC front-end. Ciò premesso, esiste un' [iniziativa](https://devblogs.microsoft.com/aspnet/grpc-web-experiment/) che consente la comunicazione gRPC dalle app basate su browser compilate con le tecnologie JavaScript o blazer webassembly. [GRPC-Web per .NET](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md) consente a un ASP.NET Core app gRPC di supportare le funzionalità di gRPC nelle app del browser:

- Client fortemente tipizzati e generati dal codice
- Compatta messaggi protobuf
- Streaming Server

## <a name="grpc-implementation"></a>implementazione di gRPC

L'architettura di riferimento del microservizio, [eShop sui contenitori](https://github.com/dotnet-architecture/eShopOnContainers), di Microsoft, illustra come implementare i servizi gRPC nelle applicazioni .NET Core. La figura 4-22 presenta l'architettura back-end.

![Architettura back-end per eShop nei contenitori](./media/eshop-with-aggregators.png)

**Figura 4-22**. Architettura back-end per eShop nei contenitori

Nella figura precedente si noti il modo in cui eShop accetta il [back-end per il modello](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) front-end (BFF) esponendo più gateway API. Il modello BFF è stato discusso più indietro in questo capitolo. Prestare particolare attenzione al microservizio Aggregator (in grigio) che risiede tra il gateway dell'API di acquisti Web e i microservizi di acquisti back-end. L'aggregatore riceve una singola richiesta da un client, la invia a diversi microservizi, aggrega i risultati e li invia al client richiedente. Queste operazioni richiedono in genere la comunicazione sincrona per produrre una risposta immediata. In eShop le chiamate back-end di aggregator vengono eseguite usando gRPC, come illustrato nella figura 4-23.

![gRPC in eShop nei contenitori](./media/grpc-implementation.png)

**Figura 4-23**. gRPC in eShop nei contenitori

la comunicazione gRPC richiede componenti client e server. Nella figura precedente si noti il modo in cui l'aggregatore di acquisti implementa un client gRPC. Il client esegue chiamate gRPC sincrone (in rosso) a microservizi back-end, ognuno dei quali implementa un server gRPC. Sia il client che il server sfruttano il plumbing gRPC incorporato dalla .NET Core SDK. Gli *Stub* lato client forniscono il plumbing per richiamare chiamate gRPC remote. I componenti lato server forniscono il plumbing gRPC che le classi di servizio personalizzate possono ereditare e utilizzare.

I microservizi che espongono sia un'API RESTful che la comunicazione gRPC richiedono più endpoint per gestire il traffico. Si apre un endpoint che ascolta il traffico HTTP per le chiamate RESTful e un altro per le chiamate gRPC. L'endpoint gRPC deve essere configurato per il protocollo HTTP/2 richiesto per la comunicazione gRPC.

Sebbene si sforzi per separare i microservizi con i modelli di comunicazione asincrona, alcune operazioni richiedono chiamate dirette. gRPC deve essere la scelta principale per la comunicazione sincrona diretta tra microservizi. Il protocollo di comunicazione ad alte prestazioni, basato su HTTP/2 e i buffer del protocollo, lo rende una scelta perfetta.

## <a name="looking-ahead"></a>Ricerca avanti

In futuro, gRPC continuerà a ottenere la trazione per i sistemi nativi del cloud. I vantaggi delle prestazioni e la facilità di sviluppo sono molto interessanti. REST, tuttavia, sarà probabilmente da molto tempo. Eccelle per le API esposte pubblicamente e per motivi di compatibilità con le versioni precedenti.

>[!div class="step-by-step"]
>[Precedente](service-to-service-communication.md) 
> [Avanti](service-mesh-communication-infrastructure.md)
