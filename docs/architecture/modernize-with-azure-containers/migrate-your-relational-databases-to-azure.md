---
title: Eseguire la migrazione dei database relazionali in azureMigrate your relational databases to azure
description: Modernizza le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows eseguire la migrazione dei database relazionali in azure
ms.date: 04/28/2018
ms.openlocfilehash: efd1548c3f74fc27450f4949d71a1c4d61907ba5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73093619"
---
# <a name="migrate-your-relational-databases-to-azure"></a>Eseguire la migrazione dei database relazionali in azureMigrate your relational databases to azure

Visione: Azure offre la migrazione del database più completa.

In Azure è possibile eseguire la migrazione dei server di database direttamente alle macchine virtuali IaaS (passaggio e spostamento pura) oppure eseguire la migrazione al database SQL di Azure per ulteriori vantaggi. Il database SQL di Azure offre opzioni di istanza gestita e di database come servizio (DBaaS) completo. Nella figura 3-1 sono illustrati i percorsi di migrazione di più database relazionali disponibili in Azure.

![Database migration paths in Azure](./media/image3-1.png)

**Figura 3-1.** Database migration paths in Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Quando eseguire la migrazione all'istanza gestita del database SQL di AzureWhen to migrate to Azure SQL Database Managed Instance

In most cases, Azure SQL Database Managed Instance will be your best option to consider when you migrate your data to Azure. Se si esegue la migrazione dei database di SQL Server ed è necessaria quasi al 100% la certezza di non dover riprogettare l'applicazione o apportare modifiche ai dati o al codice di accesso ai dati, scegliere la funzionalità Istanza gestita del database SQL di Azure.If you are migrating SQL Server databases and need quasi 100% assurance that you won't need to rearchitect your application or make changes to your data or data access code, choose the Managed Instance feature of Azure SQL Database.

Istanza gestita database SQL di Azure è l'opzione migliore se si dispone di requisiti aggiuntivi per la funzionalità a livello di istanza di SQL Server o requisiti di isolamento oltre alle funzionalità fornite in un database SQL di Azure standard (modello di database singolo). Quest'ultima è la scelta più orientata a PaaS, ma non offre le stesse funzionalità di un server SQL tradizionale. La migrazione potrebbe causare attriti.

Ad esempio, un'organizzazione che ha effettuato investimenti approfonditi nelle funzionalità di SQL Server a livello di istanza trarrebbe vantaggio dalla migrazione all'istanza gestita SQL. Esempi di funzionalità di SQL Server a livello di istanza includono l'integrazione di SQL Common Language Runtime (CLR), SQL Server Agent e l'esecuzione di query tra database. Il supporto per queste funzionalità non è disponibile nel database SQL di Azure standard (un modello a database singolo).

Un'organizzazione che opera in un settore altamente regolamentato e che deve mantenere l'isolamento per motivi di sicurezza, potrebbe anche trarre vantaggio dalla scelta del modello di istanza gestita SQL.

L'istanza gestita nel database SQL di Azure presenta le caratteristiche seguenti:Managed Instance in Azure SQL Database has the following characteristics:

- Isolamento della sicurezza tramite la rete virtuale di AzureSecurity isolation through Azure Virtual Network

- Compatibilità della superficie dell'applicazione, con queste caratteristiche:Application surface compatibility, with these features:

  - Agente SQL Server e SQL Server Profiler

  - Riferimenti e query tra database, CLR SQL, replica, Change Data Capture (CDC) e Service Broker

- Dimensioni del database fino a 35 TB

- Migrazione del tempo di inattività minimo, con le seguenti funzionalità:

  - Servizio Migrazione del database di Azure

  - Backup e ripristino nativi e distribuzione dei log

Con queste funzionalità, quando si esegue la migrazione dei database dell'applicazione esistenti al database SQL di Azure, il modello di istanza gestita offre quasi il 100% dei vantaggi di PaaS per SQL Server. Istanza gestita è un ambiente SQL Server in cui si continua a utilizzare le funzionalità a livello di istanza senza modificare la progettazione dell'applicazione.

Istanza gestita è probabilmente la soluzione migliore per le aziende che attualmente utilizzano SQL Server e che richiedono flessibilità nella sicurezza di rete nel cloud. È come avere una rete virtuale privata per i database SQL.

