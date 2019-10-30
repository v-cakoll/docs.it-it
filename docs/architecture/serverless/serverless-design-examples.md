---
title: Esempi di progettazione senza server-app senza server
description: Comprendere la varietà di scenari supportati dalle architetture senza server, dalla pianificazione e dall'elaborazione basata su eventi ai trigger di file e al processo di flusso.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4e8fda0c1423c881c0807602e11f7c49ff7cfe4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73093560"
---
# <a name="serverless-design-examples"></a>Esempi di progettazione serverless

Esistono molti modelli di progettazione disponibili per i server. Questa sezione acquisisce alcuni scenari comuni che usano senza server. Ciò che tutti gli esempi hanno in comune è la combinazione fondamentale di un trigger di evento e di una logica di business.

## <a name="scheduling"></a>Pianificazione

La pianificazione delle attività è una funzione comune. Il diagramma seguente illustra un database legacy che non dispone di controlli di integrità appropriati. È necessario ripulire periodicamente il database. La funzione senza server trova dati non validi e li pulisce. Il trigger è un timer che esegue il codice in base a una pianificazione.

![Pianificazione senza server](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>Separazione di responsabilità per query e comandi (CQRS)

Separazione di responsabilità per query e comandi (CQRS) è un modello che fornisce interfacce diverse per la lettura o l'esecuzione di query su dati e operazioni che modificano i dati. Risolve diversi problemi comuni. Nei sistemi basati su Create Read Update Delete (CRUD) tradizionali i conflitti possono verificarsi da un volume elevato di letture e scritture nello stesso archivio dati. Il blocco può verificarsi spesso e rallenta notevolmente le letture. Spesso i dati vengono presentati come un composto di diversi oggetti di dominio e le operazioni di lettura devono combinare i dati di entità diverse.

Con CQRS, una lettura può coinvolgere un'entità speciale "flat" che modella i dati nel modo in cui vengono usati. La lettura viene gestita in modo diverso rispetto al modo in cui viene archiviata. Ad esempio, anche se il database può archiviare un contatto come record di intestazione con un record di indirizzo figlio, la lettura può coinvolgere un'entità con proprietà di intestazione e indirizzo. Sono disponibili innumerevoli approcci alla creazione del modello di lettura. Potrebbe essere materializzato dalle viste. Le operazioni di aggiornamento possono essere incapsulate come eventi isolati che quindi attivano gli aggiornamenti di due modelli diversi. Sono disponibili modelli distinti per la lettura e la scrittura.

![Esempio di CQRS](./media/cqrs-example.png)

Senza server può adattarsi al modello CQRS fornendo gli endpoint separati. Una funzione senza server consente di gestire query o letture, mentre un'altra funzione o set di funzioni senza server gestisce le operazioni di aggiornamento. Una funzione senza server può anche essere responsabile dell'aggiornamento del modello di lettura e può essere attivato dal [feed delle modifiche](https://docs.microsoft.com/azure/cosmos-db/change-feed)del database. Lo sviluppo front-end è semplificato per la connessione agli endpoint necessari. L'elaborazione degli eventi viene gestita nel back-end. Questo modello viene inoltre ridimensionato correttamente per i progetti di grandi dimensioni, perché i team diversi possono lavorare su diverse operazioni.

## <a name="event-based-processing"></a>Elaborazione basata su eventi

Nei sistemi basati su messaggi, gli eventi vengono spesso raccolti in code o argomenti di pubblicazione/Sottoscrittore su cui agire. Questi eventi possono attivare funzioni senza server per eseguire una parte della logica di business. Un esempio di elaborazione basata su eventi è costituito da sistemi originati da eventi. Viene generato un "evento" per contrassegnare un'attività come completata. Una funzione senza server attivata dall'evento aggiorna il documento di database appropriato. Una seconda funzione senza server può utilizzare l'evento per aggiornare il modello di lettura per il sistema. [Griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/overview) offre un modo per integrare gli eventi con funzioni come sottoscrittori.

> Gli eventi sono messaggi informativi. Per altre informazioni, vedere [modello](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)di origine eventi.

## <a name="file-triggers-and-transformations"></a>Trigger e trasformazioni di file

L'estrazione, la trasformazione e il caricamento (ETL) è una funzione di business comune. Senza server è un'ottima soluzione per ETL perché consente l'attivazione del codice come parte di una pipeline. I singoli componenti di codice possono risolvere diversi aspetti. Una funzione senza server può scaricare il file, un altro applica la trasformazione e un altro carica i dati. Il codice può essere testato e distribuito in modo indipendente, semplificando la gestione e la scalabilità in base alle esigenze.

![Trigger e trasformazioni di file senza server](./media/serverless-file-triggers.png)

Nel diagramma "cool storage" fornisce dati analizzati in analisi di flusso di [Azure](https://docs.microsoft.com/azure/stream-analytics). Eventuali problemi rilevati nel flusso di dati attivano una funzione di Azure per risolvere l'anomalia.

## <a name="asynchronous-background-processing-and-messaging"></a>Elaborazione e messaggistica in background asincrona

La messaggistica asincrona e l'elaborazione in background consentono alle applicazioni di avviare i processi senza dover attendere. Un esempio di elaborazione asincrona è un'app OCR. Un'immagine viene inviata e accodata per l'elaborazione. L'analisi dell'immagine per estrarre il testo potrebbe richiedere tempo e, una volta completata, viene inviata una notifica. Senza server è possibile gestire sia la chiamata che il risultato in questo scenario.

## <a name="web-apps-and-apis"></a>App Web e API

Uno scenario comune per le applicazioni senza server è l'applicazione a più livelli, in genere quella in cui il livello dell'interfaccia utente è un'app Web. La popolarità delle applicazioni a pagina singola (SPA) è stata recentemente interstata. Le app SPA eseguono il rendering di una singola pagina, quindi si basano sulle chiamate API e sui dati restituiti per eseguire dinamicamente il rendering di una nuova interfaccia utente senza ricaricare una pagina completa. Il rendering lato client fornisce un'applicazione molto più veloce e reattiva all'utente finale.

Per gestire le richieste API, è possibile usare endpoint senza server attivati da chiamate HTTP. Ad esempio, una società di servizi ad può chiamare una funzione senza server con informazioni sul profilo utente per richiedere la pubblicità personalizzata. La funzione senza server restituisce l'annuncio personalizzato e la pagina Web ne esegue il rendering.

![API Web senza server](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>Pipeline di dati

Le funzioni senza server possono essere utilizzate per facilitare una pipeline di dati. In questo esempio un file attiva una funzione per convertire i dati in un file CSV nelle righe di dati di una tabella. La tabella organizzata consente a un dashboard Power BI di presentare l'analisi all'utente finale.

![Pipeline di dati senza server](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Elaborazione del flusso

I dispositivi e i sensori spesso generano flussi di dati che devono essere elaborati in tempo reale. Sono disponibili numerose tecnologie che consentono di acquisire messaggi e flussi da Hub [eventi](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) e dall' [Hub](https://docs.microsoft.com/azure/iot-hub) di tutto il [bus di servizio](https://docs.microsoft.com/azure/service-bus). Indipendentemente dal trasporto, il server è un meccanismo ideale per l'elaborazione dei messaggi e dei flussi di dati non appena arrivano. La scalabilità senza server può essere ridotta rapidamente per soddisfare la richiesta di grandi volumi di dati. Il codice senza server può applicare la logica di business per analizzare i dati e l'output in un formato strutturato per l'analisi e l'azione.

![Elaborazione di flussi senza server](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>Gateway API

Un gateway API fornisce un singolo punto di ingresso per i client e quindi instrada in modo intelligente le richieste ai servizi back-end. È utile per gestire set di servizi di grandi dimensioni. Consente inoltre di gestire il controllo delle versioni e semplificare lo sviluppo grazie alla semplice connessione dei client a ambienti diversi. Senza server è possibile gestire il ridimensionamento del back-end dei singoli microservizi, presentando un singolo front-end tramite un gateway API.

![Gateway API senza server](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>Risorse consigliate

- [Griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/overview)
- [Hub Azure](https://docs.microsoft.com/azure/iot-hub)
- [Problemi e soluzioni per la gestione dei dati distribuiti](../microservices/architect-microservice-container-applications/distributed-data-management.md)
- [Progettazione di microservizi: identificazione dei limiti dei microservizi](https://docs.microsoft.com/azure/architecture/microservices/microservice-boundaries)
- [Hub eventi](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
- [Modello di origine eventi](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)
- [Implementazione dello schema di interruttori](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md)
- [Hub Internet delle cose](https://docs.microsoft.com/azure/iot-hub)
- [Bus di servizio](https://docs.microsoft.com/azure/service-bus)
- [Utilizzo del supporto del feed delle modifiche in Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[Precedente](serverless-architecture-considerations.md)
>[Successivo](azure-serverless-platform.md)
