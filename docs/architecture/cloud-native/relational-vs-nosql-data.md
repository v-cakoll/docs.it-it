---
title: Modelli di data mining relazionali Dati NoSQL
description: Informazioni sui dati relazionali e NoSQL nelle applicazioni native del cloud
author: robvet
ms.date: 05/17/2020
ms.openlocfilehash: cc47faa4fcd4468de9ddc468e488297db4289ff5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613785"
---
# <a name="relational-vs-nosql-data"></a>Modelli di data mining relazionali Dati NoSQL

Relazionali e NoSQL sono due tipi di sistemi di database implementati comunemente nelle app native del cloud. Sono compilati in modo diverso, archiviano i dati in modo diverso e sono accessibili in modo diverso In questa sezione verranno esaminati entrambi i aspetti. Più avanti in questo capitolo verrà esaminata una tecnologia di database emergente denominata *NewSQL*.

I *database relazionali* sono stati una tecnologia prevalente per decenni. Sono maturi, collaudati e ampiamente implementati. I prodotti, gli strumenti e le competenze per database in competizione sono molto ricchi. I database relazionali forniscono un archivio di tabelle di dati correlate. Queste tabelle hanno uno schema fisso, usano SQL (Structured Query Language) per gestire i dati e supportano le garanzie ACID.

I *database no-SQL* fanno riferimento ad archivi dati non relazionali a prestazioni elevate. Si distinguono per la facilità d'uso, la scalabilità, la resilienza e le caratteristiche di disponibilità. Anziché riunire tabelle di dati normalizzati, NoSQL archivia dati non strutturati o semistrutturati, spesso in coppie chiave-valore o documenti JSON. Nessun database SQL in genere non fornisce garanzie ACID oltre l'ambito di una singola partizione di database. Servizi di volume elevato che richiedono tempi di risposta di sottosecondo favoriscono gli archivi dati NoSQL.

L'effetto delle tecnologie [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) per i sistemi distribuiti nativi del cloud non può essere sovrastato. La proliferazione di nuove tecnologie dati in questo spazio ha comportato soluzioni che una volta si basavano esclusivamente sui database relazionali.

I database NoSQL includono diversi modelli per l'accesso e la gestione dei dati, ciascuno adatto a specifici casi di utilizzo. La figura 5-9 presenta quattro modelli comuni.

![Modelli di dati NoSQL](./media/types-of-nosql-datastores.png)

**Figura 5-9**: modelli di dati per i database NoSQL

| Modello | Caratteristiche |
| :-------- | :-------- |
| Archivio documenti | I dati e i metadati vengono archiviati gerarchicamente nei documenti basati su JSON all'interno del database. |
| Archivio valore chiave | Il più semplice dei database NoSQL, i dati vengono rappresentati come una raccolta di coppie chiave-valore. |
| Archivio a colonne Wide | I dati correlati vengono archiviati come un set di coppie chiave/valore annidate all'interno di una singola colonna. |
| Archivio grafico | I dati vengono archiviati in una struttura Graph come proprietà Node, Edge e data. |

## <a name="the-cap-theorem"></a>Teorema CAP

Per comprendere le differenze tra questi tipi di database, prendere in considerazione il teorema CAP, un set di principi applicati ai sistemi distribuiti che archiviano lo stato. La figura 5-10 illustra le tre proprietà del teorema CAP.

![Teorema CAP](./media/cap-theorem.png)

**Figura 5-10**. Teorema CAP

Il teorema indica che i sistemi di dati distribuiti offriranno un compromesso tra coerenza, disponibilità e tolleranza di partizione. E che qualsiasi database possa garantire solo *due* delle tre proprietà:

- *Coerenza.* Ogni nodo del cluster risponde con i dati più recenti, anche se il sistema deve bloccare la richiesta fino a quando tutte le repliche non vengono aggiornate. Se si esegue una query su un "sistema coerente" per un elemento attualmente in fase di aggiornamento, si attenderà tale risposta finché tutte le repliche non verranno aggiornate correttamente. Si riceveranno tuttavia i dati più recenti.

- *Disponibilità.* Ogni nodo restituisce una risposta immediata, anche se tale risposta non è i dati più recenti. Se si esegue una query su un "sistema disponibile" per un elemento in fase di aggiornamento, si otterrà la migliore risposta possibile che il servizio può fornire in quel momento.