## <a name="when-to-migrate-to-azure-sql-database"></a>Quando eseguire la migrazione al database SQL di AzureWhen to migrate to Azure SQL Database

Come accennato in precedenza, il database SQL di Azure standard è un DBaaS relazionale completamente gestito. Il database SQL gestisce attualmente milioni di database di produzione, in 38 data center, in tutto il mondo. Supporta un'ampia gamma di applicazioni e carichi di lavoro, dalla gestione di dati transazionali semplici, alla guida delle applicazioni mission-critical più ad alta intensità di dati che richiedono un'elaborazione avanzata dei dati su scala globale.

A causa delle sue funzionalità PaaS complete, è consigliabile passare al database SQL di Azure standard come "scelta predefinita" se si dispone di un'applicazione che usa database SQL standard di base e non altre funzionalità di istanza. Le funzionalità di SQL Server come l'integrazione CLR SQL, Agente SQL Server e l'esecuzione di query tra database non sono supportate nel database SQL di Azure standard. Tali funzionalità sono disponibili solo nel modello di istanza gestita del database SQL di Azure.Those features are available only in the Azure SQL Database Managed Instance model.

Il database SQL di Azure è l'unico servizio di database cloud intelligente creato per gli sviluppatori di app. È anche l'unico servizio di database cloud scalabile in tempo reale, senza tempi di inattività, per aiutarti a distribuire in modo efficiente le app multi-tenant. In definitiva, il database SQL di Azure lascia più tempo per innovare e accelera il time-to-market. È possibile creare app sicure e connettersi al database SQL usando le lingue e le piattaforme preferite.

Il database SQL di Azure offre i vantaggi seguenti:Azure SQL Database offers the following benefits:

- Intelligenza integrata (apprendimento automatico) che apprende e si adatta alla tua app

- Provisioning di database su richiesta

- Una gamma di offerte, per tutti i carichi di lavoro

- Contratto di servizio per la disponibilità del 99,99%, zero manutenzione

- Servizi di replica geografica e ripristino per la protezione dei dati

- Funzionalità di ripristino temporizzato Azure SQL Database Point in Time

- Compatibilità con SQL Server 2016, inclusi immigrazione e ibrido

Il database SQL di Azure standard è più vicino a PaaS rispetto all'istanza gestita del database SQL di Azure.The standard Azure SQL Database is closer to PaaS than Azure SQL Database Managed Instance. Preferisci il database SQL di Azure standard perché otterrai maggiori vantaggi da un cloud gestito. Tuttavia, il database SQL di Azure presenta alcune differenze fondamentali rispetto alle istanze normali e locali di SQL Server.However, Azure SQL Database has some key differences from regular and on-premises SQL Server instances. A seconda dei requisiti del database dell'applicazione esistente e dei requisiti e dei criteri aziendali, potrebbe non essere la scelta migliore quando si pianifica la migrazione al cloud.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Quando spostare il sistema RDBMS originale in una macchina virtuale (IaaS)When to move your original RDBMS to a VM (IaaS)

Una delle opzioni di migrazione consiste nello spostare il sistema di gestione di database relazionali (RDBMS) originale, inclusi Oracle, IBM DB2, MySQL, PostgreSQL o SQL Server, in un server simile in esecuzione in una macchina virtuale di Azure.One of your migration options is to move your original relational database management system (RDBMS), including Oracle, IBM DB2, MySQL, PostgreSQL, or SQL Server, to a similar server that's running on an Azure VM. Se si dispone di applicazioni esistenti che richiedono la migrazione più rapida al cloud con modifiche minime o nessuna modifica, una migrazione diretta a IaaS nel cloud potrebbe essere un'opzione equa. Potrebbe non essere il modo migliore per sfruttare tutti i vantaggi del cloud, ma è probabilmente il percorso iniziale più veloce.

Attualmente, Microsoft Azure supporta fino a 331 server di database diversi distribuiti come macchine virtuali IaaS.Currently, Microsoft Azure supports up to [331 different](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) database servers deployed as IaaS VMs. Questi includono RDBMS popolari come SQL Server, Oracle, MySQL, PostgreSQL e IBM DB2 e molti altri database NoSQL come MongoDB, Cassandra, DataStax, MariaDB e Cloudera.

