---
title: Eseguire la migrazione dei database relazionali in Azure
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | eseguire la migrazione dei database relazionali in Azure
ms.date: 04/28/2018
ms.openlocfilehash: 3d4f03e61144bb6a442a50916d7fd024d38ec611
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578374"
---
# <a name="migrate-your-relational-databases-to-azure"></a>Eseguire la migrazione dei database relazionali in Azure

Obiettivo: Azure offre la migrazione più completa del database.

In Azure è possibile eseguire la migrazione dei server di database direttamente alle macchine virtuali IaaS (Lift-and-Shift puri) oppure è possibile eseguire la migrazione al database SQL di Azure per altri vantaggi. Il database SQL di Azure offre opzioni di istanza gestita e database completo come servizio (DBaaS). La figura 3-1 Mostra i percorsi di migrazione di database relazionali multipli disponibili in Azure.

![Percorsi di migrazione del database in Azure](./media/image3-1.png)

> **Figura 3-1.** Percorsi di migrazione del database in Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Quando eseguire la migrazione a Istanza gestita di database SQL di Azure

Nella maggior parte dei casi, Istanza gestita di database SQL di Azure sarà l'opzione migliore da considerare quando si esegue la migrazione dei dati in Azure. Se si esegue la migrazione di database di SQL Server e si ha bisogno di circa il 100% di garanzia che non sarà necessario riprogettare l'applicazione o apportare modifiche ai dati o al codice di accesso ai dati, scegliere la funzionalità Istanza gestita del database SQL di Azure.

Istanza gestita di database SQL di Azure è l'opzione migliore se si hanno requisiti aggiuntivi per SQL Server funzionalità a livello di istanza o requisiti di isolamento oltre alle funzionalità disponibili in un database SQL di Azure standard (modello di database singolo). Questa ultima è la scelta più orientata a PaaS, ma non offre le stesse funzionalità di un SQL Server tradizionale. La migrazione può comportare attriti.

Ad esempio, un'organizzazione che ha effettuato investimenti profondi nelle funzionalità SQL Server a livello di istanza può trarre vantaggio dalla migrazione a SQL Istanza gestita. Esempi di funzionalità di SQL Server a livello di istanza includono l'integrazione di SQL Common Language Runtime (CLR), SQL Server Agent e l'esecuzione di query tra database. Il supporto per queste funzionalità non è disponibile nel database SQL di Azure standard (un modello a database singolo).

Un'organizzazione che opera in un settore altamente regolamentato e che deve mantenere l'isolamento per motivi di sicurezza può anche trarre vantaggio dalla scelta del modello di Istanza gestita SQL.

Istanza gestita nel database SQL di Azure presenta le caratteristiche seguenti:

- Isolamento della sicurezza tramite la rete virtuale di Azure

- Compatibilità della superficie dell'applicazione con queste funzionalità:

  - SQL Server Agent e SQL Server Profiler

  - Riferimenti e query tra database, CLR SQL, replica, Change Data Capture (CDC) e Service Broker

- Dimensioni database fino a 35 TB

- Migrazione del tempo di inattività minimo con queste funzionalità:

  - Servizio migrazione del database di Azure

  - Backup e ripristino nativi e log shipping

Con queste funzionalità, quando si esegue la migrazione dei database delle applicazioni esistenti al database SQL di Azure, il modello di Istanza gestita offre quasi il 100% dei vantaggi di PaaS per SQL Server. Istanza gestita è un ambiente SQL Server in cui si continua a utilizzare le funzionalità a livello di istanza senza modificare la progettazione dell'applicazione.

Istanza gestita è probabilmente la soluzione migliore per le aziende che attualmente usano SQL Server e che richiedono flessibilità nella sicurezza di rete nel cloud. È come avere una rete virtuale privata per i database SQL.

## <a name="when-to-migrate-to-azure-sql-database"></a>Quando eseguire la migrazione al database SQL di Azure

Come indicato in precedenza, il database SQL di Azure standard è un DBaaS relazionale completamente gestito. Il database SQL gestisce attualmente milioni di database di produzione, in tutti i Data Center 38, in tutto il mondo. Supporta un'ampia gamma di applicazioni e carichi di lavoro, dalla gestione di dati transazionali semplici, alla guida delle applicazioni cruciali con maggiore utilizzo di dati, che richiedono l'elaborazione avanzata dei dati su scala globale.

Grazie alle funzionalità complete di PaaS, ai prezzi migliori e in definitiva al costo inferiore, è consigliabile passare al database SQL di Azure standard come scelta predefinita se si dispone di un'applicazione che usa database SQL di base, standard e senza altre funzionalità dell'istanza. SQL Server funzionalità quali l'integrazione con CLR SQL, SQL Server Agent e l'esecuzione di query tra database non sono supportate nel database SQL di Azure standard. Queste funzionalità sono disponibili solo nel modello di Istanza gestita di database SQL di Azure.

Il database SQL di Azure è l'unico servizio di database cloud intelligente creato per gli sviluppatori di app. È anche l'unico servizio di database cloud che offre scalabilità immediata, senza tempi di inattività, per consentire di distribuire in modo efficiente le app multi-tenant. Infine, il database SQL di Azure lascia più tempo per l'innovazione e accelera il time-to-Market. Puoi creare app sicure e connetterle al database SQL usando i linguaggi e le piattaforme che preferisci.

