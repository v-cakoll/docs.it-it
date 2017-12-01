---
title: Stato e i dati nelle applicazioni di Docker
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Stato e i dati nelle applicazioni di Docker
keywords: Docker, Microservizi, ASP.NET, contenitore, SQL, CosmosDB, Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 36d0fb9f27ef56b36c380e2fc972c79cff77003e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="state-and-data-in-docker-applications"></a>Stato e i dati nelle applicazioni di Docker

Nella maggior parte dei casi, è possibile considerare un contenitore come un'istanza di un processo. Un processo non mantiene uno stato persistente. Mentre un contenitore è possibile scrivere nello spazio di archiviazione locale, presupponendo che un'istanza sarà intorno all'infinito sarebbe simile a quanto presupponendo che un'unica posizione in memoria siano durevole. Immagini contenitore, ad esempio i processi, devono essere presupposto di avere più istanze o che sono infine essere terminate; Se vengono gestiti con un agente di orchestrazione del contenitore, è necessario considerare che potrebbe essere stata spostate da un nodo o da macchina virtuale a un altro.

Docker offre una funzionalità denominata la *sovrapposizione sistema file*. Implementa un'operazione copy-on-write che archivia informazioni aggiornate al file system del contenitore radice. Tali informazioni sono inoltre l'immagine originale su cui è basato il contenitore. Se il contenitore viene eliminato dal sistema, tali modifiche andranno perdute. Pertanto, sebbene sia possibile salvare lo stato di un contenitore entro lo spazio di archiviazione locale, la progettazione di un sistema di risoluzione di questo problema genererebbe un conflitto con il presupposto di progettazione di contenitore, che per impostazione predefinita è senza stato.

Le soluzioni seguenti consentono di gestire i dati nelle applicazioni di Docker:

-   [I volumi di dati](https://docs.docker.com/engine/tutorials/dockervolumes/) che di montaggio all'host.

-   [Contenitori di volumi di dati](https://docs.docker.com/engine/tutorials/dockervolumes/#creating-and-mounting-a-data-volume-container) che forniscono spazio di archiviazione condiviso tra contenitori tramite un contenitore esterno.

-   [I plug-in di volume](https://docs.docker.com/engine/tutorials/dockervolumes/) che montare i volumi ai servizi remoti, fornendo la persistenza a lungo termine.

-   [Archiviazione di Azure](https://docs.microsoft.com/azure/storage/), che fornisce l'archiviazione geo-distribuibile, fornendo una buona soluzione persistenza a lungo termine per i contenitori.

-   Ad esempio database relazionali remoti [Database SQL di Azure](https://azure.microsoft.com/services/sql-database/) o nei database NoSQL, ad esempio [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction), oppure memorizzare nella cache di servizi come [Redis](https://redis.io/).

Nelle sezioni che seguono vengono fornite ulteriori informazioni su queste opzioni.

**I volumi di dati** sono directory associate dal sistema operativo host per le directory nei contenitori. Quando codice nel contenitore dispone di accesso alla directory, che l'accesso sia effettivamente in una directory nel sistema operativo host. Questa directory non è correlata al ciclo di vita del contenitore e la directory sia accessibile dal codice eseguito direttamente nel sistema operativo host o da un altro contenitore che esegue il mapping nella stessa directory di host a se stessa. Di conseguenza, i volumi di dati sono progettati per rendere persistenti i dati in modo indipendente dal ciclo di vita del contenitore. Se si elimina un contenitore o un'immagine dall'host Docker, i dati persistenti nel volume di dati non viene eliminato. I dati in un volume è accessibile dall'host del sistema operativo anche.

**Contenitori di volumi di dati** sono un'evoluzione di volumi di dati normali. Un contenitore di volumi di dati è un contenitore semplice che include uno o più volumi di dati in esso contenuti. Il contenitore del volume di dati fornisce l'accesso ai contenitori da un punto di montaggio centrale. Questo metodo di accesso ai dati è utile perché estrae il percorso dei dati originali. A parte ciò, il comportamento è simile a quello di un volume di dati normale, pertanto i dati sono persistenti in questo contenitore dedicato in modo indipendente dal ciclo di vita dei contenitori dell'applicazione.

Come illustrato nella figura 4-5, volumi Docker regolari possono essere archiviati di fuori di contenitori stessi ma entro i limiti fisici del server host o VM. Tuttavia, i contenitori di Docker non possono accedere a un volume dal server di un host o macchina virtuale a un altro. In altre parole, con questi volumi, non è possibile gestire i dati condivisi tra contenitori che vengono eseguiti in diversi host Docker

![](./media/image5.png)

**Figura 4-5**. I volumi di dati e origini dati esterne per le applicazioni basate sul contenitore

Inoltre, quando da un agente di orchestrazione vengono gestiti i contenitori di Docker, contenitori potrebbero "Sposta" tra gli host, a seconda che le ottimizzazioni eseguite dal cluster. Pertanto, non è consigliabile utilizzare i volumi di dati per i dati aziendali. Ma sono un meccanismo efficace per lavorare con file di traccia, il file temporale, o simile che non influiranno la coerenza dei dati di business.

**I plug-in di volume** come [Flocker](https://clusterhq.com/flocker/) forniscono accesso ai dati in tutti gli host in un cluster. Mentre non tutti i plug-in di volume vengono creati nello stesso modo, i plug-in di volume in genere forniscono esternalizzati archiviazione affidabile permanente dai contenitori non modificabili.

**Origini dati remote e cache** strumenti come Database SQL di Azure, Azure Cosmos DB o una cache remota come Redis può essere usato in contenitore applicazioni esattamente come vengono utilizzati durante lo sviluppo senza contenitori. Questo è un modo comprovato per archiviare i dati delle applicazioni aziendali.

**Archiviazione di Azure.** Dati di business in genere dovrà essere inserito nel database, come archiviazione di Azure o di risorse esterne. Archiviazione di Azure, in concreto, fornisce i seguenti servizi nel cloud:

-   Archiviazione BLOB archivia i dati di oggetto non strutturati. Un blob può essere qualsiasi tipo di dati di testo o binario, ad esempio i file di documento o un supporto (file immagini, audio e video). Archiviazione BLOB è detta anche archiviazione di oggetti.

-   Archiviazione di file offre spazio di archiviazione condiviso per le applicazioni legacy utilizzando il protocollo SMB standard. Macchine virtuali di Azure e servizi cloud possono condividere i dati dei file nei componenti delle applicazioni tramite condivisioni montate. Applicazioni locali possono accedere dati dei file in una condivisione tramite l'API REST del servizio File.

-   Archiviazione tabelle vengono memorizzati i set di dati strutturati. Archiviazione tabelle è un archivio dati degli attributi di chiave NoSQL, che consente lo sviluppo rapido e l'accesso rapido a quantità elevate di dati.

**I database relazionali e database NoSQL.** Esistono numerose opzioni per i database esterni, dai database relazionali, come i database di SQL Server, PostgreSQL, Oracle o NoSQL Azure Cosmos DB, MongoDB, ecc. Questi database non intende essere spiegato come parte di questa Guida, poiché si trovano in un oggetto completamente diverso.


>[!div class="step-by-step"]
[Precedente] (inserita in un contenitore-monolitico-applications.md) [Avanti] (service-oriented-architecture.md)