- *Tolleranza della partizione.* Garantisce che il sistema continui a funzionare anche in caso di errore di un nodo di dati replicati o di perdita della connettività con altri nodi dati replicati.

I database relazionali forniscono in genere coerenza e disponibilità, ma non la tolleranza della partizione. Viene in genere eseguito il provisioning in un singolo server e la scalabilità verticale tramite l'aggiunta di altre risorse al computer.

Molti sistemi di database relazionali supportano le funzionalità di replica predefinite in cui è possibile effettuare copie del database primario in altre istanze del server secondario. Le operazioni di scrittura vengono eseguite nell'istanza primaria e replicate in ognuno dei database secondari. Quando si verifica un errore, l'istanza primaria può eseguire il failover su un database secondario per garantire un'elevata disponibilità. I database secondari possono essere usati anche per distribuire le operazioni di lettura. Mentre le operazioni di scrittura vengono sempre eseguite sulla replica primaria, le operazioni di lettura possono essere indirizzate a qualsiasi database secondario per ridurre il carico di sistema.

I dati possono anche essere partizionati orizzontalmente in più nodi, ad esempio [con il partizionamento](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-scale-introduction)orizzontale. Il partizionamento orizzontale, tuttavia, aumenta in modo significativo il sovraccarico operativo, sputando i dati in molte parti che non possono comunicare con facilità. Può risultare costoso e dispendioso in termini di tempo da gestire. Può compromettere le prestazioni, i join di tabella e l'integrità referenziale.

Se le repliche di dati dovessero perdere la connettività di rete in un cluster di database relazionale "estremamente coerente", non sarebbe possibile scrivere nel database. Il sistema rifiuterà l'operazione di scrittura perché non è in grado di replicare la modifica apportata all'altra replica dei dati. Ogni replica dati deve essere aggiornata prima che la transazione possa essere completata.

I database NoSQL in genere supportano la disponibilità elevata e la tolleranza della partizione. Aumentano orizzontalmente, spesso in tutti i server di prodotti. Questo approccio offre una straordinaria disponibilità, sia all'interno che tra le aree geografiche a un costo ridotto. È possibile partizionare e replicare i dati tra questi computer, o nodi, garantendo ridondanza e tolleranza di errore. Il lato negativo è la coerenza. Una modifica ai dati in un nodo NoSQL può richiedere del tempo per la propagazione ad altri nodi. In genere, un nodo del database NoSQL fornirà una risposta immediata a una query, anche se i dati presentati sono obsoleti e non sono stati ancora aggiornati.

Se le repliche di dati dovessero perdere la connettività in un cluster di database NoSQL a disponibilità elevata, è comunque possibile completare un'operazione di scrittura nel database. Il cluster di database consente l'operazione di scrittura e aggiorna ogni replica di dati non appena diventa disponibile.

Questo tipo di risultato è noto come coerenza finale, una caratteristica dei sistemi dati distribuiti in cui non sono supportate le transazioni ACID. Si tratta di un breve ritardo tra l'aggiornamento di un elemento di dati e il tempo necessario per propagare tale aggiornamento a ogni nodo di replica. In condizioni normali, il ritardo è in genere breve, ma può aumentare quando si verificano problemi. Ad esempio, cosa accade se si aggiorna un elemento del prodotto in un database NoSQL nel Stati Uniti e si esegue una query sullo stesso elemento di dati da un nodo di replica in Europa? Si riceveranno le informazioni precedenti sul prodotto, fino a quando il cluster non aggiornerà il nodo europeo con la modifica del prodotto. Restituendo immediatamente il risultato di una query e non attendendo l'aggiornamento di tutti i nodi di replica, si ottengono scalabilità e volume enormi, ma con la possibilità di presentare dati meno recenti.

La disponibilità elevata e la scalabilità di grandi dimensioni sono spesso più critiche per l'azienda rispetto alla coerenza assoluta. Gli sviluppatori possono implementare tecniche e modelli, ad esempio saghe, CQRS e messaggistica asincrona, per adottare la coerenza finale.

> Attualmente è necessario prestare attenzione quando si conidering i vincoli del teorema CAP. È emerso un nuovo tipo di database, denominato NewSQL, che estende il motore di database relazionale per supportare sia la scalabilità orizzontale che la scalabilità delle prestazioni dei sistemi NoSQL.

## <a name="considerations-for-relational-vs-nosql-systems"></a>Considerazioni sui sistemi relazionali e NoSQL

