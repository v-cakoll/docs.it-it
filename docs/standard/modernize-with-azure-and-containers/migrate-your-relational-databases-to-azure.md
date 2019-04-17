---
title: Eseguire la migrazione dei database relazionali in azure
description: Modernizzare le applicazioni .NET esistenti con Cloud di Azure e i contenitori di Windows | eseguire la migrazione dei database relazionali in azure
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 600c47b6b0ccaf704c8e7b638c759e990acaaacf
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611419"
---
# <a name="migrate-your-relational-databases-to-azure"></a>Eseguire la migrazione dei database relazionali in azure

Visione artificiale: Azure offre la più completa migrazione del database.

In Azure, è possibile eseguire la migrazione di server di database direttamente alle macchine virtuali IaaS (pure lift and -shift) oppure è possibile eseguire la migrazione al Database SQL di Azure per altri vantaggi. Database SQL di Azure offre opzioni di (DBaaS) completo del database-as-a-service e istanza gestita. Figura 3-1 mostra il database relazionale più percorsi di migrazione disponibili in Azure.

![Percorsi di migrazione di database in Azure](./media/image3-1.png)

> **Figura 3-1.** Percorsi di migrazione di database in Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Quando eseguire la migrazione a istanza gestita di Azure SQL Database

Nella maggior parte dei casi, istanza gestita di Azure SQL Database sarà la scelta migliore per prendere in considerazione quando si esegue la migrazione dei dati in Azure. Se si esegue la migrazione di database di SQL Server e quasi assurance 100% che non sarà necessario riprogettare l'applicazione o apportare modifiche ai dati o codice di accesso ai dati, scegliere la funzionalità istanza gestita di Database SQL di Azure.

Istanza gestita del Database SQL Azure è l'opzione migliore se si dispone di requisiti aggiuntivi per la funzionalità a livello di istanza di SQL Server o i requisiti di isolamento oltre le funzionalità fornite in un Database SQL di Azure standard (modello di database singolo). Quest'ultimo caso è la scelta più orientato su PaaS, ma non offre le stesse funzionalità di SQL server tradizionale. Migrazione potrebbe verificarsi conflitti.

Ad esempio, un'organizzazione che ha investito approfondito le funzionalità di SQL Server a livello di istanza possono trarre vantaggio dalla migrazione a istanza gestita di SQL. Esempi di funzionalità di SQL Server a livello di istanza sono SQL integrazione common language runtime (CLR), SQL Server Agent e l'esecuzione di query tra database. Supporto per queste funzionalità non è disponibile nel Database SQL di Azure standard (un modello single-database).

Un'organizzazione che opera in un settore con regolamentazione elevata e che deve mantenere l'isolamento per motivi di sicurezza, anche potrebbe trarre vantaggio dalla scelta del modello di istanza gestita di SQL.

Istanza gestita di Database SQL di Azure presenta le caratteristiche seguenti:

- Isolamento di sicurezza tramite la rete virtuale di Azure

- Superficie compatibilità delle applicazioni, grazie a queste funzionalità:

  - SQL Server Agent e SQL Server Profiler

  - Replica di SQL CLR, query e i riferimenti tra database, change data capture (CDC) e Service Broker

- Database con dimensioni fino a 35 TB

- Migrazione di tempo di inattività minimo, grazie a queste funzionalità:

  - Servizio migrazione del Database di Azure

  - Backup nativo e ripristino e il log shipping

Con queste funzionalità, quando si esegue la migrazione di database dell'applicazione esistente al Database SQL di Azure, il modello di istanza gestita offre quasi il 100% dei vantaggi di PaaS per SQL Server. Istanza gestita è un ambiente di SQL Server in cui si continuare a usare le funzionalità a livello di istanza senza modificare la progettazione dell'applicazione.

Istanza gestita è probabilmente la soluzione ottimale per le aziende che attualmente utilizzano SQL Server e che richiedono flessibilità per la sicurezza di rete nel cloud. È come avere una rete privata virtuale per i database SQL.

## <a name="when-to-migrate-to-azure-sql-database"></a>Quando eseguire la migrazione al Database SQL di Azure

Come accennato, il Database SQL di Azure standard è un DBaaS relazionale, completamente gestito. Database SQL gestisce attualmente milioni di database di produzione, in 38 Data Center, tutto il mondo. Supporta un'ampia gamma di applicazioni e carichi di lavoro, la gestione di semplici dati transazionali, per guidare le applicazioni più intensivo di dati di importanza critica che richiedono elaborazione avanzata dei dati su scala globale.

A causa delle relative funzionalità PaaS completa, prezzi migliori- e in ultima analisi costi-è necessario passare a Database SQL di Azure standard come la "scelta per impostazione predefinita" Se si dispone di un'applicazione che database SQL Usa basic, standard e nessuna funzionalità aggiuntive dell'istanza. Funzionalità di SQL Server, ad esempio l'integrazione con CLR SQL, SQL Server Agent e l'esecuzione di query tra database non sono supportate nel Database SQL di Azure standard. Tali funzionalità sono disponibili solo nel modello di istanza gestita di Azure SQL Database.

Database SQL di Azure è il servizio di database cloud intelligente solo che è stato compilato per gli sviluppatori di app. È anche l'unico servizio di database cloud con scalabilità in lettura al volo, senza tempi di inattività, che consentono di distribuire in modo efficiente le app multi-tenant. In definitiva, Database SQL di Azure rende più tempo per innovare e consente di accelerare la fase di immissione sul mercato. È possibile compilare App sicure e connettersi al database SQL di mediante i linguaggi e piattaforme che preferisci.

