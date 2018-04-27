---
title: La migrazione di database relazionali in azure
description: Modernizzare le applicazioni .NET esistenti con Cloud di Azure e i contenitori di Windows | la migrazione di database relazionali in azure
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: aa23d525c80d02ae19783a32f197a412276db36e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="migrate-your-relational-databases-to-azure"></a>La migrazione di database relazionali in azure

Visione: Azure offre la migrazione del database più completa.

In Azure, è possibile eseguire la migrazione di server di database direttamente alle macchine virtuali IaaS (accuratezza pura e MAIUSC) oppure è possibile eseguire la migrazione al Database di SQL Azure, per ulteriori vantaggi. Database SQL di Azure offre opzioni (DBaaS) completo del database-as-a-service e istanza gestita. Figura 3-1 viene illustrato il database relazionale più percorsi di migrazione disponibili in Azure.

![Percorsi di migrazione di database in Azure](./media/image3-1.png)

> **Figura 3-1.** Percorsi di migrazione di database in Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Quando eseguire la migrazione per istanza gestita di Azure SQL Database

Nella maggior parte dei casi, l'istanza gestita di Azure SQL Database sarà la migliore opzione da considerare quando si esegue la migrazione dei dati in Azure. Se si esegue la migrazione di database di SQL Server ed è necessario quasi garanzia 100% che non è necessario riprogettare l'applicazione o apportare modifiche ai dati o un codice di accesso ai dati, scegliere la funzionalità istanza gestita di Database SQL di Azure.

Istanza gestita del Database SQL Azure è la scelta migliore se si dispone di ulteriori requisiti per funzionalità a livello di istanza di SQL Server o i requisiti di isolamento oltre le funzionalità disponibili in un Database SQL di Azure standard (singolo modello di database). In questo ultimo è la scelta più orientati PaaS, ma non offre le stesse funzionalità di SQL server tradizionale. Migrazione potrebbe superficie frictions.

Ad esempio, un'organizzazione che ha apportato complete investimenti nella funzionalità di SQL Server a livello di istanza può costituire un vantaggio dalla migrazione per istanza gestita di SQL. Esempi di funzionalità di SQL Server a livello di istanza sono SQL integrazione common language runtime (CLR), SQL Server Agent e l'esecuzione di query tra database. Supporto per queste funzionalità non sono disponibili nel Database SQL di Azure standard (modello di un singolo database).

Un'organizzazione che funziona in un settore altamente regolamentato, e che necessitano di mantenere l'isolamento per motivi di sicurezza, anche potrà trarre vantaggio dalla scelta del modello di istanza gestita di SQL.

Istanza gestita nel Database di SQL Azure presenta le caratteristiche seguenti:

- Isolamento di sicurezza attraverso la rete virtuale di Azure

- Superficie di attacco compatibilità, grazie a queste funzionalità:

  - SQL Server Profiler e SQL Server Agent

  - Replica di query, CLR SQL e i riferimenti tra database, change data capture (CDC) e Service Broker

- Database di dimensioni fino a 35 TB

- Migrazione del tempo di inattività minimo, con queste caratteristiche:

  - Servizio di migrazione di Database di Azure

  - Native backup e ripristino e il log shipping

Con queste funzionalità, quando si esegue la migrazione di database dell'applicazione esistente al Database di SQL Azure, il modello di istanza gestita offre quasi il 100% dei vantaggi di Paas per SQL Server. Istanza gestita è un ambiente di SQL Server in cui continuare a usare le funzionalità a livello di istanza senza modificare la progettazione dell'applicazione.

Istanza gestita è probabilmente la scelta migliore per le aziende che attualmente utilizzano SQL Server e che richiedono flessibilità per la sicurezza di rete nel cloud. È ad esempio disporre di una rete privata virtuale per i database SQL.

## <a name="when-to-migrate-to-azure-sql-database"></a>Quando eseguire la migrazione di Database SQL di Azure

Come indicato, il Database SQL di Azure standard è un DBaaS relazionale e completamente gestito. Database SQL attualmente gestisce milioni di database di produzione, in data 38 Center, tutto il mondo. Supporta un'ampia gamma di applicazioni e carichi di lavoro, la gestione dei dati transazionali semplici, per gestire le applicazioni più dati impegnativa in termini di importanza critica che richiedono l'elaborazione dati avanzata in una scala globale.

A causa delle relative funzionalità PaaS completa e una migliore prezzi- e anche di ridurre i costi, è consigliabile spostare al database SQL di Azure standard come "per impostazione predefinita prescelto" Se si dispone di un'applicazione che usa basic, standard, i database SQL e nessuna funzionalità aggiuntive dell'istanza. Funzionalità di SQL Server come integrazione CLR di SQL, SQL Server Agent e l'esecuzione di query tra database non sono supportate in Database SQL di Azure standard. Tali funzionalità sono disponibili solo nel modello di istanza gestita di Azure SQL Database.

Database SQL di Azure è il servizio di database cloud solo intelligente che è stato compilato per sviluppatori dell'applicazione. È anche l'unico servizio di database cloud che viene ridimensionata in immediatamente, senza tempi di inattività, che consentono di distribuire in modo efficiente App multi-tenant. Infine, Database SQL di Azure lascia innovazione più tempo e accelerano i tempi sul mercato. È possibile compilare applicazioni protette e connettersi al database SQL tramite i linguaggi e piattaforme di cui si preferiscono.

Database SQL di Azure offre i vantaggi seguenti:

- Intelligenti (apprendimento) che apprende e si adatta all'App

- Provisioning del database su richiesta

- Una serie di offerte, per tutti i carichi di lavoro

