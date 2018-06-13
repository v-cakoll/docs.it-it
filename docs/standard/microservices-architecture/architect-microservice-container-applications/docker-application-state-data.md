---
title: Stato e dati nelle applicazioni di Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Stato e dati nelle applicazioni di Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: c5cfe617335d8150d069149ac87f79206b1b5eca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578655"
---
# <a name="state-and-data-in-docker-applications"></a>Stato e dati nelle applicazioni di Docker

Nella maggior parte dei casi è possibile considerare un contenitore come un'istanza di un processo. Un processo non mantiene uno stato persistente. Anche se un contenitore può scrivere nella propria archiviazione locale, presupporre che un'istanza resti disponibile all'infinito sarebbe come presupporre che una singola posizione in memoria sia durevole. Si deve presupporre che le immagini del contenitore, come i processi, abbiano più istanze o che queste vengano infine terminate. Se vengono gestite con un agente di orchestrazione dei contenitori, dovrebbero poter essere spostate da un nodo o da una macchina virtuale a un'altra.

Docker offre una funzionalità denominata *sovrimpressione di file system*. Implementa un'operazione di copia su scrittura che archivia le informazioni aggiornate nel file system radice del contenitore. Tali informazioni vengono aggiunte all'immagine originale su cui si basa il contenitore. Se il contenitore viene eliminato dal sistema, le modifiche andranno perdute. Quindi, anche se è possibile salvare lo stato di un contenitore all'interno dell'archiviazione locale, progettare un sistema in base a questo presupposto genererebbe un conflitto con una delle impostazioni predefinite della progettazione di contenitori, ovvero l'assenza di stato.

Le soluzioni seguenti vengono usate per gestire i dati persistenti nelle applicazioni di Docker:

-   [I volumi di dati](https://docs.docker.com/engine/tutorials/dockervolumes/) montati nell'host.

-   [I contenitori dei volumi di dati](https://docs.docker.com/engine/tutorials/dockervolumes/#creating-and-mounting-a-data-volume-container) che forniscono l'archiviazione condivisa tra contenitori usando un contenitore esterno.

-   [I plug-in di volume](https://docs.docker.com/engine/tutorials/dockervolumes/) che montano i volumi nei servizi remoti, fornendo una persistenza a lungo termine.

-   [Archiviazione di Azure](https://docs.microsoft.com/azure/storage/) che fornisce un'archiviazione geo-distribuibile e una buona soluzione di persistenza a lungo termine per i contenitori.

-   Database relazionali remoti come i [database SQL di Azure](https://azure.microsoft.com/services/sql-database/), database NoSQL come [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) o servizi di cache come [Redis](https://redis.io/).

Le sezioni seguenti forniscono altre informazioni su queste opzioni.

**I volumi di dati** sono directory associate dal sistema operativo host alle directory nei contenitori. Quando il codice nel contenitore accede alla directory, in realtà accede a una directory nel sistema operativo host. Questa directory non è legata alla durata dello specifico contenitore e l'accesso può essere eseguito dal codice in esecuzione direttamente nel sistema operativo host o da un altro contenitore che esegue il mapping della stessa directory host a se stessa. Di conseguenza, i volumi di dati sono progettati per rendere persistenti i dati in modo indipendente dalla durata del contenitore. Se si elimina un contenitore o un'immagine dall'host Docker, i dati persistenti nel volume di dati non vengono eliminati. L'accesso ai dati in un volume può essere eseguito anche dal sistema operativo host.

**I contenitori dei volumi di dati** sono un'evoluzione dei normali volumi di dati. Un contenitore dei volumi di dati è un contenitore semplice che include uno o più volumi di dati. Il contenitore del volume di dati fornisce l'accesso ai contenitori da un punto di montaggio centrale. Questo metodo di accesso ai dati è utile perché estrae il percorso dei dati originali. A parte ciò, il comportamento è simile a quello di un volume di dati normale, quindi i dati vengono mantenuti in questo contenitore dedicato in modo indipendente dalla durata dei contenitori dell'applicazione.

Come illustrato nella figura 4-5, i volumi Docker normali possono essere archiviati fuori dai contenitori stessi, ma all'interno dei limiti fisici del server host o della macchina virtuale. Tuttavia, i contenitori Docker non possono accedere a un volume da un server host o da una macchina virtuale a un'altra. In altre parole, con questi volumi non è possibile gestire i dati condivisi tra contenitori che vengono eseguiti in diversi host Docker

![](./media/image5.png)

**Figura 4-5**. Volumi di dati e origini dati esterne per applicazioni basate su contenitore

Quando i contenitori Docker vengono gestiti da un agente di orchestrazione, i contenitori possono anche "spostarsi" tra gli host, a seconda delle ottimizzazioni eseguite dal cluster. Non è quindi consigliabile usare i volumi di dati per i dati aziendali. Tuttavia, possono essere efficaci quando si lavora con file di traccia, file temporanei o file simili che non influiscono sulla coerenza dei dati aziendali.

**I plug-in di volume** come [Flocker](https://clusterhq.com/flocker/) forniscono l'accesso ai dati in tutti gli host in un cluster. Anche se non tutti i plug-in di volume sono uguali, i plug-in di volume in genere forniscono un'archiviazione affidabile, persistente ed esternalizzata grazie a contenitori non modificabili.

**Gli strumenti per le origini dati remote e la cache**, ad esempio i database SQL di Azure, Azure Cosmos DB o le cache remote come Redis, possono essere usati nelle applicazioni incluse in contenitori allo stesso modo con cui vengono usati durante lo sviluppo senza contenitori. Si tratta di un modo consolidato per archiviare i dati delle applicazioni aziendali.

**Archiviazione di Azure.** I dati aziendali in genere devono essere inseriti in risorse o database esterni, ad esempio Archiviazione di Azure. Archiviazione di Azure fornisce essenzialmente i servizi seguenti nel cloud:

-   L'archiviazione BLOB archivia i dati oggetto non strutturati. Un BLOB può essere costituito da qualsiasi tipo di dati di testo o binari, ad esempio documenti o file multimediali (file di immagini, audio e video). L'archiviazione BLOB viene chiamata anche archiviazione di oggetti.

-   L'archiviazione dei file offre un'archiviazione condivisa per le applicazioni legacy usando il protocollo SMB standard. Le macchine virtuali di Azure e i servizi cloud possono condividere i dati dei file nei componenti delle applicazioni tramite condivisioni montate. Le applicazioni locali possono accedere ai dati dei file in una condivisione tramite l'API REST del Servizio file.

-   L'archiviazione tabelle archivia i set di dati strutturati. L'archiviazione tabelle è un archivio dati chiave-attributo NoSQL, che consente di sviluppare e di accedere rapidamente a quantità elevate di dati.

**Database relazionali e database NoSQL.** Esistono numerose opzioni per i database esterni, dai database relazionali come SQL Server, PostgreSQL, Oracle o NoSQL ai database NoSQL come Azure Cosmos DB, MongoDB e così via. Questi database non verranno spiegati in questa guida perché riguardano un argomento completamente diverso.


>[!div class="step-by-step"]
[Indietro] (containerize-monolithic-applications.md) [Avanti] (service-oriented-architecture.md)