> [!NOTE]
> Anche se lo spostamento del sistema RDBMS in una macchina virtuale di Azure potrebbe essere il modo più rapido per eseguire la migrazione dei dati nel cloud (perché è IaaS), questo approccio richiede un investimento significativo nei team IT (amministratori di database e professionisti IT). I team aziendali devono essere in grado di configurare e gestire la disponibilità elevata, il ripristino di emergenza e l'applicazione di patch per SQL Server.Enterprise teams need to be able to set up and manage high availability, disaster recovery, and patching for SQL Server. Questo contesto richiede anche un ambiente personalizzato, con diritti amministrativi completi.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Quando eseguire la migrazione a SQL Server come macchina virtuale (IaaS)When to migrate to SQL Server as a VM (IaaS)

Potrebbero verificarsi alcuni casi in cui è ancora necessario eseguire la migrazione a SQL Server come una normale macchina virtuale. Uno scenario di esempio è se è necessario utilizzare SQL Server Reporting Services.An example scenario is if you need to use SQL Server Reporting Services. Nella maggior parte dei casi, tuttavia, l'istanza gestita del database SQL di Azure può fornire tutto il necessario per eseguire la migrazione da server SQL locali, pertanto la migrazione a una macchina virtuale di SQL Server deve essere l'ultima risorsa da provare.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Usare il servizio di migrazione del database di Azure per eseguire la migrazione dei database relazionali in AzureUse Azure Database Migration Service to migrate your relational databases to Azure

È possibile usare il servizio di migrazione del database di Azure per eseguire la migrazione di database relazionali come SQL Server, Oracle e MySQL in Azure, indipendentemente dal fatto che il database di destinazione sia Database SQL di Azure, Istanza gestita database SQL di Azure o SQL Server in una macchina virtuale di Azure.You can use Azure Database Migration Service to migrate relational databases like SQL Server, Oracle, and MySQL to Azure, whether your target database is Azure SQL Database, Azure SQL Database Managed Instance, or SQL Server on an Azure VM.

Il flusso di lavoro automatizzato, con report di valutazione, guida l'utente attraverso le modifiche che è necessario apportare prima di eseguire la migrazione del database. Quando si è pronti, il servizio esegue la migrazione del database di origine in Azure.When you are ready, the service migrates the source database to Azure.

Ogni volta che si modifica un rDBMS originale, potrebbe essere necessario eseguire nuovamente il test. Potrebbe anche essere necessario modificare le frasi SQL o il codice ORM (Object-Relational Mapping) nell'applicazione, a seconda dei risultati del test.

Se si dispone di qualsiasi altro database (ad esempio, IBM DB2) e si opta per un approccio lift and shift, è possibile continuare a usare tali database come macchine virtuali IaaS in Azure, a meno che non si sia disposti a eseguire una migrazione dei dati più complessa. Una migrazione dei dati più complessa richiederà uno sforzo aggiuntivo perché si sta eseguendo la migrazione a un tipo di database diverso con nuovo schema e librerie di programmazione diverse.

Per informazioni su come eseguire la migrazione dei database tramite il servizio di migrazione del database di Azure, vedere [Ottenere nel cloud più velocemente con l'istanza gestita del database SQL](https://channel9.msdn.com/Events/Build/2017/P4008)di Azure e il servizio migrazione del database di Azure.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Scegliere un'opzione cloud di SQL Server: Database SQL di Azure (PaaS) o SQL Server in VM di Azure (IaaS)Choose a cloud SQL Server option: Azure SQL Database (PaaS) or SQL Server on Azure VM (IaaS)**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **Ottieni rapidamente nel cloud con l'istanza gestita del database SQL di Azure e il servizio di migrazione del database**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **Migrazione di un database SQL Server al database SQL nel cloud**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Database SQL di Azure**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **SQL Server in macchine virtuali**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [Successivo](lift-and-shift-existing-apps-azure-iaas.md)
> [precedente](modernize-existing-apps-to-cloud-optimized/index.md) <!-- Next Chapter -->
