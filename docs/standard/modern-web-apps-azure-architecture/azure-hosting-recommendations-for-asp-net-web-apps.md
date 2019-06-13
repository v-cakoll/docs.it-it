---
title: Consigli relativi all'hosting di Azure per le applicazioni Web ASP.NET Core
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Consigli relativi all'hosting di Azure per le applicazioni Web ASP.NET
author: ardalis
ms.author: wiwagn
ms.date: 06/06/2019
ms.openlocfilehash: 7cfb9ada4f963aa392a41cfb9f1b2df22f542d41
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758717"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Consigli relativi all'hosting di Azure per le applicazioni Web ASP.NET Core

> "I responsabili line-of-business ovunque siano ignorando i reparti IT per ottenere applicazioni dal cloud (noto anche come SaaS) e pagamento come se si trattasse abbonamenti a riviste. Quando il servizio non è più necessario, possono annullare l'abbonamento senza dover gestire componenti obsoleti".  
> _\- Daryl Plummer, analista Gartner_

Qualsiasi elemento esigenze e l'architettura dell'applicazione Microsoft Azure può supportare tale condizione. Le esigenze di hosting possono essere semplice quanto un sito Web statico o un'applicazione sofisticata, costituite da decine di servizi. Per le applicazioni Web monolitiche e i servizi di supporto ASP.NET Core è possibile consigliare l'uso di diverse combinazioni note. Le indicazioni riportate in questo articolo sono raggruppate in base al tipo di risorse da ospitare, a seconda che si tratti di applicazioni complete, singoli processi o dati.

## <a name="web-applications"></a>Applicazioni Web

Le applicazioni Web possono essere ospitate con:

- App Web del servizio app

- Contenitori (diverse opzioni)

- Macchine virtuali (VM)

Tra questi, App Web del servizio App è l'approccio consigliato per la maggior parte degli scenari, tra cui semplici App basate su contenitori. Per le architetture con microservizi può risultare opportuno un approccio basato sui contenitori. Se è necessario un maggior controllo sui computer che eseguono l'applicazione, prendere in considerazione le macchine virtuali di Azure.

### <a name="app-service-web-apps"></a>App Web del servizio app

Le app Web del servizio app offrono una piattaforma completamente gestita, ottimizzata per l'hosting di applicazioni Web. Platform-as-a-Service (PaaS) consente di concentrarsi sulla logica di business, lasciando ad Azure la gestione dell'infrastruttura necessaria a garantire l'esecuzione e la scalabilità dell'app. Alcune funzionalità essenziali delle app Web del servizio app:

- Ottimizzazione di DevOps (integrazione e consegna continue, più ambienti, test A/B, supporto dello scripting).

- Scala globale e disponibilità elevata.

- Connessioni alle piattaforme SaaS e ai dati locali.

- Sicurezza e conformità.

- Integrazione con Visual Studio.

