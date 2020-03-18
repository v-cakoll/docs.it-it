---
title: Sollevare e spostare le app .NET esistenti in Azure IaaS (Cloud Infrastructure-Ready)
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows.Modernize Existing .NET Applications with Azure Cloud and Windows Containers.
ms.date: 04/28/2018
ms.openlocfilehash: c7638a034dbb27baea1b097bdb66175bfb5a71f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73089641"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Sollevare e spostare le app .NET esistenti in Azure IaaS (Cloud Infrastructure-Ready)

> Visione: come primo passo, per ridurre l'investimento in locale e il costo totale della manutenzione dell'hardware e della rete, è sufficiente ospitare nuovamente le applicazioni esistenti nel cloud.

Prima di iniziare *a* eseguire la migrazione delle applicazioni esistenti alla piattaforma IaaS (Azure Infrastructure as a Service), è importante analizzare i motivi per cui si vuole eseguire la migrazione direttamente a IaaS in Azure.Before get into how to migrate your existing applications to the Azure infrastructure as a service (IaaS) platform, it's important to analyze the reasons *why* you'd want to migrate directly to IaaS in Azure. Lo scenario a questo livello di maturità di modernizzazione consiste essenzialmente nell'iniziare a usare le macchine virtuali nel cloud, anziché continuare a usare l'infrastruttura locale corrente.

Un altro punto da analizzare è *il motivo* per cui è possibile eseguire la migrazione al cloud IaaS puro anziché aggiungere solo servizi gestiti più avanzati in Azure.Another point to analyze is why you might want to migrate to pure IaaS cloud instead of just adding more advanced managed services in Azure. Determinare quali casi potrebbero richiedere IaaS in primo luogo.

Figura 2-1 posiziona applicazioni Cloud Infrastructure-Ready nei livelli di maturità di modernizzazione:

![Posizionamento delle applicazioni Cloud Infrastructure-Ready](./media/image2-1.png)

**Figura 2-1.** Posizionamento delle applicazioni Cloud Infrastructure-Ready

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Perché eseguire la migrazione di applicazioni Web .NET esistenti ad Azure IaaSWhy migrate existing .NET web applications to Azure IaaS

Il motivo principale per migrare al cloud, anche a livello iniziale di IaaS, è quello di ottenere riduzioni dei costi. Utilizzando più servizi di infrastruttura gestita, l'organizzazione può ridurre gli investimenti in manutenzione hardware, provisioning e distribuzione di server o macchine virtuali e gestione dell'infrastruttura.

Dopo aver deciso di spostare le app nel cloud, il motivo principale per cui è possibile scegliere IaaS anziché opzioni più avanzate come PaaS è semplicemente che l'ambiente IaaS sarà più familiare. Il passaggio a un ambiente simile all'ambiente locale corrente offre una curva di apprendimento inferiore, che lo rende il percorso più rapido verso il cloud.

Tuttavia, prendere il percorso più rapido per il cloud non significa che si otterrà il massimo vantaggio da avere le applicazioni in esecuzione nel cloud. Qualsiasi organizzazione otterrà i vantaggi più significativi da una migrazione cloud ai livelli di maturità Cloud-Optimized e Cloud-Native già introdotti.

È anche diventato evidente che le applicazioni sono più facili da modernizzare e riprogettare in futuro quando sono già in esecuzione nel cloud, anche su IaaS. La migrazione dei dati delle applicazioni è già stata eseguita. Inoltre, l'organizzazione avrà acquisito le competenze necessarie per lavorare nel cloud e ha fatto il passaggio a operare in una "cultura del cloud".

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Quando eseguire la migrazione a IaaS anziché a PaaS

Le sezioni successive illustrano le applicazioni ottimizzate per il cloud che si basano principalmente su piattaforme e servizi PaaS. Queste app offrono la maggior parte dei vantaggi derivanti dalla migrazione al cloud.

Se l'obiettivo consiste semplicemente nello spostamento delle applicazioni esistenti nel cloud, identificare innanzitutto le applicazioni esistenti che non richiederebbero modifiche sostanziali per l'esecuzione nel servizio app di Azure.If your goal is simply to move existing applications to the cloud, first, identify existing applications that would not require substantial modification to run in Azure App Service. Queste app devono essere i primi candidati per cloud-Optimized.

Quindi, per le app che non possono ancora passare ai contenitori di Windows e PaaS, ad esempio il servizio app o gli agenti di orchestrazione come il servizio Azure Kubernetes, eseguirne la migrazione a macchine virtuali semplici (IaaS).

Tuttavia, tenere presente che la corretta configurazione, protezione e manutenzione delle macchine virtuali richiede molto più tempo e competenze IT rispetto all'utilizzo dei servizi PaaS in Azure.But, keep in mind that correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to using PaaS services in Azure. Se si consideraNo le macchine virtuali di Azure, assicurarsi di prendere in considerazione lo sforzo di manutenzione in corso necessario per applicare patch, aggiornare e gestire l'ambiente VM. Azure Virtual Machines is IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Usare Azure Migrate per analizzare ed eseguire la migrazione delle applicazioni esistenti in AzureUse Azure Migrate to analyze and migrate your existing applications to Azure

