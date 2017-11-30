---
title: Spostare le app di esistenti IaaS di Azure
description: Modernizzare le applicazioni .NET esistenti con Cloud di Azure e i contenitori di Windows.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 7f7715bb0ec323874271a7e9ce1c666e23e33b22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lift-and-shift-existing-apps-azure-iaas"></a>Spostare le app di esistenti IaaS di Azure

> Visione: come primo passaggio, per ridurre i costi di investimento e totale on-premise di hardware e rete manutenzione, semplicemente riallocare le applicazioni esistenti nel cloud.

Prima di entrare nei *come* per migrare le applicazioni esistenti per l'infrastruttura di Azure come piattaforma di servizio (IaaS), è importante analizzare i motivi *perché* si desidera eseguire la migrazione direttamente in IaaS in Azure. Per iniziare a usare le macchine virtuali nel cloud, anziché continuare a usare l'infrastruttura locale esistente, è essenzialmente è lo scenario di questo livello di maturità modernizzazione.

Un altro punto da analizzare è *perché* si consiglia di eseguire la migrazione al cloud IaaS pure anziché aggiungere solo più avanzata di servizi gestiti in Azure. È necessario determinare cosa casi potrebbe essere necessario in primo luogo IaaS.

Figura 2-1 posiziona le applicazioni Cloud pronto infrastruttura nei livelli di maturità modernizzazione:

![Posizionamento di applicazioni di infrastruttura Cloud pronto](./media/image2-1.png)

> **Figura 2-1.** Posizionamento di applicazioni di infrastruttura Cloud pronto

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Motivo per cui eseguire la migrazione di applicazioni web .NET esistenti a Azure IaaS 

Il motivo principale per la migrazione al cloud, anche a livello di IaaS iniziale, è quello di ottenere la riduzione dei costi. Utilizzando più servizi di infrastruttura gestita, l'organizzazione può ridurre investimenti in manutenzione dell'hardware, server o il provisioning di VM e la distribuzione e gestione dell'infrastruttura.

Dopo aver apportato la decisione di spostare le applicazioni nel cloud, il motivo principale per cui è possibile scegliere IaaS anziché le opzioni più avanzate come PaaS è semplicemente che l'ambiente IaaS sarà maggiore familiarità. Lo spostamento in un ambiente che è simile a corrente, nell'ambiente locale offre una curva di apprendimento più bassa, che rende il percorso più rapido nel cloud.

Tuttavia, richiede il percorso più rapido nel cloud non significa che sarà possibile ottenere il massimo vantaggio da con le applicazioni in esecuzione nel cloud. Qualsiasi organizzazione otterranno i vantaggi più significativi da una migrazione cloud ai livelli di maturità (ottimizzato per il Cloud) già introdotte DevOps Cloud pronto e PaaS.

È inoltre diventato evidente che le applicazioni sono più semplici da modernizzare e ridefinizione dell'architettura in futuro quando sono già in esecuzione nel cloud, anche in IaaS. Questo vale in parte perché la migrazione dei dati dell'applicazione è già stato raggiunto. Inoltre, l'organizzazione verrà acquisita competenze necessarie per l'utilizzo nel cloud che effettuato lo spostamento funziona in una "impostazioni cultura cloud".

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Quando eseguire la migrazione di IaaS anziché a PaaS

Nelle sezioni successive, approfondiremo applicazioni Cloud pronto DevOps principalmente basato su servizi e delle piattaforme PaaS. Queste App offrono il maggior parte dei vantaggi dalla migrazione al cloud.

Se l'obiettivo è semplicemente per spostare le applicazioni esistenti nel cloud, innanzitutto, identificare le applicazioni esistenti che richiederanno variazioni sostanziali per l'esecuzione in Azure App Service. Queste App devono essere i primo candidati.

Quindi, se si desidera o comunque non è possibile spostare i contenitori di Windows e o orchestrators come Azure Service Fabric o Kubernetes, ancora, quindi è quando è necessario utilizzare normale macchine virtuali (IaaS).

Tuttavia, tenere presente che correttamente la configurazione, protezione e gestione di macchine virtuali richiede più tempo e competenze IT rispetto all'utilizzo di servizi PaaS in Azure. Se si prevede di macchine virtuali di Azure, assicurarsi di prendere in considerazione l'impegno di manutenzione richiesto per applicare la patch, aggiornare e gestire l'ambiente di VM. Macchine virtuali di Azure è IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Utilizzare la migrazione di Azure per analizzare ed eseguire la migrazione delle applicazioni esistenti in Azure