Il servizio app di Azure è la scelta ottimale per la maggior parte delle applicazioni Web. La gestione e la distribuzione sono integrate nella piattaforma e i siti possono essere ridimensionati rapidamente per gestire volumi di traffico elevati, mentre il bilanciamento e la gestione del traffico incorporati garantiscono una disponibilità elevata. È possibile spostare facilmente siti esistenti al servizio app di Azure con uno strumento di migrazione online, usare un'app open source dalla Raccolta di app Web o creare un nuovo sito usando il framework e gli strumenti preferiti. La funzionalità Processi Web semplifica l'aggiunta dell'elaborazione di processi in background all'app Web del servizio app. Se si dispone di un applicazione ASP.NET ospitata in locale con un database locale, quindi un percorso chiaro per la migrazione dell'app in un'App Web del servizio App con un Database SQL di Azure (o proteggere l'accesso al server di database in locale, se si preferisce).

![Strategia di migrazione consigliato per un'istanza locale delle app .NET nel servizio App di Azure](./media/image1-6.png)

Nella maggior parte dei casi, lo spostamento da un'app ASP.NET ospitata localmente a un'App Web del servizio App è un processo semplice. Modifiche o minime non dovrebbe essere richiesta dell'app stessa e può iniziare rapidamente a sfruttare i vantaggi delle numerose funzionalità che offrono App Web di servizio App di Azure.

Oltre alle App che non sono ottimizzate per il cloud, App Web di servizio App di Azure sono una soluzione eccellente per molti semplice (non distribuita) applicazioni monolitiche, ad esempio numero di App ASP.NET Core. Questo approccio, l'architettura è basic e semplice da comprendere e gestire:

![Architettura di base di Azure](./media/image1-5.png)

Un numero ridotto di risorse in un unico gruppo di risorse è in genere sufficiente per gestire un'app di questo tipo. Le app che vengono in genere distribuite come singola unità, piuttosto che le app che sono costituite da molti processi separati, sono buoni candidati per questo [approccio dell'architettura di base](https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app). Anche se a livello di architettura semplice, questo approccio consente comunque all'app ospitata di scala sia backup (più risorse per ogni nodo) e out (più nodi hosted) per soddisfare un aumento della domanda. Scalabilità automatica, l'app può essere configurato per regolare automaticamente il numero di nodi che ospitano le app basate su richiesta e di carico medio tra i nodi.

### <a name="app-service-web-apps-for-containers"></a>Servizio app di App Web per contenitori

Oltre al supporto per le app web di hosting, direttamente [App Web del servizio App per contenitori](https://azure.microsoft.com/services/app-service/containers/) può essere usato per eseguire applicazioni in contenitori in Windows e Linux. Uso del servizio, è possibile facilmente distribuire ed eseguire applicazioni in contenitori scalabili con la tua azienda. Le app sono tutte le funzionalità dell'App Web del servizio App elencati in precedenza. Inoltre, le app Web per il supporto di contenitori ottimizzata CI/CD con Docker Hub, registro contenitori di Azure e GitHub. È possibile usare Azure DevOps per definire le pipeline di compilazione e distribuzione che pubblicano le modifiche in un registro di sistema. Queste modifiche possono essere testate in un ambiente di staging e distribuite automaticamente nell'ambiente di produzione usando gli slot di distribuzione, che consente gli aggiornamenti senza tempi di inattività. Eseguire il rollback a versioni precedenti può essere eseguito altrettanto facilmente.

Esistono alcuni scenari in cui le app Web per contenitori più adatti. Se sono presenti App che è possibile creare contenitori, se nei contenitori Windows o Linux, è possibile ospitare le using facilmente questo set di strumenti. È sufficiente pubblicare il contenitore e quindi configurare le app Web per contenitori eseguire il pull dal Registro di sistema di scelta la versione più recente di tale immagine. Questo è un approccio di "lift and -shift" per la migrazione da modelli a un modello ottimizzato per il cloud di hosting di app classico.

![Eseguire la migrazione di applicazioni .NET in contenitori in locale per App Web di Azure per contenitori](./media/image1-8.png)

Questo approccio funziona anche bene se il team di sviluppo è in grado di spostare in un processo di sviluppo basato su contenitori. Il ciclo"interno" di sviluppo di App con i contenitori include la creazione dell'app con i contenitori. Le modifiche apportate al codice e configurazione del contenitore vengono eseguito il push al controllo del codice sorgente e una compilazione automatizzata è responsabile per la pubblicazione di nuove immagini del contenitore in un registro di sistema, ad esempio Hub Docker o registro contenitori di Azure. Queste immagini vengono quindi usate come base per sviluppo aggiuntivi, nonché per le distribuzioni di produzione, come illustrato nel diagramma seguente:

![Flusso di lavoro ciclo di vita DevOps end to End Docker](./media/image1-7.png)

Sviluppo con i contenitori offre molti vantaggi, specialmente quando i contenitori vengono usati nell'ambiente di produzione. La configurazione del contenitore stesso è utilizzata per ospitare l'app in ogni ambiente in cui viene eseguito, dal computer di sviluppo locale per compilare e testare sistemi nell'ambiente di produzione. Questo riduce notevolmente la probabilità di errori derivanti dalle differenze relative alla configurazione della macchina o le versioni del software. Gli sviluppatori possono anche usare gli strumenti risultano più produttivi, tra cui sistema operativo, dal momento che possono eseguire in qualsiasi sistema operativo. In alcuni casi, le applicazioni distribuite che interessano numerosi contenitori possono essere molto grande quantità di risorse per l'esecuzione in un singolo computer di sviluppo. In questo scenario, si potrebbe avere senso per eseguire l'aggiornamento all'uso di Kubernetes e spazi di sviluppo di Azure, illustrati nella sezione successiva.

Come parti di applicazioni di grandi dimensioni sono suddivisi in più proprio piccolo, indipendente *microservizi*, modelli di Progettazione aggiuntive possono essere utilizzati per migliorare un comportamento dell'app. Invece di lavorare direttamente con singoli servizi, un' *gateway API* può semplificare l'accesso e per separare i client dal relativo back-end. Con il back-end per front-end diverso servizio separato consente inoltre servizi di evolversi in concerto con gli utenti. Servizi comuni sono accessibili tramite un oggetto separato *sidecar* contenitore, che potrebbe includere le librerie di connettività client comuni utilizzando il *ambassador* pattern.

![I Microservizi architettura di esempio con diversi modelli di progettazione comuni indicati.](./media/image1-10.png)

[Altre informazioni sui modelli di progettazione da prendere in considerazione durante la creazione di sistemi basati su microservizi.](https://docs.microsoft.com/azure/architecture/microservices/design/patterns)

### <a name="azure-kubernetes-service"></a>Servizio Azure Kubernetes

Il servizio Azure Kubernetes gestisce l'ambiente Kubernetes ospitato, rendendo veloce e facile distribuire e gestire applicazioni in contenitori senza competenze nell'orchestrazione di contenitori. Elimina inoltre il carico delle operazioni in corso e la manutenzione con il provisioning, l'aggiornamento e il ridimensionamento delle risorse su richiesta, senza portare offline le applicazioni.

Il servizio Azure Kubernetes riduce la complessità e i costi operativi di gestione di un cluster Kubernetes addossando gran parte di tale responsabilità ad Azure. Come un servizio Kubernetes ospitato, Azure gestisce attività critiche come il monitoraggio dell'integrità e la manutenzione per conto dell'utente. Inoltre, vengono addebitati solo i costi relativi ai nodi agente all'interno del cluster, non per i master. Come servizio Kubernetes gestito, il servizio Azure Kubernetes fornisce:

- Aggiornamenti e patch automatizzati della versione di Kubernetes.
- Ridimensionamento semplice dei cluster.
- Piano di controllo ospitato di riparazione automatica (master).
- Risparmio sui costi: vengono addebitati solo i costi di esecuzione dei nodi dei pool di agenti.

Grazie alla gestione dei nodi nel cluster del servizio Azure Kubernetes da parte di Azure, non è più necessario eseguire molte attività manualmente, ad esempio gli aggiornamenti del cluster. Poiché Azure gestisce queste attività di manutenzione critiche per l'utente, il servizio Azure Kubernetes non fornisce accesso diretto (ad esempio con SSH) al cluster.

I team che stanno sfruttando servizio contenitore di AZURE possono anche sfruttare i vantaggi di spazi di sviluppo di Azure. Spazi di sviluppo Azure consente ai team di concentrarsi sullo sviluppo e un'iterazione rapida della propria applicazione di microservizi, consentendo ai team di lavorare direttamente con la propria architettura di microservizi intera o applicazione in esecuzione nel servizio contenitore di AZURE. Spazi di sviluppo Azure offre inoltre un modo per aggiornare in modo indipendente le parti della tua architettura di microservizi in isolamento senza alcun effetto sul resto del cluster servizio contenitore di AZURE o di altri sviluppatori.

![Esempio di flusso di lavoro di Azure Dev spazi](./media/image1-9.gif)

Spazi di sviluppo di Azure:

- Ridurre al minimo i requisiti di risorse e il tempo di configurazione computer locale
- Consentire ai team di eseguire un'iterazione più veloce
- Ridurre il numero di ambienti di integrazione richiesto dal team
- Rimuovi da simulare determinati servizi nel sistema distribuito durante lo sviluppo/test

[Altre informazioni su spazi di sviluppo di Azure](https://docs.microsoft.com/azure/dev-spaces/about)

### <a name="azure-virtual-machines"></a>Macchine virtuali di Azure

Se un'applicazione esistente richiede modifiche sostanziali per l'esecuzione nel servizio app di Azure, la scelta delle macchine virtuali può semplificare la migrazione al cloud. Tuttavia la configurazione, la protezione e la gestione ottimale delle macchine virtuali richiedono molto più tempo e molte più competenze IT rispetto al servizio app di Azure. Se si prevede di usare le macchine virtuali di Azure, prendere in considerazione il carico di lavoro continuativo necessario per applicare patch, aggiornare e gestire l'ambiente delle macchine virtuali. Macchine virtuali di Azure è una soluzione infrastruttura distribuita come servizio (IaaS), mentre il servizio app e una soluzione PaaS. È anche necessario considerare se la distribuzione dell'app come un contenitore Windows nell'app Web per contenitori potrebbe essere un'opzione valida per il proprio scenario.

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

- Architecture\ dell'applicazione Web di base di Azure
  <https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app>

- Schemi progettuali per Microservices\
  <https://docs.microsoft.com/azure/architecture/microservices/design/patterns>

- Guida per gli sviluppatori per Microsoft Azure\
  <https://azure.microsoft.com/campaigns/developer-guide/>

- Panoramica sulle app Web\
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- App Web per contenitori\
  <https://azure.microsoft.com/services/app-service/containers/>

- Introduzione a servizio Azure Kubernetes\
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[Precedente](development-process-for-azure.md)
