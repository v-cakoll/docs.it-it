---
title: Stato e dati nelle applicazioni di Docker
description: Scopri l'opzione disponibile per salvare lo stato nelle applicazioni in contenitori.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 30dde3ce44aa61fff3fad1841ae4a8b941573877
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795446"
---
# <a name="state-and-data-in-docker-applications"></a>Stato e dati nelle applicazioni di Docker

Nella maggior parte dei casi è possibile considerare un contenitore come un'istanza di un processo. Un processo non mantiene uno stato persistente. Anche se un contenitore può scrivere la risorsa di archiviazione locale, presupponendo che un'istanza resti disponibile all'infinito è come presupporre che un'unica posizione in memoria sia durevole. Immagini del contenitore, come i processi, devono essere presupposto di installare più istanze e che vengano infine terminate essi; Se vengono gestite con un agente di orchestrazione del contenitore, si deve presupporre di poter essere spostate da un nodo o della macchina virtuale a un altro.

Le soluzioni seguenti vengono usate per gestire i dati persistenti nelle applicazioni di Docker:

Dall'host Docker, come [volumi Docker](https://docs.docker.com/engine/admin/volumes/):

- I **volumi** vengono archiviati in un'area del file system dell'host gestito da Docker.

- **Associare i punti di montaggio** può eseguire il mapping a qualsiasi cartella nel file System host, in modo che l'accesso non può essere controllato da un processo di Docker e può comportare un rischio di sicurezza come un contenitore è stato possibile accedere alle cartelle riservate del sistema operativo.

- I **montaggi di tipo tmpfs** sono come cartelle virtuali presenti solo nella memoria dell'host e non vengono mai scritte nel file system.

Dall'archiviazione remota:

- [Archiviazione di Azure](https://azure.microsoft.com/documentation/services/storage/) fornisce l'archiviazione geo-distribuibile, che fornisce un'ottima soluzione di persistenza a lungo termine per i contenitori.

- Database relazionali remoti come [Database SQL di Azure](https://azure.microsoft.com/services/sql-database/), i database NoSQL come [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction), o servizi, ad esempio di cache [Redis](https://redis.io/).

Dal contenitore Docker:

- Docker offre una funzionalità denominata *sovrimpressione di file system*. Questa funzione implementa un'attività di copia su scrittura che archivia le informazioni aggiornate nel file System radice del contenitore. Tali informazioni "imposta il layout nella parte superiore del" l'immagine originale su cui si basa il contenitore. Se il contenitore viene eliminato dal sistema, le modifiche andranno perdute. Pertanto, sebbene sia possibile salvare lo stato di un contenitore nell'archiviazione locale, la progettazione di un sistema basato su questa funzionalità genererebbe un conflitto con il presupposto di progettazione di contenitori, che per impostazione predefinita è senza stato.

- Tuttavia, i volumi Docker è ora il modo migliore per gestire i dati locali in Docker. Se sono necessarie altre informazioni sull'archiviazione in contenitori, controllare [i driver di archiviazione di Docker](https://docs.docker.com/engine/userguide/storagedriver/) e [sulle immagini, contenitori e i driver di archiviazione](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).

Nelle sezioni che seguono vengono fornite ulteriori informazioni su queste opzioni.

I **volumi di dati** sono directory associate dal sistema operativo host alle directory nei contenitori. Quando il codice nel contenitore accede alla directory, in realtà accede a una directory nel sistema operativo host. Questa directory non è associata alla durata del contenitore stesso, viene gestita da Docker e isolata dalla funzionalità principale del computer host. Di conseguenza, i volumi di dati sono progettati per rendere persistenti i dati in modo indipendente dalla durata del contenitore. Se si elimina un contenitore o un'immagine dall'host Docker, i dati persistenti nel volume di dati non vengono eliminati.

I volumi possono essere denominati o possono essere anonimi (opzione predefinita). I volumi denominati rappresentano l'evoluzione dei **contenitori dei volumi di dati** e semplificano la condivisione dei dati tra contenitori. Volumi supportano anche i driver di volume che consentono di archiviare i dati in host remoti, tra le altre opzioni.

**Associare i punti di montaggio** sono disponibili da molto tempo e consentire il mapping di qualsiasi cartella da un punto di montaggio in un contenitore. I montaggi di associazione presentano più limitazioni rispetto ai volumi e generano alcuni problemi importanti in termini di sicurezza. È quindi consigliabile usare i volumi.

**`tmpfs` Consente di montare** sono cartelle virtuali attivi solo in memoria dell'host e non vengono mai scritti nel file System. Sono sicuri e veloci, consumano la memoria e sono applicabili solo a dati non permanenti.

Come illustrato nella figura 4-5, i volumi Docker normali possono essere archiviati fuori dai contenitori stessi, ma all'interno dei limiti fisici del server host o della macchina virtuale. Tuttavia, i contenitori Docker non possono accedere a un volume da un server host o da una macchina virtuale a un'altra. In altre parole, con questi volumi non è possibile gestire i dati condivisi tra contenitori che vengono eseguiti in host Docker diversi. A tale scopo, si può tuttavia usare un driver del volume che supporta gli host remoti.

![I volumi possono essere condivisi tra contenitori, ma solo nello stesso host, a meno che non si usi un driver remoto che supporta host remoti. ](./media/image5.png)

**Figura 4-5**. Volumi di dati e origini dati esterne per applicazioni basate su contenitore

Quando i contenitori Docker vengono gestiti da un agente di orchestrazione, i contenitori possono anche "spostarsi" tra gli host, a seconda delle ottimizzazioni eseguite dal cluster. Non è quindi consigliabile usare i volumi di dati per i dati aziendali. Ma sono un meccanismo appropriato per lavorare con file di traccia, file temporali, o simile, che non influirà sulla coerenza dei dati aziendali.

**Gli strumenti per le origini dati remote e la cache**, ad esempio i database SQL di Azure, Azure Cosmos DB o le cache remote come Redis, possono essere usati nelle applicazioni incluse in contenitori allo stesso modo con cui vengono usati durante lo sviluppo senza contenitori. Si tratta di un modo consolidato per archiviare i dati delle applicazioni aziendali.

**Archiviazione di Azure.** I dati di business devono in genere si trovino in risorse esterne o i database, come archiviazione di Azure. Archiviazione di Azure offre i servizi seguenti nel cloud:

- L'archiviazione BLOB archivia i dati oggetto non strutturati. Un BLOB può essere costituito da qualsiasi tipo di dati di testo o binari, ad esempio documenti o file multimediali (file di immagini, audio e video). L'archiviazione BLOB viene chiamata anche archiviazione di oggetti.

- Archiviazione file offre un'archiviazione condivisa per le applicazioni che usano il protocollo SMB standard. Le macchine virtuali di Azure e i servizi cloud possono condividere i dati dei file nei componenti delle applicazioni tramite condivisioni montate. Applicazioni locali possono accedere i dati dei file in una condivisione tramite l'API REST di servizi File.

- L'archiviazione tabelle archivia i set di dati strutturati. L'archiviazione tabelle è un archivio dati chiave-attributo NoSQL, che consente di sviluppare e di accedere rapidamente a quantità elevate di dati.

**Database relazionali e database NoSQL.** Esistono numerose opzioni per i database esterni, dai database relazionali come SQL Server, PostgreSQL, Oracle o NoSQL ai database NoSQL come Azure Cosmos DB, MongoDB e così via. Questi database non verranno spiegati nell'ambito di questa guida perché sono completamente un altro argomento.

>[!div class="step-by-step"]
>[Precedente](monolithic-applications.md)
>[Successivo](soa-applications.md)