In base ai requisiti specifici dei dati, un microservizio basato su cloud nativo può implementare un archivio dati relazionale, NoSQL o entrambi.

|  Si consideri un archivio dati NoSQL quando: | Considerare un database relazionale nei casi seguenti: |
| :-------- | :-------- |
| Sono presenti carichi di lavoro con volumi elevati che richiedono scalabilità elevata | Il volume del carico di lavoro è coerente e richiede una scala media-large |
| I carichi di lavoro non richiedono garanzie ACID |  Sono necessarie le garanzie ACID |
| I dati sono dinamici e vengono modificati di frequente | I dati sono prevedibili e altamente strutturati |
| I dati possono essere espressi senza relazioni | I dati sono espressi in modo ottimale in modo relazionale |  
| Sono necessarie Scritture rapide e la protezione della scrittura non è fondamentale | La protezione da scrittura è un requisito |  
| Il recupero dei dati è semplice e tende a essere Flat | Utilizzo di query e report complessi|
| I dati richiedono un'ampia distribuzione geografica | Gli utenti sono più centralizzati |
| L'applicazione verrà distribuita nell'hardware di un prodotto, ad esempio con i cloud pubblici | L'applicazione verrà distribuita in hardware di grandi dimensioni di fascia alta |

Nelle sezioni successive verranno analizzate le opzioni disponibili nel cloud di Azure per l'archiviazione e la gestione dei dati nativi del cloud.

## <a name="database-as-a-service"></a>Database distribuito come servizio

Per iniziare, è possibile effettuare il provisioning di una macchina virtuale di Azure e installare il database scelto per ogni servizio. Sebbene si disponga di un controllo completo sull'ambiente, è opportuno rinunciare a numerose funzionalità predefinite della piattaforma cloud. Si è inoltre responsabili della gestione della macchina virtuale e del database per ogni servizio. Questo approccio può diventare rapidamente dispendioso in termini di tempo e costoso.