Database SQL di Azure offre i vantaggi seguenti:

- Funzionalità di intelligence integrata (apprendimento) che apprende e si adatta all'App

- Il provisioning del database su richiesta

- Una gamma di offerte, per tutti i carichi di lavoro

- disponibilità del 99,99% contratto di servizio, senza necessità di manutenzione

- Servizi di ripristino e la replica geografica per la protezione dati

- Punto di Database SQL di Azure nelle funzionalità Ripristino temporizzato

- Compatibilità con SQL Server 2016, tra cui distribuzione ibrida e migrazione

Il Database SQL di Azure standard è più simile a PaaS a istanza gestita di Azure SQL Database. Preferisce il Database SQL di Azure standard perché potrai ulteriori vantaggi da un cloud gestito. Tuttavia, Database SQL di Azure con alcune differenze importanti da regolare e istanze di SQL Server locale. A seconda di requisiti del database dell'applicazione esistente e i requisiti aziendali e i criteri, potrebbe non essere la scelta migliore quando si pianifica la migrazione al cloud.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Casi in cui spostare il sistema RDBMS originale a una macchina virtuale (IaaS)

Una delle opzioni di migrazione consiste nello spostamento l'originale sistema di gestione di database relazionali (RDBMS), tra cui Oracle, IBM DB2, MySQL, PostgreSQL o SQL Server, a un server simile che è in esecuzione in una VM di Azure. Se sono presenti applicazioni che richiedono la migrazione al cloud con modifiche minime o nessuna modifica più veloce del tutto, migrazione diretta da IaaS nel cloud è un'opzione equa. Potrebbe non essere il modo migliore per sfruttare i vantaggi del cloud, ma è probabile che il percorso iniziale più rapido.

Microsoft Azure supporta attualmente fino a [331 server di database differenti](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) distribuite come macchine virtuali IaaS. Sono inclusi RDBMS più diffusi, ad esempio SQL Server, Oracle, MySQL, PostgreSQL e IBM DB2 e molti altri database NoSQL come MongoDB, Cassandra, DataStax, MariaDB e Cloudera.

> [!NOTE]
> Sebbene lo spostamento di RDBMS per una macchina virtuale di Azure potrebbe essere il modo più rapido per la migrazione dei dati nel cloud (perché si tratta di IaaS), questo approccio richiede un investimento significativo nei team IT (gli amministratori di database e i professionisti IT). I team aziendali devono essere in grado di configurare e gestire la disponibilità elevata, ripristino di emergenza e l'applicazione di patch per SQL Server. In questo contesto è necessario anche un ambiente personalizzato, con diritti amministrativi completi.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Quando eseguire la migrazione a SQL Server come macchina virtuale (IaaS)

Potrebbero essere presenti alcuni casi in cui è ancora necessario eseguire la migrazione a SQL Server come una normale VM. Uno scenario di esempio è se è necessario utilizzare SQL Server Reporting Services. Nella maggior parte dei casi, tuttavia, istanza gestita di Azure SQL Database può fornire tutto il che necessario per eseguire la migrazione dal server di SQL Server in locale, in modo che la migrazione a una VM SQL Server deve essere l'ultima risorsa provare.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Usare servizio migrazione del Database di Azure per eseguire la migrazione dei database relazionali in Azure 

È possibile usare servizio migrazione del Database di Azure per eseguire la migrazione di database relazionali come SQL Server, Oracle e MySQL in Azure, se il database di destinazione è il Database SQL di Azure, istanza gestita di Database di Azure SQL o SQL Server in una VM di Azure.

Il flusso di lavoro automatizzato, con la segnalazione della valutazione, descrive le modifiche da apportare prima della migrazione del database. Quando si è pronti, il servizio esegue la migrazione di database di origine in Azure.

Ogni volta che si modifica un RDBMS originale, si potrebbe essere necessario testare nuovamente. È anche necessario modificare il codice di Object-Relational Mapping (ORM) nell'applicazione, in base ai risultati dei test o le frasi SQL.

Se si dispone di qualsiasi altro database (ad esempio, IBM DB2) e non si scelga un approccio in modalità lift- and -shift, si potrebbe voler continuare a usare tali database come macchine virtuali IaaS in Azure, a meno che non si è disposti a eseguire la migrazione dei dati più complessa. Una migrazione dei dati più complessa richiederanno un impegno aggiuntivo in quanto si sarebbe la migrazione a un tipo di database diverso con nuovo schema e le librerie di programmazione diversi.

Per informazioni su come eseguire la migrazione di database usando servizio migrazione del Database di Azure, vedere [Introduzione al cloud più rapidamente con servizio migrazione del Database e istanza gestita di Azure SQL Database](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Risorse aggiuntive

- **Scegliere un'opzione di SQL Server cloud: Database SQL di Azure (PaaS) o SQL Server in macchine Virtuali di Azure (IaaS)**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **Introduzione al cloud più veloce con istanza gestita di Azure SQL DB e il servizio migrazione del Database**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **Migrazione di un database SQL Server al database SQL nel cloud**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Database SQL di Azure**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **SQL Server in macchine virtuali**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [Precedente](lift-and-shift-existing-apps-azure-iaas.md)
> [Successivo](modernize-existing-apps-to-cloud-optimized/index.md)
