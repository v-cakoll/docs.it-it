---
title: Esempi di progettazione senza server - App senza server
description: Comprendere la varietà di scenari supportati dalle architetture senza server, dalla pianificazione e l'elaborazione basata su eventi ai trigger di file e al processo di flusso.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4e8fda0c1423c881c0807602e11f7c49ff7cfe4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73093560"
---
# <a name="serverless-design-examples"></a>Esempi di progettazione serverless

Esistono molti modelli di progettazione per i modelli senza server. In questa sezione vengono acquisiti alcuni scenari comuni che utilizzano serverless. Ciò che tutti gli esempi hanno in comune è la combinazione fondamentale di un trigger di evento e di logica di business.

## <a name="scheduling"></a>Pianificazione

Le attività di pianificazione sono una funzione comune. Il diagramma seguente mostra un database legacy che non dispone di controlli di integrità appropriati. Il database deve essere pulito periodicamente. La funzione serverless trova dati non validi e li pulisce. Il trigger è un timer che esegue il codice in base a una pianificazione.

![Pianificazione senza server](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>Separazione di responsabilità per query e comandi (CQRS, Command and Query Responsibility Segregation)

Command and Query Responsibility Segregation (CQRS) è un modello che fornisce interfacce diverse per la lettura (o l'esecuzione di query) di dati e operazioni che modificano i dati. Risolve diversi problemi comuni. Nei sistemi basati su CRUD (Create Read Update Delete) tradizionali, possono verificarsi conflitti da un volume elevato di letture e scritture nello stesso archivio dati. Il blocco può verificarsi frequentemente e rallentare notevolmente le letture. Spesso, i dati vengono presentati come compositi di diversi oggetti di dominio e le operazioni di lettura devono combinare i dati di entità diverse.

Utilizzando CQRS, una lettura potrebbe coinvolgere una speciale entità "appiattita" che modella i dati nel modo in cui vengono utilizzati. La lettura viene gestita in modo diverso rispetto a come viene archiviata. Ad esempio, anche se il database può archiviare un contatto come record di intestazione con un record di indirizzo figlio, la lettura potrebbe coinvolgere un'entità con entrambe le proprietà di intestazione e indirizzo. Esistono una miriade di approcci alla creazione del modello di lettura. Potrebbe essere materializzato dai punti di vista. Le operazioni di aggiornamento possono essere incapsulate come eventi isolati che quindi attivano gli aggiornamenti a due modelli diversi. Esistono modelli separati per la lettura e la scrittura.

![Esempio CQRS](./media/cqrs-example.png)

Serverless può supportare il modello CQRS fornendo gli endpoint separati. Una funzione senza server supporta query o letture e una funzione o un set di funzioni senza server diverso gestisce le operazioni di aggiornamento. Una funzione senza server può anche essere responsabile di mantenere aggiornato il modello di lettura e può essere attivata dal feed di [modifiche](https://docs.microsoft.com/azure/cosmos-db/change-feed)del database. Lo sviluppo front-end è semplificato per la connessione agli endpoint necessari. L'elaborazione degli eventi viene gestita nel back-end. Questo modello è anche scalabile per progetti di grandi dimensioni perché team diversi possono lavorare su operazioni diverse.

## <a name="event-based-processing"></a>Elaborazione basata su eventi

Nei sistemi basati su messaggi, gli eventi vengono spesso raccolti in code o negli argomenti relativi ai server di pubblicazione/sottoscrizione su cui intervenire. Questi eventi possono attivare funzioni senza server per eseguire una parte della logica di business. Un esempio di elaborazione basata su eventi sono i sistemi con origine eventi. Viene generato un "evento" per contrassegnare un'attività come completata. Una funzione senza server attivata dall'evento aggiorna il documento di database appropriato. Una seconda funzione serverless può utilizzare l'evento per aggiornare il modello di lettura per il sistema. [Griglia di eventi](https://docs.microsoft.com/azure/event-grid/overview) di Azure offre un modo per integrare gli eventi con le funzioni come sottoscrittori.

> Gli eventi sono messaggi informativi. Per ulteriori informazioni, consultate [Modello di event sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

## <a name="file-triggers-and-transformations"></a>Trigger e trasformazioni di file

Estrai, trasforma e carica (ETL) è una funzione aziendale comune. Serverless è un'ottima soluzione per ETL perché consente l'attivazione del codice come parte di una pipeline. I singoli componenti di codice possono affrontare vari aspetti. Una funzione senza server può scaricare il file, un'altra applica la trasformazione e un'altra carica i dati. Il codice può essere testato e distribuito in modo indipendente, semplificando ne al livello della manutenzione e della scalabilità ovunque necessario.

![Trigger e trasformazioni di file senza server](./media/serverless-file-triggers.png)

Nel diagramma, "cool storage" fornisce i dati che vengono analizzati in Analisi di flusso di [Azure.](https://docs.microsoft.com/azure/stream-analytics) Eventuali problemi riscontrati nel flusso di dati attivano una funzione di Azure per risolvere l'anomalia.

## <a name="asynchronous-background-processing-and-messaging"></a>Elaborazione asincrona in background e messaggistica

La messaggistica asincrona e l'elaborazione in background consentono alle applicazioni di avviare i processi senza dover attendere. Un esempio di elaborazione asincrona è un'app OCR. Un'immagine viene inviata e accodata per l'elaborazione. La scansione dell'immagine per estrarre il testo può richiedere tempo e al termine dell'invio di una notifica. Serverless è in grado di gestire sia la chiamata che il risultato in questo scenario.

## <a name="web-apps-and-apis"></a>App Web e API

Uno scenario più diffuso per i serverless sono le applicazioni a più livelli, in genere quelle in cui il livello dell'interfaccia utente è un'app Web. La popolarità delle applicazioni a pagina singola (SPA) è aumentata di recente. Le app SPA eseguono il rendering di una singola pagina, quindi si basano sulle chiamate API e sui dati restituiti per eseguire il rendering dinamico della nuova interfaccia utente senza ricaricare una pagina intera. Il rendering lato client fornisce un'applicazione molto più veloce e reattiva all'utente finale.

Gli endpoint senza server attivati dalle chiamate HTTP possono essere usati per gestire le richieste API. Ad esempio, una società di servizi pubblicitari può chiamare una funzione senza server con informazioni sul profilo utente per richiedere pubblicità personalizzata. La funzione senza server restituisce l'annuncio personalizzato e la pagina Web ne esegue il rendering.

![API Web senza server](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>Data Pipeline

Le funzioni senza server possono essere utilizzate per facilitare una pipeline di dati. In questo esempio, un file attiva una funzione per convertire i dati in un file CSV in righe di dati in una tabella. La tabella organizzata consente a un dashboard di Power BI di presentare l'analisi all'utente finale.

![Pipeline di dati senza server](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Elaborazione del flusso

I dispositivi e i sensori spesso generano flussi di dati che devono essere elaborati in tempo reale. Esistono diverse tecnologie in grado di acquisire messaggi e flussi da [Hub eventi](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) e [Hub IoT](https://docs.microsoft.com/azure/iot-hub) a [Bus di servizio](https://docs.microsoft.com/azure/service-bus). Indipendentemente dal trasporto, serverless è un meccanismo ideale per l'elaborazione dei messaggi e dei flussi di dati non appena vengono in arrivo. Serverless può essere scalato rapidamente per soddisfare la domanda di grandi volumi di dati. Il codice senza server può applicare la logica di business per analizzare i dati e l'output in un formato strutturato per l'azione e l'analisi.

![Elaborazione del flusso senza server](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>Gateway API

Un gateway API fornisce un singolo punto di ingresso per i client e quindi indirizza in modo intelligente le richieste ai servizi back-end. È utile gestire grandi set di servizi. Può inoltre gestire il controllo delle versioni e semplificare lo sviluppo connettendo facilmente i client ad ambienti diversi. Serverless può gestire il ridimensionamento back-end di singoli microservizi durante la presentazione di un singolo front-end tramite un gateway API.

![Gateway API senza server](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>Risorse consigliate

- [Griglia di eventi di AzureAzure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Hub IoT di AzureAzure IoT Hub](https://docs.microsoft.com/azure/iot-hub)
- [Problemi e soluzioni per la gestione dei dati distribuiti](../microservices/architect-microservice-container-applications/distributed-data-management.md)
- [Progettazione di microservizi: identificazione dei limiti dei microservizi](https://docs.microsoft.com/azure/architecture/microservices/microservice-boundaries)
- [Hub eventi](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
- [Modello di approvvigionamento di eventi](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)
- [Implementazione dello schema Circuit Breaker](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md)
- [IoT Hub](https://docs.microsoft.com/azure/iot-hub)
- [Bus di servizio](https://docs.microsoft.com/azure/service-bus)
- [Uso del supporto del feed delle modifiche in Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[Successivo](serverless-architecture-considerations.md)
>[precedente](azure-serverless-platform.md)