Al contrario, le applicazioni native del cloud favoriscono i servizi dati esposti come [database come servizio (DBaaS)](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/). Completamente gestito da un fornitore di servizi cloud, questi servizi forniscono sicurezza, scalabilità e monitoraggio predefiniti. Anziché essere proprietario del servizio, è sufficiente utilizzarlo come [servizio di backup](./definition.md#backing-services). Il provider gestisce la risorsa su larga scala e ha la responsabilità di prestazioni e manutenzione.

Possono essere configurate in aree e zone di disponibilità cloud per ottenere la disponibilità elevata. Supportano la capacità just-in-time e un modello con pagamento in base al consumo. Azure offre diversi tipi di opzioni di servizi dati gestiti, ognuno con vantaggi specifici.

Per prima cosa verranno esaminati i servizi DBaaS relazionali disponibili in Azure. Si noterà che l'ammiraglia di Microsoft SQL Server database è disponibile insieme a diverse opzioni open source. Quindi, parleremo dei servizi dati di NoSQL in Azure.

## <a name="azure-relational-databases"></a>Database relazionali di Azure

Per i microservizi nativi del cloud che richiedono dati relazionali, Azure offre quattro offerte database relazionali come servizio (DBaaS) gestite, illustrate nella figura 5-11.

![Database relazionali gestiti in Azure](./media/azure-managed-databases.png)

**Figura 5-11**. Database relazionali gestiti disponibili in Azure

Nella figura precedente si noti che ognuno si trova su un'infrastruttura DBaaS comune che offre funzionalità chiave senza costi aggiuntivi.

Queste funzionalità sono particolarmente importanti per le organizzazioni che eseguono il provisioning di un numero elevato di database, ma hanno risorse limitate per gestirle.
È possibile effettuare il provisioning di un database di Azure in pochi minuti selezionando la quantità di core di elaborazione, la memoria e l'archiviazione sottostante. Puoi ridimensionare il database in tempo reale e modificare dinamicamente le risorse senza tempi di inattività.

## <a name="azure-sql-database"></a>database SQL di Azure

I team di sviluppo con competenze in Microsoft SQL Server devono prendere in considerazione il [database SQL di Azure](https://docs.microsoft.com/azure/sql-database/). Si tratta di un database relazionale come servizio completamente gestito (DBaaS) basato sul motore di database Microsoft SQL Server. Il servizio condivide molte funzionalità disponibili nella versione locale di SQL Server ed esegue la versione stabile più recente del motore di database di SQL Server.

Per l'uso con un microservizio nativo del cloud, il database SQL di Azure è disponibile con tre opzioni di distribuzione:

- Una Database singolo rappresenta un database SQL completamente gestito in esecuzione in un [server di database SQL di Azure](https://docs.microsoft.com/azure/sql-database/sql-database-servers) nel cloud di Azure. Il database viene considerato [*contenuto*](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) perché non ha dipendenze di configurazione sul server di database sottostante.
  
- Una [istanza gestita](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) è un'istanza completamente gestita del motore di database di Microsoft SQL Server che garantisce una compatibilità quasi al 100% con una SQL Server locale. Questa opzione supporta database di dimensioni maggiori, fino a 35 TB e viene posizionata in una [rete virtuale di Azure](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) per un migliore isolamento.

- Il [database SQL di Azure senza server](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) è un livello di calcolo per un singolo database che viene ridimensionato automaticamente in base alla domanda del carico di lavoro. Fattura solo la quantità di risorse di calcolo usate al secondo. Il servizio è particolarmente adatto per carichi di lavoro con modelli di utilizzo intermittenti e non prevedibili, sparpagliati con periodi di inattività. Il livello di calcolo senza server inoltre sospende automaticamente i database durante i periodi di inattività, in modo che vengano addebitati solo i costi di archiviazione. Riprende automaticamente quando l'attività restituisce.

Oltre allo stack di Microsoft SQL Server tradizionale, Azure include anche le versioni gestite dei tre database open source più diffusi.

## <a name="open-source-databases-in-azure"></a>Database open source in Azure

I database relazionali Open Source sono diventati una scelta molto diffusa per le applicazioni native del cloud. Molte aziende li prediligono rispetto ai prodotti di database commerciali, soprattutto per risparmiare sui costi. Molti team di sviluppo godono di flessibilità, sviluppo supportato dalla community e ecosistema di strumenti ed estensioni. I database open source possono essere distribuiti tra più provider di servizi cloud, riducendo al minimo la preoccupazione di "blocco del fornitore".

Gli sviluppatori possono facilmente ospitare autonomamente qualsiasi database open source in una macchina virtuale di Azure. Fornendo il controllo completo, questo approccio consente di gestire, monitorare e gestire il database e la macchina virtuale.

Tuttavia, Microsoft continua a impegnarsi per mantenere Azure una "piattaforma aperta" offrendo diversi database open source diffusi come servizi DBaaS *completamente gestiti* .

### <a name="azure-database-for-mysql"></a>Database di Azure per MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL)   è un database relazionale open source e un pilastro per le applicazioni basate sullo [stack LAMP software](https://en.wikipedia.org/wiki/LAMP_(software_bundle)). Ampiamente scelto per i carichi di lavoro di *lettura pesanti* , viene usato da molte organizzazioni di grandi dimensioni, tra cui Facebook, Twitter e YouTube. La Community Edition è disponibile gratuitamente, mentre la versione Enterprise Edition richiede l'acquisto di una licenza. Originariamente creato in 1995, il prodotto è stato acquistato da Sun Microsystems in 2008. Oracle ha acquisito Sun e MySQL in 2010.

[Database di Azure per MySQL](https://azure.microsoft.com/services/mysql/) è un servizio di database relazionale gestito basato sul motore del server MySQL open source. USA MySQL Community Edition. Il server MySQL di Azure è il punto di amministrazione per il servizio. Si tratta dello stesso motore di MySQL server usato per le distribuzioni locali. Il motore di può creare un singolo database per ogni server o più database per server che condividono risorse. È possibile continuare a gestire i dati usando gli stessi strumenti open source senza dover apprendere nuove competenze o gestire le macchine virtuali.

### <a name="azure-database-for-mariadb"></a>Database di Azure per MariaDB

[MariaDB](https://mariadb.com/) Server è un altro noto server di database open source. È stato creato come *fork* di MySQL quando Oracle ha acquistato Sun Microsystems, proprietario di MySQL. Lo scopo era quello di garantire che MariaDB fosse rimasto open source. Poiché MariaDB è un fork di MySQL, le definizioni di dati e tabelle sono compatibili, mentre i protocolli, le strutture e le API client sono di chiusura.

MariaDB ha una community avanzata e viene usata da molte grandi aziende. Sebbene Oracle continui a mantenere, migliorare e supportare MySQL, MariaDB Foundation gestisce MariaDB, consentendo contributi pubblici al prodotto e alla documentazione.

[Database di Azure per MariaDB](https://azure.microsoft.com/services/mariadb/) è un database relazionale completamente gestito come servizio nel cloud di Azure. Il servizio è basato sul motore del server MariaDB Community Edition. Consente di gestire carichi di lavoro cruciali con prestazioni prevedibili e scalabilità dinamica.

### <a name="azure-database-for-postgresql"></a>Database di Azure per PostgreSQL

[PostgreSQL](https://www.postgresql.org/) è un database relazionale open source con oltre 30 anni di sviluppo attivo. PostgreSQL ha una solida reputazione per l'affidabilità e l'integrità dei dati. Si tratta di funzionalità avanzate, conformi a SQL e considerate più performanti rispetto a MySQL, specialmente per i carichi di lavoro con query complesse e scritture pesanti. Molte grandi aziende, tra cui Apple, Red Hat e Fujitsu, hanno creato prodotti con PostgreSQL.

[Database di Azure per PostgreSQL](https://azure.microsoft.com/services/postgresql/) è un servizio di database relazionale completamente gestito, basato sul motore di database Postgres open source. Il servizio supporta molte piattaforme di sviluppo, tra cui C++, Java, Python, node, C \# e php. È possibile eseguire la migrazione di database PostgreSQL usando lo strumento dell' [interfaccia della riga di comando](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) o il servizio migrazione dei dati di Azure.

Database di Azure per PostgreSQL è disponibile con due opzioni di distribuzione:

- L'opzione di distribuzione a [server singolo](https://docs.microsoft.com/azure/postgresql/concepts-servers) è un punto amministrativo centrale per più database in cui è possibile distribuire molti database. I prezzi sono strutturati per server in base ai core e all'archiviazione.

- L' [opzione iperscale (CITUS)](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) è basata sulla tecnologia CITUS Data Technology. Consente prestazioni elevate mediante *scalabilità orizzontale* di un database singolo in centinaia di nodi per offrire prestazioni e scalabilità rapide. Questa opzione consente al motore di adattare più dati in memoria, parallelizzare le query tra centinaia di nodi e indicizzare i dati più velocemente.

## <a name="nosql-data-in-azure"></a>NoSQL dati in Azure

Cosmos DB è un servizio di database NoSQL completamente gestito e distribuito a livello globale nel cloud di Azure. È stata adottata da molte aziende di grandi dimensioni in tutto il mondo, tra cui Coca-Cola, Skype, ExxonMobil e Liberty Mutual.

Se i servizi richiedono una risposta rapida da qualsiasi parte del mondo, disponibilità elevata o scalabilità elastica, Cosmos DB rappresenta la scelta ottimale. La figura 5-12 Mostra Cosmos DB.

![Panoramica di Cosmos DB](./media/cosmos-db-overview.png)

**Figura 5-12**: panoramica di Cosmos DB

La figura precedente presenta molte delle funzionalità native del cloud predefinite disponibili in Cosmos DB. In questa sezione verranno esaminati in modo più approfondito.

### <a name="global-support"></a>Supporto globale

Le applicazioni native del cloud spesso hanno un pubblico globale e richiedono la scalabilità globale.

È possibile distribuire i database Cosmos tra aree o in tutto il mondo, inserendo dati vicini agli utenti, migliorando il tempo di risposta e riducendo la latenza. È possibile aggiungere o rimuovere un database da un'area senza sospendere o ridistribuire i servizi. In background, Cosmos DB replica in modo trasparente i dati in ogni area configurata.

Cosmos DB supporta il clustering [attivo/attivo](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) a livello globale, consentendo di configurare le aree del database per supportare le operazioni di *scrittura e lettura*.

Il protocollo [multimaster](https://docs.microsoft.com/azure/cosmos-db/multi-master-benefits) è una funzionalità importante di Cosmos DB che consente di abilitare le funzionalità seguenti:

- Scalabilità di lettura e scrittura elastica illimitata.

- Disponibilità in lettura e scrittura pari al 99,999% in tutto il mondo.

- Letture e scritture gestite in meno di 10 millisecondi nel 99% dei casi.

Con le [API](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)multihosting di Cosmos DB, il microservizio è automaticamente a conoscenza dell'area di Azure più vicina e invia le richieste. L'area più vicina viene identificata da Cosmos DB senza modifiche alla configurazione. Se un'area non è più disponibile, la funzionalità multihosting indirizza automaticamente le richieste alla successiva area disponibile più vicina.

### <a name="multi-model-support"></a>Supporto per più modelli

Quando si ricrea la piattaforma di applicazioni monolitiche in un'architettura nativa del cloud, i team di sviluppo devono talvolta migrare gli archivi dati NoSQL open source. Cosmos DB consentono di preservare gli investimenti in questi archivi dati NoSQL con la relativa piattaforma dati *multimodello* . La tabella seguente illustra le API di [compatibilità](https://www.wikiwand.com/en/Cosmos_DB)NoSQL supportate.

| Provider | Description  |
| :-------- | :-------- |
| API SQL | API proprietaria che supporta documenti JSON e query basate su SQL |
| API MongoDB | Supporta le API del database Mongo e i documenti JSON|
| API Gremlin | Supporta l'API Gremlin con nodi basati su grafico e rappresentazioni di dati perimetrali |
| API Cassandra | Supporta l'API Casandra per le rappresentazioni di dati a colonna estesa |  
| API di tabella  | Supporta l'archiviazione tabelle di Azure con miglioramenti Premium |  
| API ETCD | Abilita Cosmos DB come archivio di backup per i cluster del servizio Kubernetes di Azure |

I team di sviluppo possono migrare i database Mongo, Gremlin o Cassandra esistenti in Cosmos DB con modifiche minime al codice o ai dati. Per le nuove app, i team di sviluppo possono scegliere tra le opzioni open source o il modello API SQL incorporato.

> Internamente, Cosmos archivia i dati in un formato struct semplice costituito da tipi di dati primitivi. Per ogni richiesta, il motore di database converte i dati primitivi nella rappresentazione del modello selezionata.

Nella tabella precedente prendere nota dell'opzione [API tabella](https://docs.microsoft.com/azure/cosmos-db/table-introduction) . Questa API è un'evoluzione dell'archiviazione tabelle di Azure. Entrambi condividono lo stesso modello di tabella sottostante, ma il Cosmos DB API Tabella aggiunge miglioramenti Premium non disponibili nell'API di archiviazione di Azure. La tabella seguente mette a confronto le funzionalità di.

|  | Archiviazione tabelle di Azure  | Azure Cosmos DB  |
| :-------- | :-------- |:-------- |
| Latenza | Veloce | Latenza in millisecondi a singola cifra per letture e scritture in qualsiasi parte del mondo |
| Velocità effettiva | Limite di 20.000 operazioni per tabella | 10 milioni operazioni per tabella |
| Distribuzione globale | Area singola con area di lettura singola secondaria facoltativa | Distribuzioni chiavi in mano in tutte le aree con failover automatico |
| Indicizzazione | Disponibile solo per le proprietà chiave di partizione e di riga | Indicizzazione automatica di tutte le proprietà |
| Prezzi | In base all'archiviazione | In base alla velocità effettiva |

I microservizi che usano l'archiviazione tabelle di Azure possono eseguire facilmente la migrazione al API Tabella Cosmos DB. Non sono necessarie modifiche al codice.

### <a name="tunable-consistency"></a>Coerenza ottimizzabile

In precedenza nella sezione *relazionale rispetto a NoSQL* è stato illustrato l'oggetto della *coerenza dei dati*. La coerenza dei dati si riferisce all' *integrità* dei dati. I servizi nativi del cloud con dati distribuiti si basano sulla replica e devono avere un compromesso fondamentale tra coerenza di lettura, disponibilità e latenza.

La maggior parte dei database distribuiti consente agli sviluppatori di scegliere tra due modelli di coerenza: coerenza assoluta e coerenza finale. La *coerenza* assoluta è lo standard Gold di programmabilità dei dati. Garantisce che una query restituirà sempre i dati più recenti, anche se il sistema deve subire una latenza in attesa che un aggiornamento venga replicato in tutte le copie del database. Mentre un database configurato per la *coerenza finale* restituirà immediatamente i dati, anche se tali dati non sono la copia più recente. La seconda opzione consente una maggiore disponibilità, una maggiore scalabilità e prestazioni migliorate.

Azure Cosmos DB offre cinque [modelli di coerenza](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) ben definiti illustrati nella figura 5-13.

![Grafico di coerenza Cosmos DB](./media/cosmos-consistency-level-graph.png)

**Figura 5-13**: livelli di coerenza Cosmos DB

 Queste opzioni consentono di effettuare scelte precise e compromessi granulari per coerenza, disponibilità e prestazioni per i dati. I livelli sono riportati nella tabella seguente.

| Livello di coerenza | Description  |
| :-------- | :-------- |
| Finale | Nessuna garanzia di ordinamento per le letture. Alla fine le repliche saranno convergenti. |
| Prefisso costante | Le letture sono ancora finali, ma i dati vengono restituiti nell'ordine in cui vengono scritti. |
| sessione | Garantisce che sia possibile leggere tutti i dati scritti durante la sessione corrente. Si tratta del livello di coerenza predefinito. |
| Decadimento ristretto | Legge le Scritture della traccia in base all'intervallo specificato. |  
| Assoluta  | Viene garantita la restituzione della versione più recente di un elemento di cui è stato eseguito il commit. Un client non rileva mai una lettura parziale o di cui non è stato eseguito il commit. |  

Nell'articolo relativo [alla gestione dei livelli di coerenza Cosmos DB illustrati](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)in questo articolo, Jeremy Likness fornisce una spiegazione eccellente dei cinque modelli.

### <a name="partitioning"></a>Partizionamento

Azure Cosmos DB abbraccia il [partizionamento](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) automatico per ridimensionare un database per soddisfare le esigenze di prestazioni dei servizi nativi del cloud.

È possibile gestire i dati in Cosmos DB dati creando database, contenitori ed elementi.

I contenitori risiedono in un database di Cosmos DB e rappresentano un raggruppamento di elementi indipendente dallo schema. Gli elementi sono i dati che si aggiungono al contenitore. Sono rappresentati come documenti, righe, nodi o bordi. Tutti gli elementi aggiunti a un contenitore vengono indicizzati automaticamente.

Per partizionare il contenitore, gli elementi sono divisi in subset distinti denominati partizioni logiche. Le partizioni logiche vengono popolate in base al valore di una chiave di partizione associata a ogni elemento in un contenitore. La figura 5-14 Mostra due contenitori ognuno con una partizione logica basata su un valore della chiave di partizione.

![Cosmos DB meccanismi di partizionamento](./media/cosmos-db-partitioning.png)

**Figura 5-14**: Cosmos DB meccanismi di partizionamento

Si noti che nella figura precedente il modo in cui ogni elemento include una chiave di partizione ' City ' o ' Airport '. La chiave determina la partizione logica dell'elemento. Gli elementi con un codice città vengono assegnati al contenitore a sinistra e gli elementi con un codice aeroportuale al contenitore a destra. Combinando il valore della chiave di partizione con il valore ID, viene creato l'indice di un elemento che identifica in modo univoco l'elemento.

Internamente, Cosmos DB gestisce automaticamente il posizionamento delle [partizioni logiche](https://docs.microsoft.com/azure/cosmos-db/partition-data) nelle partizioni fisiche per soddisfare le esigenze di scalabilità e prestazioni del contenitore. Man seconda che i requisiti di archiviazione e velocità effettiva delle applicazioni aumentano, Azure Cosmos DB ridistribuisce le partizioni logiche in un numero maggiore di server. Le operazioni di ridistribuzione vengono gestite da Cosmos DB e richiamate senza interruzioni o tempi di inattività.

## <a name="newsql-databases"></a>Database NewSQL

*NewSQL*   è una tecnologia di database emergente che combina la scalabilità distribuita di NoSQL con le garanzie ACID di un database relazionale. I database NewSQL sono importanti per i sistemi aziendali che devono elaborare volumi elevati di dati, in ambienti distribuiti, con supporto transazionale completo e conformità ACID. Sebbene un database NoSQL possa fornire scalabilità elevata, non garantisce la coerenza dei dati. I problemi intermittenti da dati incoerenti possono commettere un carico di forza nel team di sviluppo. Gli sviluppatori devono creare misure di sicurezza nel codice del microservizio per gestire i problemi causati da dati incoerenti.

Cloud native Computing Foundation (CNCF) offre diversi progetti di database NewSQL.

| Project | Caratteristiche |
| :-------- | :-------- |
| DATABASE scarafaggio |Database relazionale conforme a ACID, scalabile a livello globale. Aggiungere un nuovo nodo a un cluster e CockroachDB si occupa del bilanciamento dei dati tra istanze e aree geografiche. Consente di creare, gestire e distribuire repliche per garantire l'affidabilità. È open source e disponibile gratuitamente.  |
| TiDB | Database open source che supporta carichi di lavoro di elaborazione analitica e transazionale (HTAP) ibridi. È compatibile con MySQL e offre scalabilità orizzontale, coerenza assoluta e disponibilità elevata.  TiDB funge da server MySQL. È possibile continuare a usare le librerie client MySQL esistenti, senza richiedere modifiche di codice estese all'applicazione. |
| YugabyteDB | Un database SQL open source, ad alte prestazioni e distribuito. Supporta la bassa latenza delle query, la resilienza in caso di errori e la distribuzione globale dei dati. YugabyteDB è compatibile con PostgressSQL e gestisce i carichi di lavoro OLTP con scalabilità orizzontale e Internet. Il prodotto supporta anche NoSQL ed è compatibile con Cassandra. |
|Vite | Si tratta di una soluzione di database per la distribuzione, il ridimensionamento e la gestione di cluster di grandi dimensioni di istanze di MySQL. Può essere eseguito in un'architettura di cloud pubblico o privato. Viten combina ed estende molte importanti funzionalità di MySQL e offre funzionalità di partizionamento orizzontale verticali e orizzontali. Originato da YouTube, le vite hanno servito tutto il traffico del database di YouTube a partire da 2011. |

I progetti open source nella figura precedente sono disponibili nel cloud native Computing Foundation. Tre delle offerte sono prodotti di database completi che includono il supporto di .NET Core. L'altro è un sistema di clustering di database che ridimensiona orizzontalmente i cluster di grandi dimensioni di istanze di MySQL.

Un obiettivo di progettazione principale per i database NewSQL è lavorare in modo nativo in Kubernetes, sfruttando la resilienza e la scalabilità della piattaforma.

I database NewSQL sono progettati per prosperare negli ambienti cloud temporanei in cui le macchine virtuali sottostanti possono essere riavviate o ripianificate in un momento di preavviso. I database sono progettati per sopravvivere agli errori dei nodi senza perdita di dati o tempi di inattività. CockroachDB, ad esempio, è in grado di sopravvivere a una perdita di computer mantenendo tre repliche coerenti di tutti i dati tra i nodi di un cluster.

Kubernetes utilizza un *costrutto di servizi* per consentire a un client di indirizzare un gruppo di processi di database NewSQL identici da una singola voce DNS. Separando le istanze di database dall'indirizzo del servizio a cui è associato, è possibile applicare la scalabilità senza compromettere le istanze dell'applicazione esistenti. L'invio di una richiesta a un servizio in un determinato momento produrrà sempre lo stesso risultato.

In questo scenario, tutte le istanze del database sono uguali. Non sono presenti relazioni primarie o secondarie. Tecniche come la *replica di consenso* disponibile in CockroachDB consentono a qualsiasi nodo del database di gestire qualsiasi richiesta. Se il nodo che riceve una richiesta con carico bilanciato ha i dati necessari in locale, risponde immediatamente. In caso contrario, il nodo diventa un gateway e trasmette la richiesta ai nodi appropriati per ottenere la risposta corretta. Dal punto di vista del client, ogni nodo del database è lo stesso: vengono visualizzati come un singolo database *logico* con le garanzie di coerenza di un sistema a singolo computer, nonostante siano presenti dozzine o addirittura centinaia di nodi che operano dietro le quinte.

Per informazioni dettagliate sui meccanismi dietro i database NewSQL, vedere l'articolo [Dash: Four Properties of Kubernetes-native databases](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/) .

## <a name="data-migration-to-the-cloud"></a>Migrazione dei dati nel cloud

Una delle attività più dispendiose in termini di tempo è la migrazione dei dati da una piattaforma di dati a un'altra. Il [servizio migrazione dei dati di Azure](https://azure.microsoft.com/services/database-migration/) consente di velocizzare tali attività. Consente di eseguire la migrazione dei dati da diverse origini di database esterne a piattaforme dati di Azure con tempi di inattività minimi. Le piattaforme di destinazione includono i servizi seguenti:

- database SQL di Azure
- Database di Azure per MySQL
- Database di Azure per MariaDB
- Database di Azure per PostgreSQL
- Cosmos DB
  
Il servizio fornisce consigli per eseguire le modifiche necessarie per eseguire una migrazione, sia piccola che grande.

>[!div class="step-by-step"]
>[Precedente](distributed-data.md) 
> [Avanti](azure-caching.md)
