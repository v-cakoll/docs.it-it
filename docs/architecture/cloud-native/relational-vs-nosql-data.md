---
title: Modelli di data mining relazionali Dati NoSQL
description: Informazioni sui dati relazionali e NoSQL nelle applicazioni native cloudLearn about relational and NoSQL data in cloud-native applications
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 3fb3dcc3a87e278c05f3e15d261245f4d61453d1
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805803"
---
# <a name="relational-vs-nosql-data"></a>Modelli di data mining relazionali Dati NoSQL

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Relazionale e NoSQL sono due tipi di sistemi di database comunemente implementati nelle applicazioni native cloud. Vengono costruiti in modo diverso, archiviano i dati in modo diverso e vi si accede in modo diverso. In questa sezione, vedremo entrambi. Più avanti in questo capitolo, vedremo una tecnologia di database emergente chiamata *NewSQL*.

*I database relazionali* sono una tecnologia prevalente da decenni. Sono maturi, collaudati e ampiamente implementati. I prodotti di database concorrenti, gli utensili e le competenze abbondano. I database relazionali forniscono un archivio di tabelle dati correlate. Queste tabelle hanno uno schema fisso, utilizzano SQL (Structured Query Language) per gestire i dati e supportano le garanzie ACID.

*I database No-SQL* fanno riferimento a archivi dati ad alte prestazioni e non relazionali. Essi eccellono nelle loro caratteristiche di facilità d'uso, scalabilità, resilienza e disponibilità. Invece di unire tabelle di dati normalizzati, NoSQL archivia dati non strutturati o semistrutturati, spesso in coppie chiave-valore o documenti JSON. I database No-SQL in genere non forniscono garanzie ACID oltre l'ambito di una singola partizione di database. I servizi con volumi elevati che richiedono un tempo di risposta di secondo secondario favoriscono gli archivi dati NoSQL.High volume services that require sub second second response time favor i NoSQL datastores.

L'impatto delle tecnologie [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) per i sistemi nativi cloud distribuiti non può essere sopravvalutato. La proliferazione di nuove tecnologie di dati in questo spazio ha rivoluzionato le soluzioni che un tempo si basavano esclusivamente su database relazionali.

I database NoSQL includono diversi modelli diversi per l'accesso e la gestione dei dati, ognuno adatto a casi d'uso specifici. Figura 5-9 presenta quattro modelli comuni.

![Modelli di dati NoSQL](./media/types-of-nosql-datastores.png)

**Figura 5-9**: Modelli di dati per i database NoSQL

| Modello | Caratteristiche |
| :-------- | :-------- |
| Archivio documenti | I dati e i metadati vengono archiviati gerarchicamente nei documenti basati su JSON all'interno del database. |
| Archivio valori chiave | Il più semplice dei database NoSQL, i dati sono rappresentati come una raccolta di coppie chiave-valore. |
| Archivio a colonne wide | I dati correlati vengono archiviati come un set di coppie chiave/valore annidate all'interno di una singola colonna. |
| Negozio grafico | I dati vengono archiviati in una struttura del grafico come proprietà di nodi, bordi e dati. |

## <a name="the-cap-theorem"></a>Il teorema della PAC

Per comprendere le differenze tra questi tipi di database, si consideri il teorema CAP, un insieme di principi applicati ai sistemi distribuiti che archiviano lo stato. La figura 5-10 mostra le tre proprietà del teorema CAP.

![Teorema CAP](./media/cap-theorem.png)

**Figura 5-10**. Il teorema della PAC

Il teorema afferma che i sistemi di dati distribuiti offriranno un compromesso tra coerenza, disponibilità e tolleranza di partizione. E, che qualsiasi database può garantire solo *due* delle tre proprietà:

- *Coerenza.* Ogni nodo del cluster risponde con i dati più recenti, anche se il sistema deve bloccare la richiesta fino all'aggiornamento di tutte le repliche. Se si esegue una query su un "sistema coerente" per un elemento che è in fase di aggiornamento, la risposta attenderà fino al completamento dell'aggiornamento di tutte le repliche. Tuttavia, riceverai i dati più aggiornati.

- *Disponibilità.* Ogni nodo restituisce una risposta immediata, anche se tale risposta non è il dato più recente. Se si esegue una query su un "sistema disponibile" per un elemento che viene aggiornato, si otterrà la migliore risposta possibile che il servizio può fornire in quel momento.

