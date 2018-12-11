---
title: Esempi di progettazione senza server - App senza server
description: Comprendere la varietà di scenari supportati da architetture senza server, dalla pianificazione e l'elaborazione basata su eventi per i trigger di file e il processo di flusso.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: cf46c601ac6aa401c7c37bd64c1f8981589ebd2e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53146709"
---
# <a name="serverless-design-examples"></a>Esempi di progettazione senza server

Esistono molti modelli di progettazione che esistono per senza server. In questa sezione consente di acquisire alcuni scenari comuni che usano senza server. Ciò che tutti gli esempi hanno in comune è la combinazione fondamentale di un'evento trigger e logica di business.

## <a name="scheduling"></a>Pianificazione

Pianificazione delle attività è una funzione comune. Il diagramma seguente illustra un database legacy che non dispone di controlli di integrità appropriato. Il database debba essere sottoposti a scrubbing periodicamente. La funzione senza server trova i dati non è validi e la pulizia. Si tratta di un timer che viene eseguito il codice in base a una pianificazione.

![Pianificazione senza server](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>Comando and Query Responsibility Segregation (CQRS)

Command and Query Responsibility Segregation (CQRS) è un modello che fornisce dati di diverse interfacce per la lettura (o l'esecuzione di query) e le operazioni che modificano i dati. Risolve alcuni problemi comuni. Nei sistemi di creare lettura Update eliminazione (CRUD) basato su tradizionali, possono verificarsi conflitti di volume elevato di letture e scritture allo stesso archivio dati. Il blocco può spesso si verificano e rallentare notevolmente le letture. Spesso, i dati sono presentati come una combinazione di diversi oggetti di dominio e le operazioni di lettura debba combinare dati provenienti da entità diverse.

Usa il modello CQRS, un'operazione di lettura può implicare un'entità "bidimensionale" speciale che modella il modo in cui vengono utilizzati i dati. La lettura viene gestita in modo diverso da quello di archiviazione. Ad esempio, anche se il database può archiviare un contatto come un record di intestazione con un record di indirizzo figlio, la lettura potrebbe comportare un'entità con intestazione e le proprietà di indirizzo. Esistono molti approcci per creare il modello di lettura. Si potrebbe essere materializzato dalle viste. Operazioni di aggiornamento potrebbero essere incapsulate come eventi isolati che quindi attivano gli aggiornamenti a due modelli diversi. Modelli separati esistono per la lettura e scrittura.

![Esempio CQRS](./media/cqrs-example.png)

Un'infrastruttura senza server possono contenere il modello CQRS, fornendo gli endpoint separati. Una funzione senza server supporta le query o operazioni di lettura e una funzione senza server diversa o un set di funzioni gestisce le operazioni di aggiornamento. Una funzione senza server può inoltre essere responsabile per mantenere aggiornato il modello di lettura e possono essere attivata tramite il database [feed di modifiche](https://docs.microsoft.com/azure/cosmos-db/change-feed). Sviluppo di front-end è stato semplificato per la connessione agli endpoint necessari. L'elaborazione di eventi viene gestita nel back-end. Questo modello può essere adatta anche per progetti di grandi dimensioni perché diversi team potrebbe funzionare in diverse operazioni.

## <a name="event-based-processing"></a>Elaborazione basata su eventi

Nei sistemi basati su messaggi, gli eventi vengono spesso raccolti nelle code o argomenti di pubblicazione/sottoscrizione su cui intervenire. Questi eventi possono attivare le funzioni senza server per l'esecuzione di una parte della logica di business. Un esempio di elaborazione basato su eventi è il sistema di origine evento. Per contrassegnare un'attività come completata, viene generato un "evento". Una funzione senza server attivata dall'evento aggiorna il documento per il database appropriato. Una seconda funzione senza server può usare l'evento per aggiornare il modello di lettura per il sistema. [Griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/overview) consente di integrare gli eventi con funzioni come sottoscrittori.

> Gli eventi sono i messaggi informativi. Per altre informazioni, vedere [Event Sourcing pattern](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

## <a name="file-triggers-and-transformations"></a>I trigger di file e le trasformazioni

Estrarre, trasformare e caricamento (ETL) è una funzione di business comune. Senza server è un'ottima soluzione per ETL perché consente al codice essere attivato come parte di una pipeline. I componenti di codice singoli consente di risolvere vari aspetti. Una funzione senza server possa scaricare il file, un altro si applica la trasformazione e un altro carica i dati. Il codice può essere testato e distribuito in modo indipendente, rendendo più semplice da gestire e ridimensionare dove necessario.

![Le trasformazioni e i trigger di file senza server](./media/serverless-file-triggers.png)

Nel diagramma, "archiviazione ad accesso sporadico" fornisce i dati viene analizzato [Azure Stream Analitica](https://docs.microsoft.com/azure/stream-analytics). Eventuali problemi riscontrati nel flusso di dati attivano una funzione di Azure per risolvere l'anomalia.

## <a name="asynchronous-background-processing-and-messaging"></a>L'elaborazione in background asincrone e messaggistica

Messaggistica asincrona e l'elaborazione in background consentono alle applicazioni avviare i processi senza dover aspettare. Un esempio di elaborazione asincrona è un'app OCR. Un'immagine viene inviata e accodata per l'elaborazione. La scansione dell'immagine per estrarre il testo può richiedere tempo e dopo aver terminato una notifica viene inviata. Serverless può gestire sia la chiamata e il risultato in questo scenario.

## <a name="web-apps-and-apis"></a>App web e API

Uno scenario comune per senza server sono a più livelli delle applicazioni, in genere quelli in cui il livello UI è un'app web. La popolarità di applicazioni di pagina singola (SPA) è venuti recentemente. Le app SPA eseguire il rendering di una singola pagina, quindi si basano su chiamate API e i dati restituiti per eseguire il rendering dinamico nuova interfaccia utente senza il ricaricamento di una pagina completa. Il rendering lato client offre un'applicazione molto più veloci ed efficienti per l'utente finale.

Gli endpoint senza server attivati tramite chiamate HTTP sono utilizzabile per gestire le richieste dell'API. Ad esempio, una società di servizi di Active Directory possa chiamare una funzione senza server con informazioni sul profilo utente per richiedere di annunci pubblicitari personalizzati. La funzione senza server restituisce ad personalizzato e la pagina web viene eseguito il rendering.

![API web senza server](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>Pipeline di dati

Le funzioni senza server sono utilizzabile per facilitare una pipeline di dati. In questo esempio, un file attiva una funzione per convertire i dati in un file CSV alle righe di dati in una tabella. La tabella organizzata consente a un dashboard di Power BI presentare analitica per l'utente finale.

![Pipeline di dati senza server](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Elaborazione di Stream

Dispositivi e sensori spesso generano flussi di dati che devono essere elaborati in tempo reale. Esistono una serie di tecnologie che è possibile acquisire i messaggi e i flussi provenienti da [hub eventi](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) e [dell'IoT Hub](https://docs.microsoft.com/azure/iot-hub) al [del Bus di servizio](/service-bus). Indipendentemente dal trasporto, senza server è un meccanismo ideale per elaborare i messaggi e i flussi di dati non appena si verificano. Un'infrastruttura senza server possono essere ridimensionate rapidamente per soddisfare la domanda di grandi volumi di dati. Il codice senza server è possibile applicare la logica di business per analizzare i dati e l'output in un formato strutturato per azione e analitica.

![Elaborazione di flussi senza server](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>Gateway API

Un gateway API fornisce un singolo punto di ingresso per i client e quindi instrada in modo intelligente le richieste ai servizi back-end. È utile gestire grandi set di servizi. Può anche gestire il controllo delle versioni e semplificare lo sviluppo da connettere con facilità i client per ambienti diversi. Serverless può gestire la scalabilità dei singoli microservizi presentando un unico front-end tramite un gateway API back-end.

![Gateway API senza server](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>Risorse consigliate

* [Griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/overview)
* [Hub IoT di Azure](https://docs.microsoft.com/azure/iot-hub)
* [Problemi e soluzioni per la gestione dei dati distribuiti](../microservices-architecture/architect-microservice-container-applications/distributed-data-management.md)
* [Progettazione di microservizi: identificazione dei limiti dei microservizi](https://docs.microsoft.com/azure/architecture/microservices/microservice-boundaries)
* [Hub eventi](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
* [Modello di origine eventi](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)
* [Implementazione dello schema di interruttori](../microservices-architecture/implement-resilient-applications/implement-circuit-breaker-pattern.md)
* [Hub IoT](https://docs.microsoft.com/azure/iot-hub)
* [Bus di servizio](https://docs.microsoft.com/azure/service-bus)
* [Utilizzo con la modifica del supporto del feed in Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[Precedente](serverless-architecture-considerations.md)
>[Successivo](azure-serverless-platform.md)