---
title: Lift- and -shift le app .NET esistenti ad Azure IaaS (infrastruttura di Cloud-Ready)
description: Modernizza le applicazioni .NET esistenti con Cloud di Azure e i contenitori di Windows.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 0f9ff19c8e346560960a09d3b7c52976c478f2f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651202"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Lift- and -shift le app .NET esistenti ad Azure IaaS (infrastruttura di Cloud-Ready)

> Visione artificiale: Come primo passaggio, per ridurre l'investimento in locale e il costo totale di hardware e manutenzione di rete, è sufficiente rehosting di applicazioni esistenti nel cloud.

Prima di approfondire *modo in cui* per eseguire la migrazione delle applicazioni esistenti all'infrastruttura di Azure come piattaforma di servizio (IaaS), è importante analizzare i motivi *perché* si potrebbe voler eseguire la migrazione direttamente in IaaS in Azure. Lo scenario a questo livello di maturità della modernizzazione è essenzialmente per iniziare a usare macchine virtuali nel cloud, anziché continuare a usare l'infrastruttura corrente, in locale.

È un altro punto da analizzare *perché* si potrebbe voler eseguire la migrazione al cloud IaaS puro anziché aggiungere solo più avanzati di servizi gestiti in Azure. Determinare quali casi potrebbe essere necessario in primo luogo la tecnologia IaaS.

Figura 2-1 delle posizioni pronto per l'infrastruttura Cloud applicazioni i livelli di maturità della modernizzazione:

![Posizionamento pronto per l'infrastruttura Cloud applicazioni](./media/image2-1.png)

> **Figura 2-1.** Posizionamento pronto per l'infrastruttura Cloud applicazioni

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Il motivo per cui eseguire la migrazione di applicazioni web .NET esistenti ad Azure IaaS

Il motivo principale per eseguire la migrazione nel cloud, anche a livello di IaaS iniziale, è ottenere riduzioni dei costi. Con altri servizi di infrastruttura gestita, l'organizzazione può ridurre gli investimenti in manutenzione dell'hardware, server o il provisioning delle VM e la distribuzione e gestione dell'infrastruttura.

Dopo aver apportato la decisione di spostare le app nel cloud, il motivo principale per il motivo per cui è possibile scegliere la tecnologia IaaS anziché le opzioni più avanzate PaaS non è sufficiente che l'ambiente IaaS sarà maggiore familiarità. Passaggio a un ambiente simile a correnti, nell'ambiente locale offre una curva di apprendimento più basso, che rende il percorso più rapido nel cloud.

Portare il percorso più rapido per il cloud non significa tuttavia che si otterrà il massimo vantaggio dalla disponibilità di applicazioni in esecuzione nel cloud. Tutte le organizzazioni otterranno i vantaggi più significativi da una migrazione cloud a livello di maturità già introdotta ottimizzato per il Cloud e Native del Cloud.

Inoltre è diventato evidente che le applicazioni più facili da modernizzare e ridefinizione dell'architettura in futuro quando sono già in esecuzione nel cloud, anche su IaaS. Migrazione dei dati dell'applicazione è già stato raggiunto. Inoltre, l'organizzazione verrà ha acquisito le competenze necessarie per l'utilizzo nel cloud ed effettuato lo spostamento funziona in una "impostazioni cultura cloud".

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Quando eseguire la migrazione a IaaS anziché a PaaS

Le sezioni successive illustrano ottimizzato per il Cloud le applicazioni che sono basate principalmente sui servizi e piattaforme PaaS. Queste App offrono il maggior parte dei vantaggi dall'intraprendere la migrazione al cloud. 

Se l'obiettivo è semplicemente spostare le applicazioni esistenti nel cloud, prima di tutto identificare le applicazioni esistenti che non richiedono modifiche sostanziali per l'esecuzione in servizio App di Azure. Queste App devono essere i primi candidati per ottimizzato per il Cloud. 

Quindi, per le app che ancora non è possibile spostare in contenitori Windows e PaaS, ad esempio servizio App o gli agenti di orchestrazione come Azure Service Fabric, migrare a semplici plain le macchine virtuali (IaaS). 

Tuttavia, tenere presente che correttamente la configurazione, protezione e manutenzione delle macchine virtuali richiede molto più tempo e competenze IT rispetto all'uso dei servizi PaaS in Azure. Se si prevede di macchine virtuali di Azure, assicurarsi di prendere in considerazione il lavoro continuativo necessario per applicare la patch, aggiornare e gestire l'ambiente di macchina virtuale. Macchine virtuali di Azure è la tecnologia IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Usare Azure Migrate per analizzare ed eseguire la migrazione delle applicazioni esistenti in Azure

La migrazione nel cloud non deve essere difficile. Tuttavia, molte organizzazioni hanno difficoltà iniziare, ottenere una visibilità approfondita nell'ambiente e una stretta interdipendenze tra le applicazioni, carichi di lavoro e dati. Tale visibilità, può essere difficile pianificare il percorso in avanti. Senza informazioni dettagliate su ciò che ha richiesto per il successo della migrazione, è possibile avere le conversazioni destro all'interno dell'organizzazione. Non si hanno conoscenze sufficienti sui vantaggi, economici o se i carichi di lavoro è stato appena modalità lift-and-shift o richiederebbero variazioni significative per eseguire correttamente la migrazione. Non sorprende che molte organizzazioni esitano.

[Azure Migrate](https://aka.ms/azuremigrate) è un nuovo servizio che fornisce il materiale sussidiario insights e meccanismi deve supporto della migrazione in Azure. Azure Migrate offre:

- Individuazione e la valutazione per le macchine virtuali in locale

- Mapping delle dipendenze incorporato per l'individuazione di affidabilità elevata delle applicazioni a più livelli

- Intelligent corretto dimensionamento macchine virtuali di Azure

- Creazione di report con le linee guida per la risoluzione di potenziali problemi di compatibilità

- Integrazione con servizio di gestione di Database di Azure per l'individuazione di database e la migrazione

Azure Migrate ci si assicura che i carichi di lavoro può eseguire la migrazione con un impatto minimo per l'azienda e funzionino come previsto in Azure. Con le indicazioni e strumenti appropriati, è possibile ottenere il massimo ritorno sugli investimenti garantendo al contempo che le prestazioni critiche e vengano soddisfatte le esigenze di affidabilità.

Figura 2-2 illustra il mapping di dipendenze predefinito per tutte le connessioni server e dell'applicazione eseguita da Azure Migrate.

![Posizionamento pronto per l'infrastruttura Cloud applicazioni](./media/image2-2.png)

> **Figura 2-2.** Posizionamento pronto per l'infrastruttura Cloud applicazioni

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Usare Azure Site Recovery per eseguire la migrazione delle macchine virtuali esistenti in macchine virtuali di Azure

Come parte di end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) è uno strumento che è possibile usare per eseguire facilmente la migrazione delle App web per le macchine virtuali in Azure. È possibile usare Site Recovery per replicare le macchine virtuali locali e server fisici in Azure o per replicarle in un percorso secondario in locale. È anche possibile replicare un carico di lavoro in esecuzione in una VM di Azure supportati, in locale *Hyper-V* macchina virtuale in un *VMware* macchina virtuale, o in un server fisico Windows o Linux. Replica in Azure Elimina i costi e complessità associati alla gestione di un Data Center secondario.

Site Recovery viene effettuata anche in modo specifico per gli ambienti ibridi che sono in parte in locale e in parte in Azure. Site Recovery aiuta a garantire la continuità aziendale, mantenendo le App in esecuzione nelle macchine virtuali locali e server fisici disponibili se si arresta un sito. Replica i carichi di lavoro in esecuzione in macchine virtuali e server fisici in modo che rimangano disponibili in una posizione secondaria se il sito primario non è disponibile. Vengono ripristinati i carichi di lavoro nel sito primario quando è compito di nuovo.

Figura 2-3 mostra l'esecuzione di più migrazioni di macchine Virtuali con Azure Site Recovery.

![Posizionamento pronto per l'infrastruttura Cloud applicazioni](./media/image2-3.png)

> **Figura 2 e 3.** Posizionamento pronto per l'infrastruttura Cloud applicazioni

### <a name="additional-resources"></a>Risorse aggiuntive

- **Azure Migrate foglio dati**

    <https://aka.ms/azuremigration\_datasheet>

- **Azure Migrate**

    <https://aka.ms/azuremigrate>

- **Centro migrazione di Azure**

    <https://azure.microsoft.com/migration/>

- **Eseguire la migrazione ad Azure con Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Panoramica del servizio Azure Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **Migrazione di VM in AWS a macchine virtuali di Azure**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](migrate-your-relational-databases-to-azure.md)