- *Tolleranza della partizione.* Garantisce che il sistema continui a funzionare anche se un nodo di dati replicato non riesce o perde la connettività con altri nodi di dati replicati.

I database relazionali forniscono in genere coerenza e disponibilità, ma non la tolleranza alle partizioni. In genere viene eseguito il provisioning in un singolo server e vengono ridimensionati verticalmente aggiungendo altre risorse alla macchina.

Molti sistemi di database relazionali supportano funzionalità di replica incorporate in cui è possibile eseguire copie del database primario in altre istanze del server secondario. Le operazioni di scrittura vengono eseguite nell'istanza primaria e replicate in ognuno dei database secondari. In caso di errore, l'istanza primaria può eseguire il failover a un database secondario per garantire la disponibilità elevata. Le secondarie possono essere utilizzate anche per distribuire le operazioni di lettura. Mentre le operazioni di scrittura vanno sempre sulla replica primaria, le operazioni di lettura possono essere instradate a uno qualsiasi dei secondari per ridurre il carico del sistema.

I dati possono anche essere partizionati orizzontalmente su più nodi, ad esempio con [il partizionamento orizzontale.](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-scale-introduction) Tuttavia, il partizionamento forzatura aumenta notevolmente l'overhead operativo sputando dati su molti elementi che non possono comunicare facilmente. La gestione può essere costosa e dispendiosa in termini di tempo. Può influire sulle prestazioni, sui join delle tabelle e sull'integrità referenziale.

Se le repliche di dati perdano la connettività di rete in un cluster di database relazionale "altamente coerente", non sarebbe possibile scrivere nel database. Il sistema rifiuterebbe l'operazione di scrittura perché non è in grado di replicare tale modifica nell'altra replica di dati. Ogni replica di dati deve essere aggiornata prima del completamento della transazione.

I database NoSQL supportano in genere la disponibilità elevata e la tolleranza di partizione. Scalabilità orizzontale, spesso tra i server delle merci. Questo approccio offre un'enorme disponibilità, sia all'interno che all'interno delle aree geografiche a un costo ridotto. È possibile partizionare e replicare i dati tra questi computer, o nodi, fornendo ridondanza e tolleranza di errore. Il rovescio della medaglia è la coerenza. Una modifica ai dati in un nodo NoSQL può richiedere del tempo per propagarsi ad altri nodi. In genere, un nodo di database NoSQL fornirà una risposta immediata a una query, anche se i dati presentati non sono aggiornati.

Se le repliche di dati dovessero perdere la connettività in un cluster di database NoSQL "a disponibilità elevata", è comunque possibile completare un'operazione di scrittura nel database. Il cluster di database consentirebbe l'operazione di scrittura e aggiornerebbe ogni replica di dati non appena diventa disponibile.

Questo tipo di risultato è noto come coerenza finale, una caratteristica dei sistemi di dati distribuiti in cui le transazioni ACID non sono supportate. Si tratta di un breve ritardo tra l'aggiornamento di un elemento di dati e il tempo necessario per propagare tale aggiornamento a ciascuno dei nodi di replica. In condizioni normali, il ritardo è in genere breve, ma può aumentare quando sorgono problemi. Ad esempio, cosa accadrebbe se si aggiornasse un elemento di prodotto in un database NoSQL negli Stati Uniti e si eseguisse una query sullo stesso elemento di dati da un nodo di replica in Europa? Si riceveranno le informazioni sul prodotto precedenti, fino a quando il cluster aggiorna il nodo europeo con la modifica del prodotto. Restituendo immediatamente un risultato della query e non attendendo l'aggiornamento di tutti i nodi di replica, si ottengono enormi dimensioni e volumi, ma con la possibilità di presentare dati meno recenti.

Disponibilità elevata e scalabilità massiccia sono spesso più importanti per l'azienda rispetto alla coerenza elevata. Gli sviluppatori possono implementare tecniche e modelli come Sagas, CQRS e messaggistica asincrona per abbracciare la coerenza finale.

> Al giorno d'oggi, occorre fare attenzione quando si concepiscono i vincoli del teorema della PAC. È emerso un nuovo tipo di database, denominato NewSQL, che estende il motore di database relazionale per supportare sia la scalabilità orizzontale che le prestazioni scalabili dei sistemi NoSQL.

