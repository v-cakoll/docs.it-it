---
title: Archiviazione dati in Azure
description: Architettura di app .NET cloud native per Azure | Archiviazione dati in Azure
ms.date: 06/30/2019
ms.openlocfilehash: 5ba05f53faf65334f6269af8ae2c54d81e6b0779
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337465"
---
# <a name="data-storage-in-azure"></a>Archiviazione dati in Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Come abbiamo visto in questo libro, il cloud sta cambiando il modo in cui le applicazioni vengono progettate, distribuite e gestite. Quando si passa al cloud, una domanda critica è come spostare i dati? Fortunatamente, il cloud di Azure offre numerose opzioni.

È sufficiente eseguire il provisioning di una macchina virtuale di Azure e installare il database desiderato. Questa operazione è nota come infrastruttura distribuita [come servizio (IaaS)](https://www.techopedia.com/definition/141/infrastructure-as-a-service-iaas). Questo approccio semplifica lo spostamento di un database locale nel cloud, così come sono, ma sposta il carico di gestione della macchina virtuale e del database.

Un [database come servizio completamente gestito (DBaaS)](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/) è invece un'opzione migliore. Sono disponibili molte funzionalità predefinite mentre l'hosting, la manutenzione e la gestione delle licenze sono gestite da Microsoft. Azure offre diversi tipi di opzioni di archiviazione dei dati completamente gestite, ognuna con vantaggi specifici. Supportano la capacità just-in-time e un modello con pagamento in base al consumo.

Verranno ora esaminate le opzioni di DBaaS disponibili in Azure. Scoprirai in che modo Microsoft continuerà a mantenere Azure una "piattaforma aperta", offrendo il supporto gestito per molti database relazionali e NoSQL open source e contribuendo ai contributi chiave alle varie fondazioni open source come membri attivi.

## <a name="azure-sql-database"></a>Database SQL di Azure

Il [database SQL di Azure](https://docs.microsoft.com/azure/sql-database/) è un database relazionale come servizio (DBaaS) ricco di funzionalità per utilizzo generico basato sul motore di database Microsoft SQL Server. È completamente gestito da Microsoft ed è un database cloud ad alte prestazioni, affidabile e sicuro. Il servizio condivide molte delle funzionalità disponibili nella versione locale di SQL Server.

È possibile effettuare il provisioning di un server e di un database SQL in pochi minuti. Quando la domanda per l'applicazione cresce da pochi clienti a milioni, il database SQL di Azure viene ridimensionato in tempo reale con tempi di inattività minimi. È possibile aggiungere o rimuovere in modo dinamico le risorse, tra cui la potenza della CPU, la memoria, la velocità effettiva di i/o e l'archiviazione allocata ai database.

La figura 5-12 illustra le opzioni di distribuzione per il database SQL di Azure.

![Opzioni di distribuzione SQL di Azure](./media/azure-sql-database-deployment-options.png)

**Figura 5-12**. Opzioni di distribuzione SQL di Azure

Si notino le alternative nella figura precedente quando si distribuisce un database SQL:

- Un [database singolo](https://docs.microsoft.com/azure/sql-database/sql-database-single-database) con il proprio set di risorse gestite da un [server di database SQL](https://docs.microsoft.com/azure/sql-database/sql-database-servers). Un database singolo è simile a un [database indipendente](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) in una distribuzione SQL Server locale.

- Un [pool elastico](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool) in cui una raccolta di database SQL condivide un singolo server di database SQL a un prezzo fisso. I database singoli possono essere spostati all'interno e all'esterno di un pool elastico in base alle esigenze per ottimizzare le prestazioni dei prezzi per un gruppo di database.

- Un [istanza gestita](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) in cui è una raccolta di database di sistema e utente che garantisce una compatibilità quasi al 100% con una SQL Server locale. Questa opzione supporta database di dimensioni maggiori, fino a 35 TB e viene posizionata in una [rete virtuale di Azure](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) per un migliore isolamento.

Il database SQL di Azure è un [motore di database di piattaforma distribuita come servizio (PaaS)](https://docs.microsoft.com/azure/sql-database/sql-database-paas) completamente gestito che gestisce l'aggiornamento, l'applicazione di patch, i backup e il monitoraggio senza coinvolgimento dell'utente. Esegue sempre la versione stabile più recente del SQL Server motore di database e del sistema operativo con patch e garantisce la disponibilità del 99,99%. Una funzionalità di [replica geografica attiva](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication)consente di creare database secondari leggibili nello stesso data center di Azure o in un'altra. In caso di errore, è possibile avviare un failover su un database secondario. A questo punto, gli altri database secondari vengono collegati automaticamente al nuovo database primario. Fino a quattro repliche secondarie sono supportate nella stessa area o in aree diverse e tali database secondari possono essere usati anche per le query di accesso in sola lettura.

Il database SQL di Azure include funzionalità [di monitoraggio e ottimizzazione intelligenti predefinite](https://docs.microsoft.com/azure/sql-database/sql-database-monitoring-tuning-index) che consentono di ottimizzare le prestazioni e ridurre i costi operativi. Ad esempio, la funzionalità di [ottimizzazione automatica](https://docs.microsoft.com/azure/sql-database/sql-database-automatic-tuning) fornisce l'ottimizzazione delle prestazioni continua basata su intelligenza artificiale e machine learning. Il servizio apprende dai carichi di lavoro in esecuzione e può applicare le indicazioni di ottimizzazione. Più a lungo viene eseguito un database SQL di Azure con l'ottimizzazione automatica abilitata, migliore sarà il rendimento.

Il [database SQL di Azure senza server](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) (disponibile per l'anteprima al momento della stesura di questo libro) è un livello di calcolo per i database singoli che si ridimensiona automaticamente in base alle richieste di carico di lavoro e fattura per la quantità di calcolo usata al secondo. Il livello di calcolo senza server inoltre sospende automaticamente i database durante i periodi di inattività, in modo che vengano addebitati solo i costi di archiviazione. Riprende automaticamente quando l'attività restituisce.

Infine, è disponibile il nuovo piano tariffario per il [database SQL di Azure](https://azure.microsoft.com/services/sql-database/) . È basato su un'architettura di archiviazione altamente scalabile e consente di aumentare le dimensioni del database in base alle esigenze, eliminando la necessità di eseguire il pre-provisioning delle risorse di archiviazione. È possibile ridimensionare le risorse di calcolo e archiviazione in modo indipendente, offrendo la flessibilità necessaria per ottimizzare le prestazioni per ogni carico di lavoro. L'iperscalabilità di database SQL di Azure è ottimizzata per l'elaborazione [OLTP](https://en.wikipedia.org/wiki/Online_transaction_processing) e carichi di lavoro analitici con velocità effettiva elevata con archiviazione fino a 100 TB.  Con i carichi di lavoro con utilizzo intensivo di lettura, l'iperscalabilità offre una rapida scalabilità orizzontale tramite il provisioning di altre repliche di lettura in base alle esigenze per l'offload dei carichi di lavoro

Oltre allo stack di Microsoft SQL Server tradizionale, Azure offre anche versioni gestite di diversi database open source diffusi.

## <a name="azure-database-for-mysql"></a>Database di Azure per MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) è un [open-source](https://en.wikipedia.org/wiki/Open-source_software) [database relazionale](https://en.wikipedia.org/wiki/Relational_database_management_system). Si tratta di un componente nello [stack del software Lamp](https://en.wikipedia.org/wiki/LAMP_(software_bundle)) e usato da molte organizzazioni di grandi dimensioni, tra cui Facebook, Twitter e YouTube. La Community Edition è disponibile gratuitamente e l'edizione Enterprise richiede l'acquisto di una licenza. Originariamente creato in 1995, il prodotto è stato acquistato da Sun Microsystems nel 2008, che è stato acquisito da Oracle in 2010.

[Database di Azure per MySQL](https://azure.microsoft.com/services/mysql/) è un servizio di database relazionale completamente gestito e pronto per l'azienda basato sul motore del server MySQL open source. Implementando MySQL Community Edition sono incluse le funzionalità di PaaS seguenti senza costi aggiuntivi:

- [Disponibilità elevata](https://docs.microsoft.com/azure/mysql/concepts-high-availability)incorporata.

- Prestazioni prevedibili, con prezzi inclusivi con [pagamento in base al](https://docs.microsoft.com/azure/mysql/concepts-pricing-tiers)consumo.

- [Ridimensionare](https://docs.microsoft.com/azure/mysql/concepts-high-availability) in base alle esigenze in pochi secondi.

- Protezione dei dati sensibili inattivi e in movimento.

- [Backup automatici](https://docs.microsoft.com/azure/mysql/concepts-backup) e [ripristino temporizzato](https://docs.microsoft.com/azure/mysql/concepts-backup) per un massimo di 35 giorni.

- Sicurezza e conformità di livello aziendale.

Queste funzionalità predefinite di PaaS sono importanti per le organizzazioni che hanno centinaia di database "tattici" (non strategici) nei propri Data Center, ma non hanno le risorse necessarie per eseguire l'applicazione di patch, il backup, la protezione e il monitoraggio delle prestazioni.

Il [servizio migrazione dei dati di Azure](https://azure.microsoft.com/services/database-migration/) consente inoltre di eseguire la migrazione di dati da più origini di database alle piattaforme dati di Azure con tempi di inattività minimi. Il servizio genera report di valutazione e fornisce indicazioni che consentono di eseguire in modo semplificato le modifiche necessarie per eseguire una migrazione, sia di piccole o grandi dimensioni.

Il [server MySQL di Azure](https://docs.microsoft.com/azure/mysql/concepts-servers) gestito è il punto centrale amministrativo per il servizio. Si tratta dello stesso motore di MySQL server usato per le distribuzioni locali. Con esso, è possibile creare un singolo database per ogni server per utilizzare tutte le risorse o creare più database per server per condividere le risorse. Il team può continuare a sviluppare applicazioni con strumenti e piattaforme open source di propria scelta senza dover apprendere nuove competenze o gestire macchine virtuali e infrastrutture.

## <a name="azure-database-for-mariadb"></a>Database di Azure per MariaDB

[MariaDB](https://mariadb.com/) Server è un altro noto server di database open source. È stato creato come fork di MySQL dagli sviluppatori originali di MySQL nel momento in cui Oracle ha acquistato Sun Microsystems che possedeva MySQL. Lo scopo era quello di garantire che MariaDB fosse rimasto open source.

Poiché MariaDB è un [fork di MySQL](https://blog.panoply.io/a-comparative-vmariadb-vs-mysql), le definizioni di dati e tabelle sono compatibili e i protocolli, le strutture e le API client sono compatibili. I connettori dati MySQL funzioneranno senza modifiche MariaDB.

MariaDB ha un forte seguito e viene usato da molte grandi aziende. Sebbene Oracle continui a mantenere, migliorare e supportare MySQL, MariaDB è gestito da MariaDB Foundation che consente contributi pubblici al prodotto e alla documentazione.

[Database di Azure per MariaDB](https://azure.microsoft.com/services/mariadb/) è un database come servizio completamente gestito nel cloud di Azure. È basato sul motore del server [MariaDB Community Edition](https://mariadb.org/download/) . Consente di gestire carichi di lavoro cruciali con prestazioni prevedibili e scalabilità dinamica. Analogamente alle altre piattaforme di database di Azure, include molte funzionalità di piattaforma distribuita come servizio senza costi aggiuntivi:

- [Disponibilità elevata](https://docs.microsoft.com/azure/mariadb/concepts-high-availability)incorporata.

- Prestazioni prevedibili, con prezzi inclusivi con [pagamento in base al](https://docs.microsoft.com/azure/mariadb/concepts-pricing-tiers)consumo.

- [Ridimensionamento](https://docs.microsoft.com/azure/mariadb/concepts-high-availability) in base alle esigenze in pochi secondi.

- Protezione protetta dei dati sensibili inattivi e in movimento.

- [Backup automatici](https://docs.microsoft.com/azure/mariadb/concepts-backup) e [ripristino temporizzato](https://docs.microsoft.com/azure/mariadb/concepts-backup) per un massimo di 35 giorni.

- Sicurezza e conformità di livello aziendale.

## <a name="azure-database-for-postgresql"></a>Database di Azure per PostgreSQL

[PostgreSQL](https://www.postgresql.org/) è un altro noto database relazionale open source con oltre 30 anni di sviluppo attivo. Si tratta di un sistema di gestione di database relazionale a oggetti e per utilizzo generico. Le licenze sono considerate "liberali" e il prodotto è gratuito per l'uso, la modifica e la distribuzione in qualsiasi forma. Molte grandi aziende, tra cui Apple, Red Hat e Fujitsu, hanno creato prodotti con PostgreSQL.

[Database di Azure per PostgreSQL](https://azure.microsoft.com/services/postgresql/) è un servizio di database relazionale completamente gestito, basato sul motore di database Postgres open source. Consente di gestire carichi di lavoro cruciali con prestazioni prevedibili, sicurezza, disponibilità elevata e scalabilità dinamica. Supporta diversi Framework e linguaggi open source, tra cui C++Java, Python, node, C\#e php. Consente la [migrazione](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) dei database PostgreSQL tramite un'interfaccia della riga di comando o il [servizio migrazione dati di Azure](https://azure.microsoft.com/services/database-migration/).

Il servizio include [Intelligence incorporata](https://docs.microsoft.com/azure/postgresql/concepts-monitoring) che studia i modelli di database esclusivi e fornisce consigli personalizzati e informazioni dettagliate per ottimizzare le prestazioni del database PostgreSQL. [Advanced Threat Protection](https://docs.microsoft.com/azure/postgresql/concepts-data-access-and-security-threat-protection) monitora il database in base all'orologio e rileva le attività potenzialmente dannose, avvisando il rilevamento in modo da poter intervenire immediatamente.

Database di Azure per PostgreSQL è disponibile come due opzioni di distribuzione: server singolo e iperscalabilità (CITUS), disponibile per l'anteprima al momento della stesura di questo libro.

- L'opzione di distribuzione a [server singolo](https://docs.microsoft.com/azure/postgresql/concepts-servers) è un punto amministrativo centrale per più database. Si tratta dello stesso motore del server PostgreSQL disponibile per le distribuzioni locali. Con esso, è possibile creare un singolo database per ogni server per utilizzare tutte le risorse o creare più database per condividere le risorse. I prezzi sono strutturati per server in base ai core e all'archiviazione.

- L' [opzione iperscale (CITUS)](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) è basata sulla tecnologia [CITUS data](https://www.citusdata.com/) . Consente la scalabilità a prestazioni elevate con scalabilità orizzontale di un database singolo in centinaia di nodi per offrire prestazioni e scalabilità incredibilmente veloci. Questa opzione consente al motore di adattare più dati in memoria, parallelizzare le query tra centinaia di nodi e indicizzare i dati più velocemente. La funzionalità iperscalabile è compatibile con le innovazioni, le versioni e gli strumenti più recenti per PostgreSQL, in modo da poter sfruttare le competenze esistenti di PostgreSQL.

## <a name="cosmos-db"></a>Cosmos DB

Azure Cosmos DB è un servizio di database NoSQL completamente gestito e distribuito a livello globale, progettato per fornire bassa latenza, scalabilità elastica, coerenza dei dati gestiti e disponibilità elevata. In breve, se l'applicazione richiede tempi di risposta rapidi in qualsiasi parte del mondo, se è necessario che sia sempre online e necessiti di scalabilità illimitata e elastica della velocità effettiva e dello spazio di archiviazione, Cosmos DB rappresenta la scelta ottimale. La figura 5-13 illustra una panoramica di alto livello di Cosmos DB.

![Panoramica di Cosmos DB](./media/cosmos-db-overview.png)

**Figura 5-13**: panoramica di Cosmos DB

Si noti nella figura 5-13 come Cosmos DB è un servizio di database solido e altamente versatile con molte funzionalità predefinite native del cloud. In questa sezione verranno esaminati in modo più approfondito.

### <a name="global-support"></a>Supporto globale

Puoi distribuire a livello globale i database Cosmos in tutte le aree di Azure in tutto il mondo, inserendo i dati vicino agli utenti, migliorando il tempo di risposta e riducendo la latenza. È possibile aggiungere o rimuovere un database da un'area senza sospendere o ridistribuire l'applicazione. In background, Cosmos DB replica in modo trasparente i dati in tutte le aree configurate.

Cosmos DB supporta il clustering [attivo/attivo](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) a livello globale, consentendo di configurare una o tutte le aree del database per supportare le operazioni di scrittura e lettura.

La funzionalità protocollo [multimaster](https://docs.microsoft.com/azure/cosmos-db/how-to-multi-master) di Cosmos DB offre le funzionalità seguenti:

- Scalabilità di lettura e scrittura elastica illimitata.

- Disponibilità in lettura e scrittura pari al 99,999% in tutto il mondo.

- Letture e scritture gestite in meno di 10 millisecondi nel 99% dei casi.

Internamente, Cosmos DB gestisce la replica dei dati tra aree con garanzie a livello di coerenza e contratti di servizio con supporto finanziario.

Con le Cosmos DB [API](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)multihosting, l'applicazione può essere automaticamente a conoscenza dell'area di Azure più vicina e inviare richieste al servizio. L'area più vicina viene identificata da Cosmos DB senza modifiche alla configurazione. Se un'area non è più disponibile, Cosmos DB supporta il failover automatico e la funzionalità di multihosting instraderà automaticamente la richiesta all'area disponibile successiva più vicina.

### <a name="multi-model-support"></a>Supporto per più modelli

Cosmos DB è una *piattaforma dati multimodello* che consente di interagire con i dati usando diversi modelli NoSQL supportati, tra cui documenti, coppie chiave-valore, colonne a colonna ampia e rappresentazioni di grafici. Internamente, i dati vengono archiviati in un formato [struct](https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/using-structs) semplice costituito da tipi di dati primitivi, tra cui stringhe, valori booleani e numeri. Per ogni richiesta, il motore di database converte i dati nella rappresentazione del modello selezionata. È possibile scegliere tra un'API proprietaria Cosmos DB basata su SQL o una qualsiasi delle [API di compatibilità](https://www.wikiwand.com/en/Cosmos_DB) illustrate nella figura 5-14.

![Provider di Cosmos DB](./media/cosmos-db-providers.png)

**Figura 5-14**: provider di Cosmos DB

Si noti nella figura 5-14 come Cosmos DB supporta l' [archiviazione tabelle](https://azure.microsoft.com/services/storage/tables/). Sia Cosmos DB che [archiviazione tabelle di Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) condividono lo stesso modello di tabella sottostante ed espongono molte delle stesse operazioni di tabella. Tuttavia, il [Cosmos DB API tabella](https://docs.microsoft.com/azure/cosmos-db/table-introduction) fornisce molti miglioramenti Premium non disponibili nell'API di archiviazione di Azure. Queste funzionalità sono contrapposte alla figura 5-15.

![API Tabella di Azure](./media/azure-table-api.png)

**Figura 5-15**: API tabella di Azure

Le applicazioni scritte per l'archiviazione tabelle di Azure possono eseguire la migrazione a Azure Cosmos DB usando il API Tabella senza modifiche al codice.

Negli scenari di applicazioni [Brownfield](https://en.wikipedia.org/wiki/Brownfield_(software_development)) , i team di sviluppo possono migrare i database Mongo, Gremlin o Cassandra esistenti in Cosmos DB con modifiche minime al codice dell'applicazione o dei dati esistenti. Per gli scenari [Greenfield](https://en.wikipedia.org/wiki/Greenfield_project) , i team di sviluppo possono scegliere il modello di dati che meglio soddisfa i requisiti e le preferenze, incluse le opzioni open source completamente supportate per le piattaforme MongoDB, Cassandra e Gremlin.

### <a name="consistency-models"></a>Modelli di coerenza

In precedenza nella sezione *relazionale rispetto a NoSQL* , abbiamo discusso l'oggetto della *coerenza dei dati*, che è un termine che fa riferimento all'integrità dei dati. I database distribuiti che si basano sulla replica per la disponibilità elevata, la bassa latenza o entrambi devono avere un compromesso fondamentale tra coerenza di lettura, disponibilità e latenza.

La maggior parte dei database distribuiti consente agli sviluppatori di scegliere tra due modelli di coerenza: [coerenza](https://en.wikipedia.org/wiki/Strong_consistency) assoluta e [coerenza finale](https://en.wikipedia.org/wiki/Eventual_consistency). La *coerenza* assoluta è lo standard Gold di programmabilità dei dati. Garantisce che il risultato di una query restituirà sempre i dati più recenti, anche se il sistema deve subire una latenza in attesa che un aggiornamento venga replicato in tutte le copie del database. D'altra parte, un sistema configurato per la *coerenza finale* restituirà immediatamente i dati, anche se tali dati non sono la copia più recente. Questa opzione consente una maggiore disponibilità, una maggiore scalabilità e prestazioni migliorate.

Azure Cosmos DB offre uno spettro di [cinque modelli di coerenza ben definiti](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) illustrati nella figura 5-16. Queste opzioni consentono di effettuare scelte precise e compromessi granulari rispetto alla disponibilità e alle prestazioni in base alle esigenze dell'applicazione. Questi modelli sono ben definiti, intuitivi e supportati da contratti di servizio.

![Livelli di coerenza Cosmos DB](./media/cosmos-db-consistency-levels.png)

**Figura 5-16**: livelli di coerenza Cosmos DB

### <a name="partitioning"></a>Partizionamento

Azure Cosmos DB usa il [partizionamento](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) automatico per ridimensionare il database per soddisfare le esigenze di prestazioni dell'applicazione.

Per gestire i dati nei dati Cosmos DB, è possibile creare [database, contenitori ed elementi](https://docs.microsoft.com/azure/cosmos-db/databases-containers-items), illustrati nella figura 5-17.

![Entità Cosmos DB](./media/cosmos-db-entities.png)

**Figura 5-17**: gerarchia di entità Cosmos DB

Si noti nella figura 5-17 come iniziare creando un database Cosmos DB all'interno di un account di database. Il database diventa l'unità di gestione per un set di contenitori. Un contenitore è un raggruppamento di elementi indipendente dallo schema che può essere espresso come raccolta, tabella o grafico, in base al provider di API selezionato (descritto nella sezione precedente). Gli elementi sono i dati che si aggiungono al contenitore e sono rappresentati come documenti, righe, nodi o bordi. Per impostazione predefinita, tutti gli elementi aggiunti a un contenitore vengono indicizzati automaticamente senza richiedere la gestione esplicita di indici o schemi.

Per partizionare il contenitore, gli elementi sono divisi in subset distinti denominati [partizioni logiche](https://docs.microsoft.com/azure/cosmos-db/partition-data). Le partizioni logiche vengono create in base al valore di una chiave di partizione associata a ogni elemento in un contenitore. La figura 5-18 Mostra come tutti gli elementi di una partizione logica hanno lo stesso valore della chiave di partizione.

![Cosmos DB meccanismi di partizionamento](./media/cosmos-db-partitioning.png)

**Figura 5-18**: Cosmos DB meccanismi di partizionamento

Si noti nella figura 5-18 in che modo ogni elemento include una chiave di partizione ' City ' o ' Airport '. Questa chiave di partizione determina la partizione logica dell'elemento. Ogni codice della città viene assegnato a una partizione logica nel contenitore sul lato sinistro e a quelli con un codice aeroportuale al contenitore a destra. Combinando il valore della chiave di partizione con un valore ID di un elemento, viene creato l'indice dell'elemento, che identifica in modo univoco l'elemento.

Internamente, Cosmos DB gestisce automaticamente il posizionamento delle [partizioni logiche](https://docs.microsoft.com/azure/cosmos-db/partition-data) nelle [partizioni fisiche](https://docs.microsoft.com/azure/cosmos-db/partition-data) per soddisfare in modo efficiente le esigenze di scalabilità e prestazioni del contenitore. Poiché i requisiti di archiviazione e velocità effettiva di un'applicazione aumentano, Azure Cosmos DB sposta le partizioni logiche per ridistribuire il carico su un numero maggiore di server. Queste operazioni di ridistribuzione sono gestite da Cosmos DB e vengono eseguite senza interruzioni o tempi di inattività.

## <a name="azure-redis-cache"></a>Cache Redis di Azure

I vantaggi della memorizzazione nella cache per migliorare le prestazioni e la scalabilità sono ben noti.

Per un'applicazione nativa del cloud, un percorso comune per aggiungere la memorizzazione nella cache si trova all'interno del gateway API. Il gateway funge da front-end per tutte le richieste in ingresso. Grazie all'aggiunta della memorizzazione nella cache, è possibile aumentare le prestazioni e la velocità di risposta restituendo i dati memorizzati nella cache ed evitando round trip a un database locale o a un servizio downstream. La figura 5-19 illustra un'architettura di memorizzazione nella cache per un'applicazione nativa del cloud.

![Memorizzazione nella cache in un'app nativa del cloud](./media/caching-in-a-cloud-native-app.png)

**Figura 5-19**: memorizzazione nella cache in un'app nativa del cloud

Un modello di memorizzazione nella cache comune è il [modello cache-aside](https://docs.microsoft.com/azure/architecture/patterns/cache-aside). Per una richiesta in ingresso, eseguire prima una query sulla cache per la risposta, illustrata nel passaggio #1 nella figura 5-19. Se viene trovato, i dati vengono restituiti immediatamente. Se i dati non esistono nella cache (noto come [mancato riscontro nella cache](https://www.techopedia.com/definition/6308/cache-miss)), vengono recuperati dal database locale o dal servizio downstream (passaggio #2), scritti nella cache per richieste future (passaggio #3) e restituiti al chiamante. È necessario prestare attenzione per rimuovere periodicamente i dati memorizzati nella cache, in modo che il sistema rimanga coerente e accurato.

Si noti inoltre che nella figura 5-19 come la cache non viene implementata localmente entro i limiti del servizio, ma viene invece utilizzata come servizio di backup basato sul cloud, come illustrato nel capitolo 1.

[Cache Redis di Azure](https://azure.microsoft.com/services/cache/) è un servizio di memorizzazione dei dati e broker di messaggistica. Fornisce l'accesso a dati e velocità effettiva elevata e a bassa latenza per le applicazioni. Questa soluzione è completamente gestita da Microsoft, ospitata in Azure e accessibile a qualsiasi applicazione all'interno o all'esterno di Azure.

Internamente, cache di Azure per Redis è supportata dal [Server Redis](https://redis.io/) open source e supporta in modo nativo strutture di dati come [stringhe](https://redis.io/topics/data-types#strings), [hash](https://redis.io/topics/data-types#hashes), [elenchi](https://redis.io/topics/data-types#sets), [set](https://redis.io/topics/data-types#sets)e [set ordinati](https://redis.io/topics/data-types#sorted-sets). Se l'applicazione usa Redis, funzionerà così com'è con cache di Azure per Redis.

Cache di Azure per Redis può essere usato anche come cache di dati in memoria, database non relazionale distribuito e broker di messaggi. È disponibile in tre diversi piani tariffari. Il livello Premium offre numerose funzionalità di livello aziendale, come il clustering, la persistenza dei dati, la replica geografica e la sicurezza e l'isolamento della rete virtuale.

>[!div class="step-by-step"]
>[Precedente](data-patterns.md)
>[Successivo](resiliency.md)