Migrazione al cloud non deve essere difficile. Tuttavia, molte organizzazioni hanno difficoltà a iniziare - per ottenere la visibilità completa dell'ambiente e una stretta interdipendenze tra le applicazioni, i carichi di lavoro e i dati. Senza tale visibilità, può essere difficile pianificare il percorso in avanti. Senza informazioni dettagliate sulle operazioni necessarie per la migrazione ha esito positivo, è possibile che le conversazioni destra all'interno dell'organizzazione. Non si conosce sufficientemente circa la potenziale, vantaggi economici o se i carichi di lavoro potrebbe semplicemente accuratezza di spostamento e o richiedono notevoli variazioni per eseguire correttamente la migrazione. Non sorprende che molte organizzazioni sono riluttanti.

[Migrazione Azure](https://aka.ms/azuremigrate) è un nuovo servizio che fornisce i meccanismi necessari per la migrazione in Azure, informazioni e istruzioni. Migrazione di Azure fornisce:

-   Individuazione e la valutazione per le macchine virtuali in locale

-   Mapping di dipendenza incorporato per l'individuazione di confidenza elevata delle applicazioni a più livelli

-   Rightsizing intelligente di macchine virtuali di Azure

-   Creazione di report con le linee guida per aggiornando i potenziali problemi di compatibilità

-   Integrazione con servizio di gestione di Database di Azure per l'individuazione del database e la migrazione

Migrazione Azure ci si assicura che i carichi di lavoro può eseguire la migrazione con un impatto minimo sull'azienda e funzionino come previsto in Azure. Strumenti e linee guida sulle, è possibile ottenere massimo utile sugli investimenti pur garantendo che prestazioni critiche ed esigenze di affidabilità siano soddisfatti.

Figura 2-2 viene mostrato il mapping di dipendenza predefinito per tutte le connessioni con server e dell'applicazione eseguita da eseguire la migrazione di Azure.

![Posizionamento di applicazioni di infrastruttura Cloud pronto](./media/image2-2.png)

> **Figura 2-2.** Posizionamento di applicazioni di infrastruttura Cloud pronto

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Usare Azure Site Recovery per eseguire la migrazione di macchine virtuali esistenti in macchine virtuali di Azure

Come parte di end-to-end [eseguire la migrazione di Azure](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) è uno strumento che consente di eseguire facilmente la migrazione delle applicazioni web per le macchine virtuali in Azure. Per replicare le macchine virtuali in locale e server fisici in Azure o per replicarle in un percorso locale secondario, è possibile utilizzare il ripristino del sito. È anche possibile replicare un carico di lavoro è in esecuzione in una VM di Azure supportate, in un locale *Hyper-V* macchina virtuale in un *VMware* macchina virtuale, o in un server fisico di Windows o Linux. La replica in Azure consente di eliminare il costo e la complessità di gestione di un Data Center secondario.

Il ripristino del sito viene anche eseguito in modo specifico per gli ambienti ibridi che sono in parte in locale e in parte in Azure. Il ripristino del sito consente di garantire la continuità aziendale, mantenendo le app che sono in esecuzione nelle macchine virtuali in locale e server fisici disponibili se si arresta un sito. Replica i carichi di lavoro in esecuzione in macchine virtuali e server fisici in modo che rimangano disponibili in un percorso secondario se il sito primario non è disponibile. Vengono ripristinati i carichi di lavoro per il sito primario quando è attivo ed eseguire di nuovo.

Figura 2-3 viene illustrata l'esecuzione di più migrazioni di macchine Virtuali tramite Azure Site Recovery.

![Posizionamento di applicazioni di infrastruttura Cloud pronto](./media/image2-3.png)

> **Figura 2-3.** Posizionamento di applicazioni di infrastruttura Cloud pronto

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Foglio dati eseguire la migrazione di Azure**

    [https://aka.ms/azuremigration\_foglio dati](https://aka.ms/azuremigration\_datasheet)

-   **Eseguire la migrazione di Azure**

    [http://azuremigrationcenter.com/](http://azuremigrationcenter.com/)

-   **Eseguire la migrazione a Azure con il ripristino del sito**

    [https://docs.microsoft.com/Azure/Site-Recovery/Site-Recovery-migrate-to-Azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

-   **Panoramica del servizio Azure Site Recovery**

    [https://docs.microsoft.com/Azure/Site-Recovery/Site-Recovery-Overview](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

-   **Macchine virtuali di migrazione in AWS a macchine virtuali di Azure**

    [https://docs.microsoft.com/Azure/Site-Recovery/Site-Recovery-migrate-AWS-to-Azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](migrate-your-relational-databases-to-azure.md)