## <a name="considerations-for-relational-vs-nosql-systems"></a>Considerazioni sui sistemi relazionali e noSQLConsiderations for relational vs.

In base a requisiti di dati specifici, un microservizio basato su cloud nativo può implementare un datastore relazionale, NoSQL o entrambi.

|  Si consideri un datastore NoSQL quando:Consider a NoSQL datastore when: | Si consideri un database relazionale quando:Consider a relational database when: |
| :-------- | :-------- |
| Si dispone di carichi di lavoro con volume elevato che richiedono scalabilità elevataYou have high volume workloads that require large scale | Il volume del carico di lavoro è coerente e richiede una scalabilità media o su larga scala |
| I carichi di lavoro non richiedono garanzie ACID |  Sono richieste garanzie ACID |
| I dati sono dinamici e cambiano frequentemente | I tuoi dati sono prevedibili e altamente strutturati |
| I dati possono essere espressi senza relazioni | I dati sono meglio espressi relazionalmente |  
| Hai bisogno di scrittura veloce e la sicurezza di scrittura non è critica | La sicurezza di scrittura è un requisito |  
| Il recupero dei dati è semplice e tende ad essere piatto | Si utilizzano query e report complessi|
| I tuoi dati richiedono un'ampia distribuzione geografica | Gli utenti sono più centralizzati |
| L'applicazione verrà distribuita nell'hardware di base, ad esempio con i cloud pubblici | L'applicazione verrà distribuita in hardware di fascia alta di grandi dimensioni |
|||

Nelle sezioni successive verranno esaminate le opzioni disponibili nel cloud di Azure per l'archiviazione e la gestione dei dati nativi del cloud.

## <a name="database-as-a-service"></a>Database distribuito come servizio

Per iniziare, è possibile eseguire il provisioning di una macchina virtuale di Azure e installare il database preferito per ogni servizio. Anche se avresti il pieno controllo sull'ambiente, avresti dimenticato molte funzionalità integrate della piattaforma cloud. Sarai anche responsabile della gestione della macchina virtuale e del database per ogni servizio. Questo approccio potrebbe rapidamente diventare dispendioso in termini di tempo e denaro.

