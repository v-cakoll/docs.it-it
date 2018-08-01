---
title: Consigli relativi all'hosting di Azure per le applicazioni Web ASP.NET Core
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Consigli relativi all'hosting di Azure per le applicazioni Web ASP.NET
author: ardalis
ms.author: wiwagn
ms.date: 06/27/2018
ms.openlocfilehash: a70cb822c789638ca107b090d1aed2b88ccc6a5d
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404528"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Consigli relativi all'hosting di Azure per le applicazioni Web ASP.NET Core

> "I responsabili line-of-business ignorano l'ufficio IT e acquistano direttamente abbonamenti ad applicazioni nel cloud (SaaS), come se si trattasse abbonamenti a riviste. Quando il servizio non è più necessario, possono annullare l'abbonamento senza dover gestire componenti obsoleti".  
> _\- Daryl Plummer, analista Gartner_

Windows Azure supporta le esigenze e l'architettura di qualsiasi applicazione. Le esigenze di hosting possono essere semplici come quelle di un sito Web statico o sofisticate come quelle di applicazioni costituite da decine di servizi. Per le applicazioni Web monolitiche e i servizi di supporto ASP.NET Core è possibile consigliare l'uso di diverse combinazioni note. Le indicazioni riportate in questo articolo sono raggruppate in base al tipo di risorse da ospitare, a seconda che si tratti di applicazioni complete, singoli processi o dati.

## <a name="web-applications"></a>Applicazioni Web

Le applicazioni Web possono essere ospitate con:

- App Web del servizio app

- Contenitori

- Azure Service Fabric

- Macchine virtuali (VM)

Le app Web del servizio app è la soluzione consigliata per la maggior parte degli scenari. Per le architetture con microservizi può risultare opportuno un approccio basato sui contenitori o su Service Fabric. Se è necessario un maggior controllo sui computer che eseguono l'applicazione, prendere in considerazione le macchine virtuali di Azure.

### <a name="app-service-web-apps"></a>App Web del servizio app

Le app Web del servizio app offrono una piattaforma completamente gestita, ottimizzata per l'hosting di applicazioni Web. Platform-as-a-Service (PaaS) consente di concentrarsi sulla logica di business, lasciando ad Azure la gestione dell'infrastruttura necessaria a garantire l'esecuzione e la scalabilità dell'app. Alcune funzionalità essenziali delle app Web del servizio app:

- Ottimizzazione di DevOps (integrazione e consegna continue, più ambienti, test A/B, supporto dello scripting).

- Scala globale e disponibilità elevata.

- Connessioni alle piattaforme SaaS e ai dati locali.

- Sicurezza e conformità.

- Integrazione con Visual Studio.

Il servizio app di Azure è la scelta ottimale per la maggior parte delle applicazioni Web. La gestione e la distribuzione sono integrate nella piattaforma e i siti possono essere ridimensionati rapidamente per gestire volumi di traffico elevati, mentre il bilanciamento e la gestione del traffico incorporati garantiscono una disponibilità elevata. È possibile spostare facilmente siti esistenti al servizio app di Azure con uno strumento di migrazione online, usare un'app open source dalla Raccolta di app Web o creare un nuovo sito usando il framework e gli strumenti preferiti. La funzionalità Processi Web semplifica l'aggiunta dell'elaborazione di processi in background all'app Web del servizio app.

### <a name="azure-kubernetes-service"></a>Servizio Kubernetes di Azure

Il Servizio Kubernetes di Azure (AKS) gestisce l'ambiente Kubernetes ospitato, rendendo veloce e facile distribuire e gestire applicazioni in contenitori senza competenze nell'orchestrazione di contenitori. Elimina inoltre il carico delle operazioni in corso e la manutenzione con il provisioning, l'aggiornamento e il ridimensionamento delle risorse su richiesta, senza portare offline le applicazioni.

AKS riduce la complessità e i costi operativi di gestione di un cluster Kubernetes addossando gran parte di tale responsabilità ad Azure. Come un servizio Kubernetes ospitato, Azure gestisce attività critiche come il monitoraggio dell'integrità e la manutenzione per conto dell'utente. Inoltre, vengono addebitati solo i costi relativi ai nodi agente all'interno del cluster, non per i master. Come servizio Kubernetes gestito, AKS fornisce:

- Aggiornamenti e patch automatizzati della versione di Kubernetes.
- Ridimensionamento semplice dei cluster.
- Piano di controllo ospitato di riparazione automatica (master).
- Risparmio sui costi: vengono addebitati solo i costi di esecuzione dei nodi dei pool di agenti.

Grazie alla gestione dei nodi nel cluster AKS da parte di Azure, non è più necessario eseguire molte attività manualmente, ad esempio gli aggiornamenti del cluster. Poiché Azure gestisce queste attività di manutenzione critiche per l'utente, AKS non fornisce accesso diretto (ad esempio con SSH) al cluster.

### <a name="azure-service-fabric"></a>Azure Service Fabric

Se si crea una nuova app o si riscrive un'app esistente per l'uso di un'architettura di microservizi, Service Fabric è una scelta ottimale. Le app vengono eseguite in un pool condiviso di computer che inizialmente può essere piccolo e poi crescere fino a includere centinaia o migliaia di computer, in base alle esigenze. I servizi con stato semplificano notevolmente l'archiviazione affidabile e coerente dello stato delle app e Service Fabric gestisce in modo automatico il partizionamento, la scalatura e la disponibilità dei servizi. Service Fabric supporta anche WebAPI con Open Web Interface for .NET (OWIN) e ASP.NET Core. Rispetto al servizio app, Service Fabric offre anche maggior controllo o un accesso diretto all'infrastruttura sottostante. È possibile operare a livello remoto nei server o configurare attività di avvio dei server.