Il database SQL di Azure offre i vantaggi seguenti:

- Intelligence integrata (Machine Learning) che apprende e si adatta all'app

- Provisioning di database su richiesta

- Una gamma di offerte, per tutti i carichi di lavoro

- CONTRATTO di disponibilità del 99,99%, manutenzione zero

- Servizi di replica geografica e ripristino per la protezione dei dati

- Funzionalità di ripristino temporizzato del database SQL di Azure

- Compatibilità con SQL Server 2016, tra cui ibrido e migrazione

Il database SQL di Azure standard è più vicino a PaaS rispetto a Istanza gestita di database SQL di Azure. Preferisci il database SQL di Azure standard perché otterrai più vantaggi da un cloud gestito. Tuttavia, il database SQL di Azure presenta alcune differenze principali rispetto alle istanze di SQL Server regolari e locali. A seconda dei requisiti del database dell'applicazione esistente e dei criteri e dei requisiti aziendali, potrebbe non essere la scelta migliore quando si pianifica la migrazione al cloud.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Quando spostare il RDBMS originale in una macchina virtuale (IaaS)

Una delle opzioni di migrazione prevede lo spostamento del sistema di gestione di database relazionali (RDBMS) originale, inclusi Oracle, IBM DB2, MySQL, PostgreSQL o SQL Server, in un server simile in esecuzione in una macchina virtuale di Azure. Se si dispone di applicazioni esistenti che richiedono la migrazione più veloce al cloud con modifiche minime o senza alcuna modifica, una migrazione diretta a IaaS nel cloud potrebbe essere un'opzione corretta. Potrebbe non essere il modo migliore per sfruttare tutti i vantaggi del cloud, ma è probabilmente il percorso iniziale più rapido.

Attualmente, Microsoft Azure supporta fino a [331 server di database diversi](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) distribuiti come VM IaaS. Sono inclusi gli RDBMS più diffusi, come SQL Server, Oracle, MySQL, PostgreSQL e IBM DB2, e molti altri database NoSQL come MongoDB, Cassandra, DataStax, MariaDB e Cloudera.

> [!NOTE]
> Anche se lo spostare il RDBMS in una macchina virtuale di Azure potrebbe essere il modo più rapido per eseguire la migrazione dei dati nel cloud (perché è IaaS), questo approccio richiede un investimento significativo nei team IT (amministratori di database e professionisti IT). I team aziendali devono essere in grado di configurare e gestire la disponibilità elevata, il ripristino di emergenza e l'applicazione di patch per SQL Server. Questo contesto richiede anche un ambiente personalizzato con diritti amministrativi completi.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Quando eseguire la migrazione a SQL Server come macchina virtuale (IaaS)

Potrebbero esserci alcuni casi in cui è ancora necessario eseguire la migrazione a SQL Server come una normale macchina virtuale. Uno scenario di esempio è se è necessario usare SQL Server Reporting Services. Nella maggior parte dei casi, tuttavia, Istanza gestita di database SQL di Azure possibile fornire tutto il necessario per eseguire la migrazione da server SQL locali, quindi la migrazione a una macchina virtuale SQL Server dovrebbe essere l'ultima risorsa da provare.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Usare il servizio migrazione del database di Azure per eseguire la migrazione dei database relazionali in Azure 

È possibile usare il servizio migrazione del database di Azure per eseguire la migrazione di database relazionali come SQL Server, Oracle e MySQL in Azure, indipendentemente dal fatto che il database di destinazione sia database SQL di Azure, Istanza gestita di database SQL di Azure o SQL Server in una macchina virtuale di Azure.

Il flusso di lavoro automatizzato, con la creazione di report di valutazione, guida l'utente nelle modifiche che è necessario eseguire prima di eseguire la migrazione del database. Quando si è pronti, il servizio esegue la migrazione del database di origine in Azure.

Ogni volta che si modifica un RDBMS originale, potrebbe essere necessario eseguire nuovamente il test. Potrebbe anche essere necessario modificare le frasi SQL o il codice ORM (Object-Relational Mapping) nell'applicazione, a seconda dei risultati del test.

Se si dispone di un altro database, ad esempio IBM DB2, e si opta per un approccio Lift-and-Shift, potrebbe essere necessario continuare a usare tali database come macchine virtuali IaaS in Azure, a meno che non si sia disposti a eseguire una migrazione dei dati più complessa. Una migrazione dei dati più complessa richiederà ulteriore sforzo perché si eseguirà la migrazione a un tipo di database diverso con nuovo schema e librerie di programmazione diverse.

Per informazioni su come eseguire la migrazione dei database con il servizio migrazione del database di Azure, vedere la pagina relativa [alla migrazione rapida al cloud con istanza gestita di database SQL di Azure e il servizio migrazione del database di Azure](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Risorse aggiuntive

- **Scegliere un'opzione di SQL Server Cloud: Database SQL di Azure (PaaS) o SQL Server in una macchina virtuale di Azure (IaaS)**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **È possibile raggiungere il cloud più velocemente con il database SQL di Azure Istanza gestita e il servizio migrazione del database**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **Migrazione di un database SQL Server al database SQL nel cloud**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Database SQL di Azure**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **SQL Server sulle macchine virtuali**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [Precedente](lift-and-shift-existing-apps-azure-iaas.md)
> [Successivo](modernize-existing-apps-to-cloud-optimized/index.md)