- disponibilità del 99,99% contratto di servizio, zero manutenzione

- Servizi di ripristino e la replica geografica per la protezione dati

- Punto di Database SQL di Azure nella funzionalità Ripristino temporizzato

- Compatibilità con SQL Server 2016, inclusi ibrida e migrazione

Il Database SQL di Azure standard è inferiore a PaaS di istanza gestita di Azure SQL Database. È consigliabile utilizzarlo, se possibile, perché viene visualizzato da un cloud gestito ulteriori vantaggi. Tuttavia, il Database di SQL Azure presenta alcune differenze fondamentali normali e istanze di SQL Server locale. A seconda di requisiti del database dell'applicazione esistente e i requisiti dell'organizzazione e i criteri, che non sia la scelta migliore quando si pianifica la migrazione al cloud.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Quando spostare il RDBMS originale a una macchina virtuale (IaaS)

Una delle opzioni di migrazione consiste nello spostare l'originale sistema di gestione di database relazionali (RDBMS), inclusi IBM DB2, Oracle, MySQL, PostgreSQL o SQL Server, a un server simile che è in esecuzione in una macchina virtuale di Azure. Se si dispone di applicazioni che richiedono la migrazione al cloud con modifiche minime o nessuna modifica più veloce del tutto, la migrazione diretta a IaaS nel cloud potrebbe essere un'opzione equo. Potrebbe non essere il modo migliore per sfruttare i vantaggi del cloud, ma è probabile che il percorso iniziale più veloce.

Attualmente, Microsoft Azure supporta fino a [331 server di database differenti](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) distribuito come macchine virtuali IaaS. Questi includono RDBMSes diffusi come SQL Server, Oracle, MySQL, PostgreSQL e IBM DB2 e molti altri database NoSQL come MongoDB, Cassandra, DataStax, MariaDB e Cloudera.

> [!NOTE]
> Sebbene sia il sistema RDBMS per una macchina virtuale di Azure potrebbe essere il modo più rapido per la migrazione dei dati nel cloud (perché è IaaS), questo approccio richiede un investimento significativo in team IT (gli amministratori di database e i professionisti IT). I team dell'organizzazione devono essere in grado di configurare e gestire la disponibilità elevata, ripristino di emergenza e patch per SQL Server. Questo contesto è necessario anche un ambiente personalizzato, con diritti amministrativi completi.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Quando eseguire la migrazione a SQL Server come una macchina virtuale (IaaS)

Potrebbero essere presenti alcuni casi in cui è ancora necessario eseguire la migrazione a SQL Server come macchina virtuale regolare. Questa operazione risulta utile se è necessario utilizzare SQL Server Reporting Services. Nella maggior parte dei casi, tuttavia, istanza gestita di Azure SQL Database può fornire tutte le informazioni che necessarie per eseguire la migrazione dal server di SQL Server locale, quindi la migrazione a una macchina virtuale di SQL Server dovrebbe essere l'ultima risorsa per provare.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Utilizzare il servizio di migrazione Database di Azure per eseguire la migrazione dei database relazionali in Azure 

È possibile utilizzare un servizio di migrazione di Database di Azure per eseguire la migrazione di database relazionali di SQL Server, Oracle e MySQL in Azure, se il database di destinazione è il Database SQL di Azure, istanza gestita di Azure SQL Database o SQL Server in una macchina virtuale di Azure.

Il flusso di lavoro automatizzato, grazie ai report di valutazione, in modo semplificato le modifiche è necessario apportare prima della migrazione del database. Quando si è pronti, il servizio esegue la migrazione di database di origine in Azure.

Ogni volta che si modifica un RDBMS originale, potrebbe essere necessario rieseguire il test. Inoltre potrebbe essere necessario modificare le frasi SQL o il codice di Mapping relazionale a oggetti (ORM) nell'applicazione, in base ai risultati dei test.

Se si dispone di qualsiasi altro database (ad esempio, IBM DB2) e non si scelga un approccio di accuratezza e MAIUSC, si potrebbe desidera continuare a usare tali database come macchine virtuali IaaS di Azure, a meno che non si è disposti a eseguire una migrazione di dati più complessa. Una migrazione di dati più complessa richiedono sforzo aggiuntivo, perché potrebbe eseguire la migrazione a un tipo di database diverso con nuovo schema e le librerie di programmazione diverse.

Per informazioni su come eseguire la migrazione di database tramite servizio di migrazione di Database di Azure, vedere [ottenere nel cloud più velocemente all'istanza gestita di Azure SQL Database e del servizio di migrazione di Database Azure](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Risorse aggiuntive

- **Scegliere un cloud di opzione di SQL Server: Database SQL di Azure (PaaS) o SQL Server nella macchina virtuale di Azure (IaaS)**

    [https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas)

- **Ottenere il cloud più velocemente all'istanza gestita di Azure SQL database e il servizio di migrazione di Database**

    [https://channel9.msdn.com/Events/Build/2017/P4008](https://channel9.msdn.com/Events/Build/2017/P4008)

- **Migrazione di database di SQL Server al Database SQL nel cloud**

    [https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate](https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate)

- **Database SQL di Azure**

    [https://azure.microsoft.com/services/sql-database/?v=16.50](https://azure.microsoft.com/services/sql-database/?v=16.50)

- **SQL Server in macchine virtuali**

    [https://azure.microsoft.com/services/virtual-machines/sql-server/](https://azure.microsoft.com/services/virtual-machines/sql-server/)

>[!div class="step-by-step"]
[Precedente](lift-and-shift-existing-apps-azure-iaas.md)
[Successivo](lift-and-shift-existing-apps-devops/index.md)