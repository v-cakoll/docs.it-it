---
title: Scenari aziendali di esempio e casi d'uso per le app senza server
description: Impara a usare senza server un approccio pratico accedendo ad esempi che variano dall'elaborazione di immagini al supporto per dispositivi mobili e alle pipeline ETL.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: 3cb3b73325fccc327ccf17f7298048f2eeb3577a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158450"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Scenari di business serverless e casi d'uso

Esistono molti casi d'uso e scenari per le applicazioni senza server. Questo capitolo include esempi che illustrano i diversi scenari. Gli scenari includono collegamenti alla documentazione correlata e ai repository di codice sorgente pubblico. Gli esempi in questo capitolo consentono di iniziare a creare e implementare soluzioni senza server.

## <a name="big-data-processing"></a>Elaborazione di Big Data

![Diagramma di mapping/riduzione](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

Questo esempio USA senza server per eseguire un'operazione di mapping/riduzione su un set di Big Data. Determina la velocità media delle corse dei taxi gialli di New York al giorno nel 2017.

[Elaborazione di Big Data: MapReduce senza server in Azure](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a>Creare applicazioni senza server: Lab pratico

Informazioni su come usare le funzioni per eseguire la logica sul lato server e creare architetture senza server.

- Scelta del migliore servizio di Azure per la tua azienda
- Creazione di funzioni di Azure
- Trigger
- Funzioni di concatenamento
- Flussi di lavoro a esecuzione prolungata
- Monitoraggio
- Sviluppo, test e distribuzione

[Crea applicazioni senza server](https://docs.microsoft.com/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a>Recensioni dei clienti

Questo esempio mostra i nuovi strumenti di funzioni di Azure per le librerie di classi C# in Visual Studio. Creare un sito Web in cui i clienti inviano recensioni di prodotti archiviate in BLOB di archiviazione di Azure e CosmosDB. Aggiungere una funzione di Azure per eseguire la moderazione automatica delle revisioni dei clienti usando servizi cognitivi di Azure. Usare una coda di archiviazione di Azure per separare il sito Web dalla funzione.

[App Customer revisioni con servizi cognitivi](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a>Supporto per immagini Linux Docker

Questo esempio illustra come creare un `Dockerfile` per compilare ed eseguire funzioni di Azure in un contenitore Docker Linux.

[Funzioni di Azure in Linux](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a>Elaborazione e convalida di file

In questo esempio viene analizzato un set di file CSV da clienti ipotetici. Garantisce che tutti i file necessari per un "batch" del cliente siano pronti, quindi convalida la struttura di ogni file. Vengono presentate diverse soluzioni usando funzioni di Azure, app per la logica e Durable Functions.

[Elaborazione e convalida di file con funzioni di Azure, app per la logica e Durable Functions](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a>Visualizzazione dei dati del gioco

![Telemetria del gioco](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

Un esempio di come uno sviluppatore può implementare una soluzione di visualizzazione dati nell'editor per il gioco. In realtà, un plug-in Unreal Engine 4 e un plug-in Unity sono stati sviluppati usando questo esempio come back-end. Il componente del servizio è indipendente dal motore di gioco.

[Visualizzazione telemetria del gioco in-Editor](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a>GraphQL

Creare una funzione senza server che espone un'API GraphQL.

[Funzioni senza server per GraphQL](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a>Inoltro Reliable Edge di Internet delle cose

![Architettura dell'it](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

Questo esempio implementa un nuovo protocollo di comunicazione per consentire la comunicazione upstream affidabile dai dispositivi Internet. Automatizza il rilevamento e il recupero del gap di dati.

[Inoltro Reliable Edge](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a>Architettura di riferimento per i microservizi

![Architettura di riferimento](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

Un'architettura di riferimento che illustra il processo decisionale necessario per la progettazione, lo sviluppo e la distribuzione dell'applicazione rideshare by Relecloud (una società fittizia). Sono incluse istruzioni pratiche per la configurazione e la distribuzione di tutti i componenti dell'architettura.

[Architettura di riferimento per microservizi senza server](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a>Esegui la migrazione delle app console a senza server

Questo esempio è una funzione generica`.csx` (file) che può essere usata per convertire qualsiasi applicazione console in un servizio Web http in funzioni di Azure. È sufficiente modificare un file di configurazione e specificare i `.exe`parametri di input che verranno passati come argomenti a.

[Eseguire app console in funzioni di Azure](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a>Senza server per dispositivi mobili

Funzioni di Azure è facile da implementare e gestire e accessibile tramite HTTP. Sono un ottimo modo per implementare un'API per un'applicazione per dispositivi mobili. Microsoft offre ottimi strumenti multipiattaforma per iOS, Android e Windows con Novell. Di conseguenza, Novell e funzioni di Azure operano insieme. Questo articolo illustra come implementare una funzione di Azure nella portale di Azure o in Visual Studio inizialmente e creare un client multipiattaforma con Novell. Forms in esecuzione in Android, iOS e Windows.

[Implementazione di una semplice funzione di Azure con un client Novell. Forms](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)

## <a name="serverless-messaging"></a>Messaggistica senza server

Questo esempio illustra come usare il modello di fan-out di Durable Functions per caricare un numero arbitrario di messaggi in un numero qualsiasi di sessioni/partizioni. È destinato a bus di servizio, Hub eventi o code di archiviazione. L'esempio aggiunge anche la possibilità di utilizzare tali messaggi con un'altra funzione di Azure e di caricare i dati temporali risultanti in un altro hub eventi. I dati vengono quindi inseriti in servizi di analisi come Azure Esplora dati.

[Produrre e utilizzare messaggi tramite il bus di servizio, Hub eventi e le code di archiviazione con funzioni di Azure](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a>Risorse consigliate

- [Funzioni di Azure in Linux](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [Elaborazione di Big Data: MapReduce senza server in Azure](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [Crea applicazioni senza server](https://docs.microsoft.com/learn/paths/create-serverless-applications/)
- [App Customer revisioni con servizi cognitivi](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [Elaborazione e convalida di file con funzioni di Azure, app per la logica e Durable Functions](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- [Implementazione di una semplice funzione di Azure con un client Novell. Forms](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [Visualizzazione telemetria del gioco in-Editor](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [Inoltro Reliable Edge](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [Produrre e utilizzare messaggi tramite il bus di servizio, Hub eventi e le code di archiviazione con funzioni di Azure](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [Eseguire app console in funzioni di Azure](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [Funzioni senza server per GraphQL](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [Architettura di riferimento per microservizi senza server](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
>[Precedente](orchestration-patterns.md)
>[successivo](serverless-conclusion.md)