### <a name="azure-virtual-machines"></a>Macchine virtuali di Azure

Se un'applicazione esistente richiede modifiche sostanziali per l'esecuzione nel servizio app di Azure o in Service Fabric, la scelta delle macchine virtuali può semplificare la migrazione al cloud. Tuttavia la configurazione, la protezione e la gestione ottimale delle macchine virtuali richiedono molto più tempo e molte più competenze IT rispetto al servizio app di Azure e a Service Fabric. Se si prevede di usare le macchine virtuali di Azure, prendere in considerazione il carico di lavoro continuativo necessario per applicare patch, aggiornare e gestire l'ambiente delle macchine virtuali. Macchine virtuali di Azure è una soluzione infrastruttura distribuita come servizio (IaaS), mentre il servizio app e Service Fabric sono soluzioni PaaS.

#### <a name="feature-comparison"></a>Confronto tra funzionalità

| Funzionalità                                                                                    | Servizio app | Contenitori (AKS) | Service Fabric | Macchina virtuale |
| ------------------------------------------------------------------------------------------ | ----------- | ---------------- | -------------- | --------------- |
| Distribuzione quasi immediata                                                                    | x           | x                | x              |                 |
| Scalabilità verticale a computer più grandi senza ridistribuzione                                               | x           | x                | x              |                 |
| Le istanze condividono contenuto e configurazione; la ridistribuzione o la riconfigurazione non sono necessarie in caso di ridimensionamento | x           | x                | x              |                 |
| Più ambienti di distribuzione (produzione, gestione temporanea)                                     | x           | x                | x              |                 |
| Gestione automatica degli aggiornamenti del sistema operativo                                                             | x           | x                |                |                 |
| Commutazione trasparente fra piattaforme a 32/64 bit                                             | x           | x                |                |                 |
| Distribuire codice con Git, FTP                                                                  | x           | x                |                | x               |
| Distribuire codice con WebDeploy                                                                 | x           | x                |                | x               |
| Distribuire codice con TFS                                                                       | x           | x                | x              | x               |
| Web host o livello di servizio Web di un'architettura a più livelli                                    | x           | x                | x              | x               |
| Accedere a servizi Azure quali il bus di servizio, l'archiviazione e il database SQL                              | x           | x                | x              | x               |
| Installare qualsiasi file personalizzato con estensione msi                                                                     |             | x                | x              | x               |

## <a name="logical-processes"></a>Processi logici

I singoli processi logici separabili dal resto dell'applicazione possono essere distribuiti in modo indipendente a Funzioni di Azure con la modalità "senza server". Funzioni di Azure consente di scrivere solo il codice necessario per un problema specifico, senza preoccuparsi dell'applicazione o dell'infrastruttura necessarie per eseguire l'applicazione. È possibile scegliere il linguaggio più produttivo per l'attività in questione tra una vasta gamma di linguaggi di programmazione, che include C\#, F\#, Node.js, Python e PHP. Come per la maggior parte delle soluzioni basate sul cloud si paga solo per il tempo d'uso ed è possibile espandere Funzioni di Azure a piacere per soddisfare qualsiasi esigenza.

## <a name="data"></a>Dati

Azure offre una vasta gamma di opzioni per l'archiviazione di dati, pertanto l'applicazione può usare il provider appropriato per i dati in questione.

Per i dati transazionali e relazionali la soluzione migliore è rappresentata dai database SQL di Azure. Per dati che richiedono prestazioni elevate e sono prevalentemente di sola lettura, una cache Redis supportata da un database SQL di Azure può essere una soluzione ottimale.

I dati JSON non strutturati possono essere archiviati in vari modi, dalle colonne del database SQL a BLOB o tabelle in Archiviazione di Azure a DocumentDB. Tra i metodi citati, DocumentDB offre le migliori funzionalità di query ed è l'opzione consigliata per grandi quantità di documenti JSON che richiedono il supporto dell'esecuzione di query.

Per i dati temporanei basati su comandi o eventi e usati per orchestrare il comportamento dell'applicazione è consigliabile usare il bus di servizio di Azure o le code di Archiviazione di Azure. Il bus di archiviazione di Azure offre maggior flessibilità ed è il servizio consigliato per la messaggistica non semplice all'interno dell'applicazione e tra le applicazioni.

## <a name="architecture-recommendations"></a>Suggerimenti per l'architettura

L'architettura dovrebbe dipendere dai requisiti dell'applicazione. Sono disponibili molti servizi di Azure diversi. La scelta di quello giusto è una decisione importante. Microsoft offre una raccolta di architetture di riferimento per favorire l'identificazione delle architetture tipiche ottimizzate per scenari comuni. È possibile associare l'architettura di riferimento più conforme ai requisiti dell'applicazione o quantomeno un'architettura che garantisca un punto di partenza.

La figura 11-2 illustra un'architettura di riferimento di esempio. Questo diagramma illustra un approccio di architettura consigliato per un sito Web CMS (Content Management System) Sitecore, ottimizzato per il marketing.

![](./media/image11-2.png)

**Figura 11-1.** Architettura di riferimento del sito Web di marketing Sitecore.

**Riferimenti - Consigli relativi all'hosting di Azure**

- Architetture delle soluzioni Azure\
  <https://azure.microsoft.com/solutions/architecture/>

- Guida per gli sviluppatori per Microsoft Azure\
  <https://azure.microsoft.com/campaigns/developer-guide/>

- Panoramica sulle app Web\
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- Confronto tra Servizio app di Azure, Macchine virtuali, Service Fabric e Servizi cloud\
  <https://docs.microsoft.com/azure/app-service-web/choose-web-site-cloud-service-vm>

- Introduzione a servizio Kubernetes di Azure (AKS)\
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
[Precedente](development-process-for-azure.md)
