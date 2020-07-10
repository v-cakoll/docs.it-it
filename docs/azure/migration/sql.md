---
title: Eseguire la migrazione di un database SQL Server ad Azure
description: Informazioni su come eseguire la migrazione di un database SQL Server da SQL Server locale ad Azure.
ms.topic: how-to
ms.date: 05/27/2020
ms.openlocfilehash: 5f191cafbff3823d04e1dbd1fdf81e1157e20999
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174283"
---
# <a name="migrate-a-sql-server-database-to-azure"></a>Eseguire la migrazione di un database SQL Server ad Azure

Questo articolo fornisce una breve descrizione di due opzioni per la migrazione di un database di SQL Server in Azure. Azure offre tre opzioni principali per la migrazione di un database di SQL Server di produzione. Questo articolo è incentrato sulle due opzioni seguenti:

1. [SQL Server in VM di Azure](/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-iaas-overview):un'istanza di SQL Server installata e ospitata in una macchina virtuale Windows in esecuzione in Azure, definita anche infrastruttura distribuita come servizio (IaaS).
2. [Database SQL di Azure](/azure/sql-database/sql-database-technical-overview): un servizio completamente gestito di Azure per il database SQL, definito anche piattaforma distribuita come servizio (PaaS).

Entrambi presentano vantaggi e svantaggi che sarà necessario esaminare prima di eseguire la migrazione. La terza opzione è rappresentata dalle [istanze gestite del database SQL di Azure](/azure/sql-database/sql-database-managed-instance).

## <a name="get-started"></a>Introduzione

Le seguenti sono guide utili per la migrazione, a seconda del servizio usato:

* [Eseguire la migrazione di un database di SQL Server a SQL Server in una VM di Azure](/azure/virtual-machines/windows/sql/virtual-machines-windows-migrate-sql)
* [Migrare un database SQL Server in un database SQL di Azure](/azure/sql-database/sql-database-migrate-your-sql-server-database)

I collegamenti seguenti per contenuti concettuali consentono di comprendere meglio le VM:

* [Disponibilità elevata e ripristino di emergenza di SQL Server in Macchine virtuali di Azure](/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-high-availability-dr)
* [Performance best practices for SQL Server in Azure Virtual Machines](/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-performance) (Procedure consigliate sulle prestazioni per SQL Server nelle macchine virtuali di Azure)
* [Modelli di applicazione e strategie di sviluppo per SQL Server in Macchine virtuali di Azure](/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-app-patterns-dev-strategies)

I collegamenti seguenti invece offrono utili informazioni sul database SQL di Azure:

* [Creare e gestire database e server di database SQL di Azure](/azure/sql-database/sql-database-servers-databases)
* [Unità di transazione di database (DTU) e unità di transazione di database elastico (eDTU)](/azure/sql-database/sql-database-what-is-a-dtu)
* [Limiti delle risorse del database SQL di Azure](/azure/sql-database/sql-database-resource-limits)

## <a name="choosing-iaas-or-paas"></a>Scelta di IaaS o di PaaS

Quando si valuta la posizione in cui eseguire la migrazione del database, determinare se IaaS o PaaS è più appropriato.

**Scegliere SQL Server in macchine virtuali di Azure se:**

* Si prevede di trasferire in modalità lift-and-shift il database e le applicazioni con pochissime o nessuna modifica.
* Si preferisce avere il controllo completo sul server di database e sulla VM in cui viene eseguito.
* Si hanno già licenze SQL Server e Windows Server che si intende usare.

**Scegliere il database SQL di Azure se:**

* Si prevede di modernizzare le applicazioni e di eseguire la migrazione per usare altri servizi PaaS in Azure.
* Non si vogliono gestire il server di database e la VM in cui viene eseguito.
* Non si hanno licenze SQL Server o Windows Server o si intende lasciar scadere le licenze disponibili.

La tabella seguente descrive le differenze tra ogni servizio in base a un set di scenari.

| Scenario | SQL Server in VM di Azure | Database SQL di Azure |
|----------|-------------------------|--------------------|
| Migrazione | Richiede modifiche minime al database. | Può richiedere modifiche al database se si usano funzionalità non disponibili in Azure SQL, come stabilito da [Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595), o se si hanno altre dipendenze, ad esempio eseguibili installati in locale.|
| Gestione di disponibilità, ripristino e aggiornamenti | La disponibilità e il ripristino sono configurati manualmente. Gli aggiornamenti possono essere automatizzati con i [set di scalabilità di macchine virtuali](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade). | Gestita automaticamente. |
| Configurazione del sistema operativo sottostante | Configurazione manuale. | Gestita automaticamente. |
| Gestione delle dimensioni del database | Supporta fino a 256 TB di spazio di archiviazione per ogni istanza di SQL Server. | Supporta 8 TB di spazio di archiviazione prima che sia necessaria una partizione orizzontale. |
| Gestione dei costi | È necessario gestire i costi delle licenze SQL Server, i costi delle licenze Windows Server e i costi delle VM (in base a core, RAM e spazio di archiviazione). | È necessario gestire i costi dei servizi (in base a [eDTU o DTU](/azure/sql-database/sql-database-what-is-a-dtu), spazio di archiviazione e numero di database se si usa un pool elastico). È anche necessario gestire il costo dei contratti di servizio. |

Per altre informazioni sulle differenze tra i due, vedere [scegliere l'opzione di distribuzione corretta in Azure SQL](/azure/sql-database/sql-database-paas-vs-sql-server-iaas).

## <a name="faq"></a>Domande frequenti

* **È ancora possibile usare strumenti come SQL Server Management Studio e SQL Server Reporting Services (SSRS) con SQL Server in VM di Azure o il database SQL di Azure?**

    Sì. Tutti gli strumenti di Microsoft SQL funzionano con entrambi i servizi. SSRS tuttavia non fa parte del database SQL di Azure ed è consigliabile eseguirlo in una VM di Azure e quindi fare in modo che punti all'istanza del database.

* **Desidero passare a PaaS, ma non sono certo se il database è compatibile. Sono disponibili strumenti utili?**

    Sì. [Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595) è uno strumento usato durante la migrazione al database SQL di Azure. Il [servizio migrazione del database di Azure](https://azure.microsoft.com/campaigns/database-migration/) è un servizio di anteprima che è possibile usare sia per IaaS che per PaaS.

* **È possibile stimare i costi?**

    Sì. Il [calcolatore prezzi di Azure](https://azure.microsoft.com/pricing/calculator/) può essere usato per stimare i costi per tutti i servizi di Azure, inclusi servizi di database e VM.

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Scegliere l'opzione di hosting di Azure più adatta](choose.md)