La migrazione al cloud non deve essere difficile. Ma molte organizzazioni faticano a iniziare - per ottenere una visibilità approfondita nell'ambiente e le strette interdipendenze tra applicazioni, carichi di lavoro e dati. Senza tale visibilità, può essere difficile pianificare il percorso in avanti. Senza informazioni dettagliate su ciò che è necessario per una migrazione di successo, non è possibile avere le conversazioni giuste all'interno dell'organizzazione. Non si conoscono abbastanza i potenziali vantaggi in termini di costi o se i carichi di lavoro potrebbero semplicemente essere sollevati e spostati o potrebbero richiedere una riecreazione significativa per eseguire correttamente la migrazione. Non c'è da stupirsi che molte organizzazioni esitino.

[Azure Migrate](https://aka.ms/azuremigrate) è un nuovo servizio che fornisce le linee guida, le informazioni dettagliate e i meccanismi necessari per facilitare la migrazione ad Azure.Azure Migrate is a new service that provides the guidance, insights, and mechanisms needed to assist you in migrating to Azure. Azure Migrate offre:

- Individuazione e valutazione per le macchine virtuali locali

- Mapping delle dipendenze integrato per l'individuazione ad alta confidenza delle applicazioni multilivello

- Dimensionamento corretto intelligente per le macchine virtuali di Azure

- Report sulla compatibilità con linee guida per la correzione di potenziali problemi

- Integrazione con il servizio di gestione di database di Azure per l'individuazione e la migrazione dei database

Azure Migrate offre la certezza che i carichi di lavoro possono eseguire la migrazione con un impatto minimo per l'azienda ed essere eseguiti come previsto in Azure.Azure Migrate gives you confident that your workloads can migrate with minimal impact to the business and run as expected in Azure. Con gli strumenti e le linee guida giusti, è possibile ottenere il massimo ritorno sull'investimento assicurando al contempo che le esigenze critiche di prestazioni e affidabilità siano soddisfatte.

Nella figura 2-2 viene illustrato il mapping delle dipendenze predefinito per tutte le connessioni server e applicazioni eseguite da Azure Migrate.

![Posizionamento delle applicazioni Cloud Infrastructure-Ready](./media/image2-2.png)

**Come illustrato 2-2.** Posizionamento delle applicazioni Cloud Infrastructure-Ready

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Usare Azure Site Recovery per eseguire la migrazione delle macchine virtuali esistenti alle macchine virtuali di AzureUse Azure Site Recovery to migrate your existing VMs to Azure VMs

Come parte della migrazione end-to-end di [Azure,](https://aka.ms/azuremigrate)Azure Site Recovery è uno strumento che è possibile usare per eseguire facilmente la migrazione delle app Web alle macchine virtuali in Azure.As part of the end-to-end Azure Migrate , [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) is a tool that you can use to easily migrate your web apps to VMs in Azure. È possibile usare Site Recovery per replicare le macchine virtuali locali e i server fisici in Azure o per replicarli in un percorso locale secondario. È anche possibile replicare un carico di lavoro in esecuzione in una macchina virtuale di Azure supportata, in una macchina virtuale Hyper-V locale, in una macchina *virtuale VMware* o in un server fisico Windows o Linux.You can even replicate a workload that's running on a supported Azure VM, on an on-premises *Hyper-V* VM, on a VMware VM, or on a Windows or Linux physical server. La replica in Azure elimina i costi e la complessità associati alla gestione di un data center secondario.

Site Recovery is also made specifically for hybrid environments that are partly on-premises and partly on Azure. Site Recovery consente di garantire la continuità aziendale mantenendo disponibili le app in esecuzione nelle macchine virtuali e nei server fisici locali in caso di inattività di un sito. Replica i carichi di lavoro in esecuzione su macchine virtuali e server fisici in modo che rimangano disponibili in una posizione secondaria se il sito primario non è disponibile. Ripristina i carichi di lavoro nel sito primario quando è di nuovo attivo.

Nella figura 2-3 viene illustrata l'esecuzione di più migrazioni di macchine virtuali tramite Azure Site Recovery.

![Posizionamento delle applicazioni Cloud Infrastructure-Ready](./media/image2-3.png)

**Come illustrato 2-3.** Posizionamento delle applicazioni Cloud Infrastructure-Ready

### <a name="additional-resources"></a>Risorse aggiuntive

- **Azure Migrate Datasheet**

    <https://aka.ms/azuremigration\_datasheet>

- **Eseguire la migrazione di AzureAzure Migrate**

    <https://aka.ms/azuremigrate>

- **Centro migrazione di AzureAzure migration center**

    <https://azure.microsoft.com/migration/>

- **Eseguire la migrazione ad Azure con Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Panoramica del servizio Azure Site RecoveryAzure Site Recovery service overview**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **Migrazione di macchine virtuali in AWS a macchine virtuali di AzureMigrating VMs in AWS to Azure VMs**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](migrate-your-relational-databases-to-azure.md) <!-- Next Chapter -->
