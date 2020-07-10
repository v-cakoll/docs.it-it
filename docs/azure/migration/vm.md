---
title: Eseguire la migrazione di un'app Web ASP.NET a una macchina virtuale di Azure
description: Informazioni su come eseguire la migrazione di un'applicazione Web ASP.NET da locale a una macchina virtuale di Azure.
ms.topic: how-to
ms.date: 06/20/2020
ms.openlocfilehash: 5ef340d020b72bebe46fe598fe68e7d02d0c0363
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174244"
---
# <a name="migrate-an-aspnet-web-application-to-an-azure-virtual-machine"></a>Eseguire la migrazione di un'applicazione Web ASP.NET a una macchina virtuale di Azure

Questo documento offre una panoramica su come eseguire la migrazione di un'applicazione Web ASP.NET da locale a una macchina virtuale di Azure.

## <a name="quickstart"></a>Guida introduttiva

Informazioni su come creare una macchina virtuale e pubblicarvi un'app: [Pubblicare un'app in una VM di Azure](https://tutorials.visualstudio.com/aspnet-vm/intro)

## <a name="get-started"></a>Introduzione

Queste esercitazioni illustrano i passaggi per creare una macchina virtuale (o eseguirne la migrazione), pubblicarvi l'applicazione Web e altre attività che potrebbero essere necessarie per supportare l'applicazione in Azure.

- Creare una macchina virtuale per l'applicazione ASP.NET in Azure usando una delle opzioni seguenti:
  - [Creare una nuova macchina virtuale per le applicazioni ASP.NET](https://go.microsoft.com/fwlink/?linkid=863237)
  - [Eseguire la migrazione di una macchina virtuale VMWare locale esistente](/azure/migrate/tutorial-migrate-vmware)
  - [Eseguire la migrazione di una macchina virtuale Hyper-V locale esistente](/azure/migrate/tutorial-migrate-hyper-v)
- [Pubblicare l'app usando Visual Studio](https://go.microsoft.com/fwlink/?linkid=863240)
- [Creare una rete virtuale sicura per le VM](/azure/virtual-network/virtual-network-get-started-vnet-subnet)
- [Creare una pipeline di integrazione continua/distribuzione continua per l'applicazione](/vsts/build-release/apps/cd/deploy-webdeploy-iis-deploygroups)
- [Passare a un set di scalabilità di macchine virtuali per la scalabilità e la disponibilità elevata](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app)

## <a name="considerations"></a>Considerazioni

### <a name="benefits"></a>Vantaggi

Le macchine virtuali sono il modo più semplice per eseguire la migrazione di un'applicazione da locale al cloud. Consentono di replicare lo stesso ambiente usato dall'applicazione in locale, eliminando la necessità di mantenere i data center. I set di scalabilità di macchine virtuali forniscono scalabilità e disponibilità elevata per le applicazioni in esecuzione nelle macchine virtuali.

### <a name="virtual-machine-size"></a>Dimensioni della macchina virtuale

Scegliere per la macchina virtuale le dimensioni e il tipo ottimale per il carico di lavoro. Per altre informazioni, vedere [dimensioni per le macchine virtuali Windows in Azure](/azure/virtual-machines/windows/sizes).

### <a name="maintenance"></a>Manutenzione

Come per un computer locale, l'utente è responsabile della manutenzione e dell'aggiornamento della macchina virtuale<sup>&#42;</sup>, ma, se l'applicazione può essere eseguita in un ambiente di piattaforma distribuita come servizio (PaaS), ad esempio il [Servizio app di Azure](/azure/app-service/), o in un [contenitore](/azure/app-service/containers/), non sarà più necessario.

*<sup>&#42;</sup>[Gli aggiornamenti automatici del sistema operativo per i set di scalabilità di macchine virtuali](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade) sono attualmente disponibili come servizio in anteprima.*

### <a name="virtual-networks"></a>Reti virtuali

Le reti virtuali di Azure consentono di:

- Creare un'infrastruttura ibrida facile da controllare
- Usare indirizzi IP e server DNS personali
- Creazione di un ambiente isolato e altamente sicuro per le applicazioni
- Connettere la VM alla rete locale usando una delle diverse [opzioni di connettività](/azure/vpn-gateway/vpn-gateway-about-vpngateways#s2smulti)
- Integrare la macchina virtuale nella rete locale usando [ExpressRoute](https://azure.microsoft.com/services/expressroute/)

Per iniziare, vedere la [documentazione sulla rete virtuale](/azure/virtual-network/)

### <a name="active-directory"></a>Active Directory
Molte applicazioni usano Active Directory per l'autenticazione e la gestione delle identità.

- Azure AD Connect consente di integrare le directory locali con Azure Active Directory. Per iniziare, vedere [Integrare le directory locali con Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- In alternativa, [ExpressRoute](https://azure.microsoft.com/services/expressroute/) consente alle applicazioni di accedere all'istanza di Active Directory locale.

### <a name="sql-databases"></a>DATABASE SQL

Se l'applicazione usa un database locale, l'app non potrà comunicare con il database per impostazione predefinita. È possibile:

- Configurare una rete ibrida che consente all'applicazione di accedere al database in esecuzione in locale.
- Eseguire la migrazione del database ad Azure. Per altre informazioni, vedere [eseguire la migrazione del database di SQL Server in Azure](sql.md).

### <a name="high-availability-and-scalability"></a>Disponibilità e scalabilità elevate

#### <a name="virtual-machine-scale-sets"></a>Set di scalabilità di macchine virtuali
Per fare in modo che l'applicazione sia a disponibilità elevata e scalabile, eseguire la migrazione dell'immagine della VM a un set di scalabilità di macchine virtuali di Azure per migliorare la disponibilità e la scalabilità dell'applicazione. I set di scalabilità di macchine virtuali offrono la possibilità di usare una macchina virtuale esistente già configurata o di configurare una pipeline di compilazione per compilare un'immagine con l'applicazione.

Per iniziare, vedere [Distribuire l'applicazione nei set di scalabilità di macchine virtuali](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app).

#### <a name="centralized-logging"></a>Registrazione centralizzata
Quando si esegue l'applicazione in più istanze, prendere in considerazione la possibilità di archiviare i log in una posizione centralizzata, ad esempio [Archiviazione di Azure](/azure/storage/).

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Eseguire la migrazione di un database SQL Server ad Azure](sql.md)