Al contrario, le applicazioni native del cloud predilimono i servizi dati esposti come [Database as a Service (DBaaS)](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/). Completamente gestiti da un fornitore di cloud, questi servizi forniscono sicurezza, scalabilità e monitoraggio integrati. Invece di possedere il servizio, è sufficiente utilizzarlo come servizio di [backup](./definition.md#backing-services). Il fornitore gestisce la risorsa su larga scala e si assume la responsabilità delle prestazioni e della manutenzione.

Possono essere configurati tra aree e zone di disponibilità cloud per ottenere la disponibilità elevata. Supportano tutti la capacità just-in-time e un modello con pagamento in base al reddito. Azure offre diversi tipi di opzioni del servizio dati gestiti, ognuna con vantaggi specifici.

Esamineremo innanzitutto i servizi DBaaS relazionali disponibili in Azure.We'll look at relational DBaaS services available in Azure. Vedrai che il database di punta di SQL Server di Microsoft è disponibile insieme a diverse opzioni open source. Quindi, parleremo dei servizi dati NoSQL in Azure.Then, we'll talk about the NoSQL data services in Azure.

## <a name="azure-relational-databases"></a>Database relazionali di AzureAzure relational databases

Per i microservizi nativi cloud che richiedono dati relazionali, Azure offre quattro offerte di database relazionali gestiti come servizio (DBaaS), illustrati nella Figura 5-11.

![Database relazionali gestiti in AzureManaged relational databases in Azure](./media/azure-managed-databases.png)

**Figura 5-11**. Database relazionali gestiti disponibili in AzureManaged relational databases available in Azure

Nella figura precedente, si noti come ognuno si trova su un'infrastruttura DBaaS comune che dispone di funzionalità chiave senza costi aggiuntivi.

Queste funzionalità sono particolarmente importanti per le organizzazioni che eseguono il provisioning di un numero elevato di database, ma dispongono di risorse limitate per amministrarle.
È possibile eseguire il provisioning di un database di Azure in pochi minuti selezionando la quantità di core di elaborazione, memoria e archiviazione sottostante. È possibile ridimensionare il database in tempo reale e regolare dinamicamente le risorse con tempi di inattività minimo o nessun.

## <a name="azure-sql-database"></a>database SQL di Azure

I team di sviluppo con esperienza in Microsoft SQL Server devono prendere in considerazione il [database SQL di Azure.](https://docs.microsoft.com/azure/sql-database/) Si tratta di un database relazionale completamente gestito come un servizio (DBaaS) basato sul motore di database di Microsoft SQL Server.It's a fully managed relational database-as-a-service (DBaaS) based on the Microsoft SQL Server Database Engine. The service shares many features found in the on-premises version of SQL Server and runs the latest stable version of the SQL Server Database Engine.

Per l'uso con un microservizio nativo cloud, il database SQL di Azure è disponibile con tre opzioni di distribuzione:For use with a cloud-native microservice, Azure SQL Database is available with three deployment options:

- Un database singolo rappresenta un database SQL completamente gestito in esecuzione in un server di database SQL di Azure nel cloud di Azure.A Single Database represents a fully managed SQL Database running on an [Azure SQL Database server](https://docs.microsoft.com/azure/sql-database/sql-database-servers) in the Azure cloud. Il database è [*considerato contenuto*](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) in quanto non ha dipendenze di configurazione nel server di database sottostante.
  
- [Un'istanza gestita](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) è un'istanza completamente gestita del Motore di database di Microsoft SQL ServerSQL Server Database Engine che garantisce la compatibilità quasi al 100% con SQL ServerSQL Server locale. Questa opzione supporta database di dimensioni maggiori, fino a 35 TB e viene inserita in una [rete virtuale](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) di Azure per un migliore isolamento.

- [Il server](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) del database SQL di Azure è un livello di calcolo per un singolo database che viene ridimensionato automaticamente in base alla domanda del carico di lavoro. Fattura solo la quantità di calcolo utilizzata al secondo. Il servizio è adatto per i carichi di lavoro con modelli di utilizzo intermittenti e imprevedibili, intervallati da periodi di inattività. Il livello di calcolo senza server sospende automaticamente i database durante i periodi di inattività in modo che vengano fatturati solo i costi di archiviazione. Riprende automaticamente quando l'attività restituisce.

Oltre allo stack tradizionale di Microsoft SQL Server, Azure include anche versioni gestite di tre database open source popolari.

## <a name="open-source-databases-in-azure"></a>Database open source in AzureOpen-source databases in Azure

I database relazionali open source sono diventati una scelta popolare per le applicazioni native del cloud. Molte aziende li preferiscono rispetto ai prodotti di database commerciali, in particolare per risparmiare sui costi. Molti team di sviluppo godono della loro flessibilità, dello sviluppo sostenuto dalla comunità e dell'ecosistema di strumenti ed estensioni. I database open source possono essere distribuiti tra più provider cloud, contribuendo a ridurre al minimo la preoccupazione di "vendor lock-in".

Gli sviluppatori possono facilmente self-host qualsiasi database open source in una macchina virtuale di Azure.Developers can easily self-host any open-source database on an Azure VM. Pur fornendo il controllo completo, questo approccio offre il controllo per la gestione, il monitoraggio e la manutenzione del database e della macchina virtuale.

Tuttavia, Microsoft continua il suo impegno a mantenere Azure una "piattaforma aperta" offrendo diversi database open source popolari come servizi DBaaS *completamente gestiti.*

### <a name="azure-database-for-mysql"></a>Database di Azure per MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) è un database relazionale open source e un pilastro per le applicazioni create sullo stack di [software LAMP.](https://en.wikipedia.org/wiki/LAMP_(software_bundle)) Ampiamente scelto per la lettura di carichi di lavoro *pesanti,* viene utilizzato da molte organizzazioni di grandi dimensioni, tra cui Facebook, Twitter e YouTube. L'edizione community è disponibile gratuitamente, mentre l'edizione Enterprise richiede l'acquisto di una licenza. Originariamente creato nel 1995, il prodotto è stato acquistato da Sun Microsystems nel 2008. Oracle ha acquisito Sun e MySQL nel 2010.

[Database di Azure per MySQL](https://azure.microsoft.com/services/mysql/) è un servizio di database relazionale gestito basato sul motore Open-source MySQL Server.Azure Database for MySQL is a managed relational database service based on the open-source MySQL Server engine. Utilizza l'edizione MySQL Community. Il server MySQL di Azure è il punto amministrativo per il servizio. È lo stesso motore server MySQL utilizzato per le distribuzioni locali. Il motore può creare un singolo database per server o più database per server che condividono risorse. È possibile continuare a gestire i dati utilizzando gli stessi strumenti open source senza dover apprendere nuove competenze o gestire macchine virtuali.

### <a name="azure-database-for-mariadb"></a>Database di Azure per MariaDB

[MariaDB](https://mariadb.com/) Server è un altro server di database open source comune. E 'stato creato come una *forchetta* di MySQL quando Oracle ha acquistato Sun Microsystems, che possedeva MySQL. L'intento era quello di garantire che MariaDB rimanesse open-source. Poiché MariaDB è un fork di MySQL, i dati e le definizioni delle tabelle sono compatibili e i protocolli client, le strutture e le API sono affiatati.

MariaDB ha una forte comunità ed è utilizzato da molte grandi imprese. Mentre Oracle continua a mantenere, migliorare e supportare MySQL, la fondazione MariaDB gestisce MariaDB, consentendo contributi pubblici al prodotto e alla documentazione.

[Database di Azure per MariaDB](https://azure.microsoft.com/services/mariadb/) è un database relazionale completamente gestito come servizio nel cloud di Azure.Azure Database for MariaDB is a fully managed relational database as a service in the Azure cloud. Il servizio si basa sul motore server MariaDB Community Edition. È in grado di gestire carichi di lavoro mission-critical con prestazioni prevedibili e scalabilità dinamica.

### <a name="azure-database-for-postgresql"></a>Database di Azure per PostgreSQL

[PostgreSQL](https://www.postgresql.org/) è un database relazionale open source con oltre 30 anni di sviluppo attivo. PostgresSQL ha una solida reputazione per l'affidabilità e l'integrità dei dati. È ricco di funzionalità, conforme a SQL e considerato più performante di MySQL, in particolare per i carichi di lavoro con query complesse e scritture pesanti. Molte grandi aziende tra cui Apple, Red Hat e Fujitsu hanno costruito prodotti utilizzando PostgreSQL.

Il database di [Azure per PostgreSQL](https://azure.microsoft.com/services/postgresql/) è un servizio di database relazionale completamente gestito, basato sul motore di database Postgres open source. Il servizio supporta molte piattaforme di sviluppo, tra cui\#C , Java, Python, Node, C e PHP. È possibile eseguire la migrazione dei database PostgreSQL a esso utilizzando lo strumento di interfaccia della riga di comando o il servizio di migrazione dei dati di Azure.You can migrate PostgreSQL databases to it using the [command-line interface](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) tool or Azure Data Migration Service.

Il database di Azure per PostgreSQL è disponibile con due opzioni di distribuzione:Azure Database for PostgreSQL is available with two deployment options:

- L'opzione distribuzione [a server singolo](https://docs.microsoft.com/azure/postgresql/concepts-servers) è un punto amministrativo centrale per più database in cui è possibile distribuire molti database. Il prezzo è strutturato per server in base ai core e all'archiviazione.

- [L'opzione Hyperscale (Citus)](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) è alimentata dalla tecnologia Citus Data. Consente prestazioni elevate *scalando orizzontalmente* un singolo database in centinaia di nodi per offrire prestazioni e scalabilità elevate. Questa opzione consente al motore di adattare più dati in memoria, parallelizzare le query tra centinaia di nodi e indicizzare i dati più rapidamente.

## <a name="nosql-data-in-azure"></a>NoSQL data in Azure

Cosmos DB è un servizio di database NoSQL completamente gestito e distribuito a livello globale nel cloud di Azure.Cosmos DB is a fully managed, globally distributed NoSQL database service in the Azure cloud. È stato adottato da molte grandi aziende in tutto il mondo, tra cui Coca-Cola, Skype, ExxonMobil e Liberty Mutual.

Se i servizi richiedono una risposta rapida da qualsiasi parte del mondo, disponibilità elevata o scalabilità elastica, Cosmos DB è un'ottima scelta. Figura 5-12 Mostra Cosmos DB.

![Panoramica di Cosmos DB](./media/cosmos-db-overview.png)

**Figura 5-12**: Panoramica di Cosmos DB

La figura precedente presenta molte delle funzionalità cloud native integrate disponibili in Cosmos DB. In questa sezione, li esamineremo più da vicino.

### <a name="global-support"></a>Supporto globale

Le applicazioni native del cloud hanno spesso un pubblico globale e richiedono una scalabilità globale.

È possibile distribuire database Cosmos tra aree geografiche o in tutto il mondo, avvicinando i dati agli utenti, migliorando i tempi di risposta e riducendo la latenza. È possibile aggiungere o rimuovere un database da un'area senza sopperire o ridistribuire i servizi. In background, Cosmos DB replica in modo trasparente i dati in ciascuna delle regioni configurate.

Cosmos DB supporta il clustering [attivo/attivo](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) a livello globale, consentendo di configurare qualsiasi area di database per supportare *sia le scritture che le letture.*

Il protocollo [Multi-Master](https://docs.microsoft.com/azure/cosmos-db/multi-master-benefits) è una caratteristica importante di Cosmos DB che consente le seguenti funzionalità:

- Scalabilità di scrittura e lettura elastica illimitata.

- Disponibilità in lettura e scrittura pari al 99,999% in tutto il mondo.

- Letture e scritture gestite in meno di 10 millisecondi nel 99% dei casi.

Con le API Cosmos DB [Multi-Homing](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), il microservizio è automaticamente a conoscenza dell'area di Azure più vicina e invia le richieste. La regione più vicina è identificata da Cosmos DB senza alcuna modifica di configurazione. Se un'area non è più disponibile, la funzionalità Multi-Homing instrada automaticamente le richieste alla successiva area disponibile più vicina.

### <a name="multi-model-support"></a>Supporto multimodello

Quando si ripiattaforma applicazioni monolitiche a un'architettura cloud-native, i team di sviluppo a volte devono eseguire la migrazione di archivi dati NoSQL open-source. Cosmos DB può aiutarti a preservare il tuo investimento in questi datastore NoSQL con la sua piattaforma dati *multimodello.* Nella figura 5-13 sono illustrate le API di [compatibilità](https://www.wikiwand.com/en/Cosmos_DB)NoSQL supportate.

![Provider Cosmos DB](./media/cosmos-db-providers.png)

**Figura 5-13**: Provider Cosmos DB

I team di sviluppo possono eseguire la migrazione dei database Mongo, Gremlin o Cassandra esistenti in Cosmos DB con modifiche minime ai dati o al codice. Per le nuove app, i team di sviluppo possono scegliere tra opzioni open source o il modello di API SQL incorporato.

> Internamente, Cosmos archivia i dati in un formato struct semplice costituito da tipi di dati primitivi. Per ogni richiesta, il motore di database converte i dati primitivi nella rappresentazione del modello selezionata.

Nella figura precedente, 5-13, prendere nota dell'opzione [API tabella.](https://docs.microsoft.com/azure/cosmos-db/table-introduction) Questa API è un'evoluzione di Archiviazione tabelle di Azure.This API is an evolution of Azure Table Storage. Entrambi condividono lo stesso modello di tabella sottostante, ma l'API Cosmos DB Table aggiunge miglioramenti premium non disponibili nell'API di archiviazione di Azure.Both share the same underlying table model, but the Cosmos DB Table API adds premium enhancements not available in the Azure Storage API. Queste funzionalità sono contrapregistrate nella Figura 5-4.

![API Tabella di Azure](media/azure-table-api.png)

**Figura 5-14:** Provider di API delle tabelle di AzureFigure 5-14: Azure Table API Providers

I microservizi che utilizzano l'archiviazione tabelle di Azure possono eseguire facilmente la migrazione all'API Cosmos DB. Non sono necessarie modifiche al codice.

### <a name="tunable-consistency"></a>Coerenza regolabile

In precedenza nella sezione *relazionale e NoSQL* è stato illustrato l'argomento della coerenza dei *dati.* La coerenza dei dati si riferisce *all'integrità* dei dati. I servizi nativi cloud con dati distribuiti si basano sulla replica e devono creare un compromesso fondamentale tra coerenza di lettura, disponibilità e latenza.

La maggior parte dei database distribuiti consente agli sviluppatori di scegliere tra due modelli di coerenza: coerenza elevata ed eventuale coerenza. *Una forte coerenza* è il gold standard della programmabilità dei dati. Garantisce che una query restituisca sempre i dati più aggiornati, anche se il sistema deve incorrere in latenza in attesa che un aggiornamento venga replicato tra tutte le copie del database. Mentre un database configurato per *la coerenza finale* restituirà i dati immediatamente, anche se i dati non sono la copia più recente. Quest'ultima opzione consente una maggiore disponibilità, una maggiore scalabilità e prestazioni migliori.

Azure Cosmos DB offre cinque modelli di coerenza ben definiti illustrati nella Figura 5-15.Azure Cosmos DB offers five well-defined [consistency models](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) shown in Figure 5-15.

![Grafico della coerenza Cosmos DB](./media/cosmos-consistency-level-graph.png)

**Figura 5-15**: Livelli di coerenza di Cosmos DB

 Queste opzioni consentono di effettuare scelte precise e compromessi granulari per coerenza, disponibilità e prestazioni per i dati. Figura 5-16 descrive ogni livello.

![Livelli di coerenza di Cosmos DB](./media/cosmos-db-consistency-levels.png)

**Figura 5-16**: Cosmos DB Livello di coerenza Descrizione

Nell'articolo [Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/), Microsoft Cloud Developer Advocate Jeremy Likeness fornisce un'eccellente spiegazione dei cinque modelli.

### <a name="partitioning"></a>Partizionamento

Azure Cosmos DB adotta il [partizionamento](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) automatico per ridimensionare un database per soddisfare le esigenze di prestazioni dei servizi nativi del cloud.

I dati vengono gestiti nei dati Cosmos DB creando database, contenitori ed elementi.

I contenitori risiedono in un database Cosmos DB e rappresentano un raggruppamento di elementi indipendente dall'schema. Gli elementi sono i dati aggiunti al contenitore. Sono rappresentati come documenti, righe, nodi o bordi. Tutti gli elementi aggiunti a un contenitore vengono indicizzati automaticamente.

Per partizionare il contenitore, gli elementi vengono suddivisi in sottoinsiemi distinti denominati partizioni logiche. Le partizioni logiche vengono popolate in base al valore di una chiave di partizione associata a ogni elemento in un contenitore. Nella figura 5-18 sono illustrati due contenitori ciascuno con una partizione logica basata su un valore di chiave di partizione.

![Meccanica di partizionamento Cosmos DB](./media/cosmos-db-partitioning.png)

**Figura 5-18**: Meccanica di partizionamento di Cosmos DB

Si noti nella figura precedente come ogni elemento include una chiave di partizione di 'città' o 'aeroporto'. La chiave determina la partizione logica dell'elemento. Gli articoli con un codice di città vengono assegnati al contenitore a sinistra e gli articoli con un codice aeroportuale al contenitore a destra. La combinazione del valore della chiave di partizione con il valore ID crea l'indice di un elemento, che identifica in modo univoco l'elemento.

Internamente, Cosmos DB gestisce automaticamente il posizionamento delle [partizioni logiche](https://docs.microsoft.com/azure/cosmos-db/partition-data) nelle partizioni fisiche per soddisfare le esigenze di scalabilità e prestazioni del contenitore. Con l'aumento della velocità effettiva delle applicazioni e dei requisiti di archiviazione, Azure Cosmos DB ridistribuisce le partizioni logiche in un numero maggiore di server. Le operazioni di ridistribuzione sono gestite da Cosmos DB e richiamate senza interruzioni o tempi di inattività.

## <a name="newsql-databases"></a>Database NewSQL

*NewSQL* è una tecnologia di database emergente che combina la scalabilità distribuita di NoSQL con le garanzie ACID di un database relazionale. I database NewSQL sono importanti per i sistemi aziendali che devono elaborare volumi elevati di dati, in ambienti distribuiti, con supporto transazionale completo e conformità ACID. Sebbene un database NoSQL possa fornire scalabilità massiccia, non garantisce la coerenza dei dati. I problemi intermittenti derivanti da dati incoerenti possono comportare un onere per il team di sviluppo. Gli sviluppatori devono creare misure di sicurezza nel codice del microservizio per gestire i problemi causati da dati incoerenti.

La Cloud Native Computing Foundation (CNCF) presenta diversi progetti di database NewSQL.

| Project | Caratteristiche |
| :-------- | :-------- |
| Scarafaggio DB |Un database relazionale conforme a ACID che scala a livello globale. Aggiungere un nuovo nodo a un cluster e CockroachDB si occupa di bilanciare i dati tra istanze e aree geografiche. Crea, gestisce e distribuisce le repliche per garantire l'affidabilità. È open source e liberamente disponibile.  |
| Ordinatore di cose da parte | Database open source che supporta carichi di lavoro HTAP (Hybrid Transactional and Analytical Processing). È compatibile con MySQL e offre scalabilità orizzontale, forte coerenza e disponibilità elevata.  TiDB agisce come un server MySQL. È possibile continuare a utilizzare le librerie client MySQL esistenti, senza richiedere modifiche estese del codice all'applicazione. |
| JuribyteDB | Database SQL distribuito open source e ad alte prestazioni. Supporta una bassa latenza delle query, resilienza contro gli errori e la distribuzione globale dei dati. YugabyteDB è compatibile con PostgressSQL e gestisce i carichi di lavoro RDBMS con scalabilità orizzontale e OLTP su scala Internet. Il prodotto supporta anche NoSQL ed è compatibile con Cassandra. |
|Vitess | Vitess è una soluzione di database per la distribuzione, la scalabilità e la gestione di cluster di grandi dimensioni di istanze MySQL. Può essere eseguito in un'architettura di cloud pubblico o privato. Combina ed estende molte importanti funzionalità di MySQL e dispone di partizionamento orizzontale e verticale. Originato da YouTube, Vitess ha servito tutto il traffico del database di YouTube dal 2011 . |

I progetti open source nella figura precedente sono disponibili da Cloud Native Computing Foundation. Tre delle offerte sono prodotti di database completi, che includono il supporto .NET Core. L'altro, Vitess, è un sistema di clustering di database che scala orizzontalmente grandi cluster di istanze MySQL.

Un obiettivo di progettazione chiave per i database NewSQL è lavorare in modo nativo in Kubernetes, sfruttando la resilienza e la scalabilità della piattaforma.

I database NewSQL sono progettati per prosperare in ambienti cloud effimeri in cui le macchine virtuali sottostanti possono essere riavviate o riprogrammate in un momento di preavviso. I database sono progettati per sopravvivere agli errori dei nodi senza perdita di dati né tempi di inattività. CockroachDB, ad esempio, è in grado di sopravvivere a una perdita di macchina mantenendo tre repliche coerenti di tutti i dati tra i nodi di un cluster.

Kubernetes utilizza un *costrutto Services* per consentire a un client di indirizzare un gruppo di database NewSQL identici da una singola voce DNS. Disaccoppiando le istanze di database dall'indirizzo del servizio a cui è associato, è possibile scalare senza interrompere le istanze dell'applicazione esistenti. L'invio di una richiesta a qualsiasi servizio in un determinato momento produrrà sempre lo stesso risultato.

In questo scenario, tutte le istanze di database sono uguali. Non esistono relazioni primarie o secondarie. Tecniche come la replica di *consenso* trovata in CockroachDB consentono a qualsiasi nodo di database di gestire qualsiasi richiesta. Se il nodo che riceve una richiesta con carico bilanciato contiene i dati necessari in locale, risponde immediatamente. In caso contrario, il nodo diventa un gateway e inoltra la richiesta ai nodi appropriati per ottenere la risposta corretta. Dal punto di vista del client, ogni nodo di database è lo stesso: appaiono come un singolo database *logico* con le garanzie di coerenza di un sistema a computer singolo, pur avendo decine o addirittura centinaia di nodi che lavorano dietro le quinte.

Per un'analisi dettagliata dei meccanismi alla base dei database NewSQL, vedere l'articolo [DASH: Four Properties of Kubernetes-Native Databases](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/) .

## <a name="data-migration-to-the-cloud"></a>Migrazione dei dati nel cloud

Una delle attività più dispendiose in termini di tempo è la migrazione dei dati da una piattaforma dati a un'altra. Il [servizio migrazione dei dati](https://azure.microsoft.com/services/database-migration/) di Azure consente di velocizzare tali sforzi. Può eseguire la migrazione dei dati da diverse origini di database esterne in piattaforme di dati di Azure con tempi di inattività minimi. Le piattaforme di destinazione includono i seguenti servizi:

- database SQL di Azure
- Database di Azure per MySQL
- Database di Azure per MariaDB
- Database di Azure per PostgreSQL
- Cosmos DB
  
Il servizio fornisce suggerimenti per guidare l'utente attraverso le modifiche necessarie per eseguire una migrazione, piccola o grande.

>[!div class="step-by-step"]
>[Successivo](database-per-microservice.md)
>[precedente](azure-caching.md)
