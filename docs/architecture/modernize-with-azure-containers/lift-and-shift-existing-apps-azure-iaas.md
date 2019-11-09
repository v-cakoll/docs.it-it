---
title: Lift-and-Shift delle app .NET esistenti in Azure IaaS (pronto per l'infrastruttura cloud)
description: Modernizza le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows.
ms.date: 04/28/2018
ms.openlocfilehash: c7638a034dbb27baea1b097bdb66175bfb5a71f2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "73089641"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Lift-and-Shift delle app .NET esistenti in Azure IaaS (pronto per l'infrastruttura cloud)

> Visione: come primo passaggio, per ridurre l'investimento locale e il costo totale dell'hardware e della manutenzione di rete, è sufficiente riospitare le applicazioni esistenti nel cloud.

Prima di iniziare *a eseguire* la migrazione delle applicazioni esistenti alla piattaforma di infrastruttura distribuita come servizio (IaaS) di Azure, è importante analizzare i motivi per *cui si vuole* eseguire la migrazione diretta a IaaS in Azure. Lo scenario a questo livello di maturità della modernizzazione è essenzialmente quello di iniziare a usare le macchine virtuali nel cloud, anziché continuare a usare l'infrastruttura locale corrente.

Un altro punto da analizzare è il *motivo* per cui potrebbe essere necessario eseguire la migrazione al Cloud IaaS pure anziché aggiungere semplicemente servizi gestiti avanzati in Azure. Determinare i casi in cui potrebbe essere necessario IaaS in primo luogo.

Figura 2-1 posizioni delle applicazioni predisposte per l'infrastruttura cloud nei livelli di maturità della modernizzazione:

![Posizionamento di applicazioni predisposte per l'infrastruttura cloud](./media/image2-1.png)

**Figura 2-1.** Posizionamento di applicazioni predisposte per l'infrastruttura cloud

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Perché eseguire la migrazione di applicazioni Web .NET esistenti ad Azure IaaS

Il motivo principale per eseguire la migrazione al cloud, anche a un livello iniziale di IaaS, consiste nell'ottenere riduzioni dei costi. Usando più servizi di infrastruttura gestiti, l'organizzazione può ridurre l'investimento nella manutenzione dell'hardware, nel provisioning e nella distribuzione di server o macchine virtuali e nella gestione dell'infrastruttura.

Dopo aver deciso di spostare le app nel cloud, il motivo principale per cui è possibile scegliere IaaS anziché opzioni più avanzate come PaaS è semplicemente che l'ambiente IaaS sarà più familiare. Il passaggio a un ambiente simile all'ambiente locale attuale offre una curva di apprendimento più bassa, che lo rende il percorso più rapido per il cloud.

Tuttavia, l'adozione del percorso più rapido per il cloud non significa che è possibile sfruttare al meglio le applicazioni in esecuzione nel cloud. Tutte le organizzazioni otterranno i vantaggi più significativi di una migrazione nel cloud a livello di maturità già introdotto e ottimizzato per il cloud.

Inoltre, è diventato evidente che le applicazioni sono più facili da modernizzare e riprogettare in futuro quando sono già in esecuzione nel cloud, anche in IaaS. La migrazione dei dati delle applicazioni è già stata completata. Inoltre, l'organizzazione avrà acquisito le competenze necessarie per lavorare nel cloud e apportato il passaggio al funzionamento in una "cultura del cloud".

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Quando eseguire la migrazione a IaaS anziché a PaaS

Le sezioni successive illustrano le applicazioni ottimizzate per il cloud, basate principalmente su piattaforme e servizi PaaS. Queste app offrono i maggiori vantaggi della migrazione al cloud.

Se l'obiettivo è semplicemente spostare le applicazioni esistenti nel cloud, identificare innanzitutto le applicazioni esistenti che non richiedono una modifica sostanziale per l'esecuzione nel servizio app Azure. Queste app devono essere le prime candidate per l'ottimizzazione per il cloud.

Quindi, per le app che non possono ancora passare a contenitori di Windows e PaaS, ad esempio il servizio app o gli agenti di orchestrazione come il servizio Azure Kubernetes, eseguire la migrazione di tali applicazioni in semplici VM semplici (IaaS).

Tuttavia, tenere presente che la configurazione, la protezione e la gestione delle VM richiedono molto più tempo ed esperienza IT rispetto all'uso dei servizi PaaS in Azure. Se si intende prendere in considerazione le macchine virtuali di Azure, assicurarsi di prendere in considerazione le attività di manutenzione in corso necessarie per applicare patch, aggiornare e gestire l'ambiente di macchina virtuale. Macchine virtuali di Azure è IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Usare Azure Migrate per analizzare ed eseguire la migrazione delle applicazioni esistenti in Azure

La migrazione al cloud non deve essere difficile. Tuttavia, molte organizzazioni faticano a iniziare, per ottenere una visibilità approfondita dell'ambiente e le strettamente interdipendenze tra le applicazioni, i carichi di lavoro e i dati. Senza tale visibilità, può essere difficile pianificare il percorso in futuro. Senza informazioni dettagliate sugli elementi necessari per una migrazione corretta, non è possibile avere le conversazioni corrette all'interno dell'organizzazione. Non si è a conoscenza dei vantaggi potenziali per i costi o se è possibile che i carichi di lavoro vengano spostati in modalità Lift-and-Shift o che richiedano una corretta migrazione. Non ci si chiede che molte organizzazioni abbiano esitato.

[Azure migrate](https://aka.ms/azuremigrate) è un nuovo servizio che fornisce indicazioni, informazioni dettagliate e meccanismi necessari per facilitare la migrazione ad Azure. Azure Migrate fornisce:

- Individuazione e valutazione per le macchine virtuali locali

- Mapping delle dipendenze incorporato per l'individuazione ad alta confidenza delle applicazioni multilivello

- Ridimensionamento a destra intelligente in macchine virtuali di Azure

- Creazione di report sulla compatibilità con linee guida per la correzione di potenziali problemi

- Integrazione con il servizio di gestione di database di Azure per l'individuazione e la migrazione di database

Azure Migrate garantisce che i carichi di lavoro possano essere migrati con un effetto minimo sull'azienda ed eseguiti come previsto in Azure. Con gli strumenti e le linee guida appropriati, è possibile ottenere il massimo ritorno sugli investimenti garantendo al contempo le esigenze critiche a livello di prestazioni e affidabilità.

La figura 2-2 illustra il mapping predefinito delle dipendenze per tutte le connessioni a server e applicazioni eseguite da Azure Migrate.

![Posizionamento di applicazioni predisposte per l'infrastruttura cloud](./media/image2-2.png)

**Figura 2-2.** Posizionamento di applicazioni predisposte per l'infrastruttura cloud

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Usare Azure Site Recovery per eseguire la migrazione delle macchine virtuali esistenti in macchine virtuali di Azure

Come parte del [Azure migrate](https://aka.ms/azuremigrate)end-to-end, [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) è uno strumento che è possibile usare per eseguire facilmente la migrazione delle app Web alle macchine virtuali in Azure. È possibile usare Site Recovery per replicare le macchine virtuali locali e i server fisici in Azure o per replicarli in un percorso locale secondario. È anche possibile replicare un carico di lavoro in esecuzione in una macchina virtuale di Azure supportata, in una macchina virtuale *Hyper-V* locale, in una macchina virtuale *VMware* o in un server fisico Windows o Linux. La replica in Azure Elimina i costi e la complessità della gestione di un data center secondario.

Site Recovery viene anche eseguita in modo specifico per gli ambienti ibridi parzialmente in locale e in parte in Azure. Site Recovery garantisce la continuità aziendale mantenendo le applicazioni in esecuzione nelle macchine virtuali e nei server fisici locali disponibili se un sito diventa inattivo. Replica i carichi di lavoro in esecuzione nelle macchine virtuali e nei server fisici in modo che rimangano disponibili in una posizione secondaria se il sito primario non è disponibile. Ripristina i carichi di lavoro nel sito primario quando è di nuovo attivo e in esecuzione.

La figura 2-3 illustra l'esecuzione di più migrazioni di macchine virtuali usando Azure Site Recovery.

![Posizionamento di applicazioni predisposte per l'infrastruttura cloud](./media/image2-3.png)

**Figura 2-3.** Posizionamento di applicazioni predisposte per l'infrastruttura cloud

### <a name="additional-resources"></a>Risorse aggiuntive

- **Foglio dati Azure Migrate**

    <https://aka.ms/azuremigration\_datasheet>

- **Azure Migrate**

    <https://aka.ms/azuremigrate>

- **Centro migrazione di Azure**

    <https://azure.microsoft.com/migration/>

- **Eseguire la migrazione ad Azure con Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Panoramica sul servizio Azure Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **Migrazione di macchine virtuali in AWS alle macchine virtuali di Azure**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](migrate-your-relational-databases-to-azure.md) <!-- Next Chapter -->
