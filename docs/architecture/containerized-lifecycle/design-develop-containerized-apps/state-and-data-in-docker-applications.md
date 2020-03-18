---
title: Stato e dati nelle applicazioni di Docker
description: Informazioni sull'opzione disponibile per salvare lo stato nelle applicazioni in contenitori.
ms.date: 02/15/2019
ms.openlocfilehash: b2368efb0eff2bdce48b77b2addcc4de89822c74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394631"
---
# <a name="state-and-data-in-docker-applications"></a>Stato e dati nelle applicazioni di Docker

Nella maggior parte dei casi è possibile considerare un contenitore come un'istanza di un processo. Un processo non mantiene uno stato persistente. Anche se un contenitore può scrivere nella propria archiviazione locale, presupporre che un'istanza resti disponibile all'infinito sarebbe come presupporre che una singola posizione in memoria sia durevole. Si deve presupporre che le immagini del contenitore, come i processi, abbiano più istanze e che queste vengano infine terminate. Se vengono gestite con un agente di orchestrazione dei contenitori, dovrebbero poter essere spostate da un nodo o da una macchina virtuale a un'altra.

Le soluzioni seguenti vengono usate per gestire i dati persistenti nelle applicazioni di Docker:

Dall'host Docker, come [volumi Docker](https://docs.docker.com/engine/admin/volumes/):

- I **volumi** vengono archiviati in un'area del file system dell'host gestito da Docker.

- I **montaggi di associazione** possono eseguire il mapping a qualsiasi cartella nel file system dell'host. Non è pertanto possibile controllare l'accesso dal processo Docker, aumentando così il rischio per la sicurezza, dal momento che un contenitore potrebbe accedere alle cartelle sensibili del sistema operativo.

- I **montaggi di tipo tmpfs** sono come cartelle virtuali presenti solo nella memoria dell'host e non vengono mai scritte nel file system.

Dall'archiviazione remota:

- [Archiviazione di Azure](https://azure.microsoft.com/documentation/services/storage/) offre un'archiviazione geo-distribuibile e una buona soluzione di persistenza a lungo termine per i contenitori.

- Database relazionali remoti come il [database SQL di Azure](https://azure.microsoft.com/services/sql-database/), i database NoSQL come [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) o i servizi di cache come [Redis](https://redis.io/).

Dal contenitore Docker:

- Docker offre una funzionalità denominata *sovrimpressione di file system*. Questa funzionalità implementa un'operazione di copia su scrittura che archivia le informazioni aggiornate nel file system radice del contenitore. Tali informazioni vengono aggiunte all'immagine originale su cui si basa il contenitore. Se il contenitore viene eliminato dal sistema, le modifiche andranno perdute. Quindi, anche se è possibile salvare lo stato di un contenitore all'interno dell'archiviazione locale, progettare un sistema basato su questa funzionalità genererebbe un conflitto con una delle impostazioni predefinite della progettazione di contenitori, ovvero l'assenza di stato.

- Tuttavia, i volumi Docker rappresentano ora il modo migliore per gestire i dati locali in Docker. Per altre informazioni sull'archiviazione nei contenitori, vedere [Docker storage drivers](https://docs.docker.com/engine/userguide/storagedriver/) (Driver di archiviazione Docker) e [About storage drivers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/) (Informazioni sui driver di archiviazione).

Di seguito viene offerta una descrizione più dettagliata di queste opzioni.

I **volumi di dati** sono directory associate dal sistema operativo host alle directory nei contenitori. Quando il codice nel contenitore accede alla directory, in realtà accede a una directory nel sistema operativo host. Questa directory non è associata alla durata del contenitore stesso, viene gestita da Docker e isolata dalla funzionalità principale del computer host. Di conseguenza, i volumi di dati sono progettati per rendere persistenti i dati in modo indipendente dalla durata del contenitore. Se si elimina un contenitore o un'immagine dall'host Docker, i dati persistenti nel volume di dati non vengono eliminati.

I volumi possono essere denominati o possono essere anonimi (opzione predefinita). I volumi denominati rappresentano l'evoluzione dei **contenitori dei volumi di dati** e semplificano la condivisione dei dati tra contenitori. I volumi supportano anche i driver di volume che consentono, tra le altre opzioni, di archiviare i dati in host remoti.

I **montaggi di associazione** sono disponibili da molto tempo e consentono il mapping di qualsiasi cartella a un punto di montaggio in un contenitore. I montaggi di associazione presentano più limitazioni rispetto ai volumi e generano alcuni problemi importanti in termini di sicurezza. È quindi consigliabile usare i volumi.

le cavalcature sono cartelle virtuali che risiedono solo nella memoria dell'host e non vengono mai scritte nel file system. ** `tmpfs` ** Sono sicuri e veloci, consumano la memoria e sono applicabili solo a dati non permanenti.

Come illustrato nella figura 4-5, i volumi Docker normali possono essere archiviati fuori dai contenitori stessi, ma all'interno dei limiti fisici del server host o della macchina virtuale. Tuttavia, i contenitori Docker non possono accedere a un volume da un server host o da una macchina virtuale a un'altra. In altre parole, con questi volumi non è possibile gestire i dati condivisi tra contenitori che vengono eseguiti in host Docker diversi. A tale scopo, si può tuttavia usare un driver del volume che supporta gli host remoti.

![Diagramma che mostra i volumi Docker archiviati all'esterno dei contenitori.](./media/state-and-data-in-docker-applications/container-based-application-external-data-sources.png)

**Figura 4-5**. Volumi di dati e origini dati esterne per applicazioni basate su contenitore

Quando i contenitori Docker vengono gestiti da un agente di orchestrazione, i contenitori possono anche "spostarsi" tra gli host, a seconda delle ottimizzazioni eseguite dal cluster. Non è quindi consigliabile usare i volumi di dati per i dati aziendali. Tuttavia, possono essere efficaci quando si lavora con file di traccia, file temporanei o file simili che non influiscono sulla coerenza dei dati aziendali.

**Gli strumenti per le origini dati remote e la cache**, ad esempio i database SQL di Azure, Azure Cosmos DB o le cache remote come Redis, possono essere usati nelle applicazioni incluse in contenitori allo stesso modo con cui vengono usati durante lo sviluppo senza contenitori. Si tratta di un modo consolidato per archiviare i dati delle applicazioni aziendali.

**Archiviazione di Azure.Azure Storage.** I dati aziendali in genere devono essere inseriti in risorse o database esterni, ad esempio Archiviazione di Azure. Archiviazione di Azure offre i servizi seguenti nel cloud:

- L'archiviazione BLOB archivia i dati oggetto non strutturati. Un BLOB può essere costituito da qualsiasi tipo di dati di testo o binari, ad esempio documenti o file multimediali (file di immagini, audio e video). L'archivio BLOB è anche denominato archivio di oggetti.

- L'archiviazione file offre risorse di archiviazione condivise per le applicazioni legacy con il protocollo SMB standard. Le macchine virtuali di Azure e i servizi cloud possono condividere i dati dei file nei componenti delle applicazioni tramite condivisioni montate. Le applicazioni locali possono accedere ai dati dei file in una condivisione tramite l'API REST del servizio file.

- Nell'archivio tabelle sono archiviati set di dati strutturati. L'archiviazione tabelle è un archivio dati chiave-attributo NoSQL, che consente di sviluppare e di accedere rapidamente a quantità elevate di dati.

**Database relazionali e database NoSQL.** Esistono molte opzioni per i database esterni, da database relazionali come SQL Server, PostgreSQL, Oracle o NoSQL database come Azure Cosmos DB, MongoDB e così via. Questi database non verranno spiegati come parte di questa guida poiché sono un argomento completamente diverso.

>[!div class="step-by-step"]
>[Successivo](monolithic-applications.md)
>[precedente](soa-applications.md)
