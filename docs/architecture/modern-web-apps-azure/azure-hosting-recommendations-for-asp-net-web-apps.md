---
title: Consigli relativi all'hosting di Azure per le applicazioni Web ASP.NET Core
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Consigli relativi all'hosting di Azure per le applicazioni Web ASP.NET
author: ardalis
ms.author: wiwagn
ms.date: 06/06/2019
ms.openlocfilehash: 5587b8b20da8a6801d77b722e9c3326f6e695574
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73416720"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Consigli relativi all'hosting di Azure per le applicazioni Web ASP.NET Core

> "I responsabili line-of-business ignorano l'ufficio IT e acquistano direttamente abbonamenti ad applicazioni nel cloud (note anche come SaaS), come se si trattasse di abbonamenti a riviste. Quando il servizio non è più necessario, possono annullare l'abbonamento senza dover gestire componenti obsoleti".  
> _\-Daryl Plummer, analista di Gartner_

Microsoft Azure supporta le esigenze e l'architettura di qualsiasi applicazione. Le esigenze di hosting possono essere semplici come quelle di un sito Web statico o sofisticate come quelle di applicazioni costituite da decine di servizi. Per le applicazioni Web monolitiche e i servizi di supporto ASP.NET Core è possibile consigliare l'uso di diverse combinazioni note. Le indicazioni riportate in questo articolo sono raggruppate in base al tipo di risorse da ospitare, a seconda che si tratti di applicazioni complete, singoli processi o dati.

## <a name="web-applications"></a>Applicazioni Web

Le applicazioni Web possono essere ospitate con:

- App Web del servizio app

- Contenitori (varie opzioni)

- Macchine virtuali (VM)

Le app Web del servizio app costituiscono la soluzione consigliata per la maggior parte degli scenari, incluse le app semplici basate su contenitori. Per le architetture con microservizi può risultare opportuno un approccio basato sui contenitori. Se è necessario un maggior controllo sui computer che eseguono l'applicazione, prendere in considerazione le macchine virtuali di Azure.

### <a name="app-service-web-apps"></a>App Web del servizio app

Le app Web del servizio app offrono una piattaforma completamente gestita, ottimizzata per l'hosting di applicazioni Web. Platform-as-a-Service (PaaS) consente di concentrarsi sulla logica di business, lasciando ad Azure la gestione dell'infrastruttura necessaria a garantire l'esecuzione e la scalabilità dell'app. Alcune funzionalità essenziali delle app Web del servizio app:

- Ottimizzazione di DevOps (integrazione e consegna continue, più ambienti, test A/B, supporto dello scripting).

- Scala globale e disponibilità elevata.

- Connessioni alle piattaforme SaaS e ai dati locali.

- Sicurezza e conformità.

- Integrazione con Visual Studio.

Azure App Service è la scelta migliore per la maggior parte delle app Web. La distribuzione e la gestione sono integrate nella piattaforma ed è possibile scalare rapidamente i siti per gestire carichi di traffico elevato; inoltre, il bilanciamento del carico e la gestione del traffico predefiniti offrono disponibilità elevata. È possibile spostare facilmente siti esistenti al servizio app di Azure con uno strumento di migrazione online, usare un'app open source dalla Raccolta di app Web o creare un nuovo sito usando il framework e gli strumenti preferiti. La funzionalità Processi Web semplifica l'aggiunta dell'elaborazione di processi in background all'app Web del servizio app. Se si usa un'applicazione ASP.NET ospitata in un database locale, è disponibile un percorso diretto per la migrazione dell'app in un'app Web del servizio app tramite un database SQL di Azure (o, se si preferisce, per la protezione dell'accesso al server di database locale).

![Strategia consigliata per la migrazione di app .NET locali al servizio app di Azure](./media/image1-6.png)

Nella maggior parte dei casi, la migrazione da un'app ASP.NET ospitata in locale a un'app Web del servizio app è un processo molto semplice. È possibile iniziare rapidamente a sfruttare i vantaggi delle numerose funzionalità offerte dall'app Web del servizio app di Azure anche senza modificare l'app o apportando modifiche minime.

Le app Web del servizio app di Azure costituiscono una soluzione eccellente non solo per le app non ottimizzate per il cloud, ma anche per le numerose applicazioni monolitiche (non distribuite) semplici, ad esempio molte delle app ASP.NET Core. Con questo approccio, l'architettura da comprendere e gestire è molto semplice:

![Architettura di base di Azure](./media/image1-5.png)

In genere, è sufficiente un numero ridotto di risorse di un unico gruppo di risorse per gestire un'app di questo tipo. Per questo [approccio architetturale di base](https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app) sono indicate soprattutto le app generalmente distribuite come singola unità, piuttosto che le app costituite da molti processi separati. Anche se architetturalmente semplice, questo approccio garantisce comunque all'app ospitata sia scalabilità verticale (più risorse per nodo) che scalabilità orizzontale (più nodi ospitati), in modo da poter soddisfare un eventuale aumento della domanda. Con la scalabilità automatica, inoltre, l'app può essere configurata in modo da regolare automaticamente il numero di nodi che ospitano l'app in base al carico medio previsto per i nodi.

### <a name="app-service-web-apps-for-containers"></a>App Web del servizio app per contenitori

Oltre al supporto per l'hosting diretto delle app Web, le [app Web del servizio app per contenitori](https://azure.microsoft.com/services/app-service/containers/) possono essere usate anche per eseguire applicazioni in contenitori di Windows e Linux. Usando questo servizio, infatti, è possibile distribuire ed eseguire facilmente applicazioni incluse in contenitori, che possono essere ridimensionate in funzione delle esigenze aziendali. Le app disporranno di tutte le funzionalità delle app Web del servizio app elencate in precedenza. Le app Web per contenitori supportano inoltre processi ottimizzati di integrazione continua/recapito continuo tramite Docker Hub, il registro Azure Container e GitHub. È possibile usare Azure DevOps per definire pipeline di compilazione e distribuzione in grado di pubblicare in un registro le modifiche apportate. Queste modifiche possono essere quindi testate in un ambiente di staging e distribuite automaticamente nell'ambiente di produzione tramite slot di distribuzione, che consentono aggiornamenti senza tempi di inattività. Il rollback a una versione precedente può essere comunque eseguito con altrettanta facilità.

Le app Web per contenitori sono particolarmente adatte in determinati scenari. Se si dispone di app che è possibile includere in contenitori (Windows o Linux), è possibile ospitarle facilmente usando questo set di strumenti. È sufficiente pubblicare il contenitore e configurare quindi le app Web per contenitori in modo da eseguire il pull della versione più recente dell'immagine dal registro in uso. Questo approccio di migrazione da modelli di hosting app classici a un modello ottimizzato per il cloud prende il nome di "lift and -shift".

![Eseguire la migrazione di applicazioni .NET locali in contenitori in app Web Azure per contenitori](./media/image1-8.png)

Questo approccio funziona in modo ottimale se il team di sviluppo è in grado di passare a un processo di sviluppo basato su contenitori. Il "ciclo interno" relativo allo sviluppo di app con contenitori prevede la creazione dell'app con contenitori. Viene eseguito il push delle modifiche apportate al codice e alla configurazione del contenitore nel controllo del codice sorgente e la pubblicazione di nuove immagini del contenitore in un registro come Docker Hub o il registro Azure Container viene eseguita da una compilazione automatizzata. Queste immagini vengono quindi usate come base per altri processi di sviluppo o per altre distribuzioni nell'ambiente di produzione, come illustrato nel diagramma seguente:

![Flusso di lavoro del ciclo di vita delle operazioni di sviluppo di Docker](./media/image1-7.png)

Lo sviluppo con contenitori offre molti vantaggi, in particolar modo quando i contenitori vengono usati nell'ambiente di produzione. La stessa configurazione del contenitore viene usata per effettuare l'hosting dell'app in ogni ambiente in cui viene eseguita, dal computer di sviluppo locale ai sistemi di compilazione e test, fino all'ambiente di produzione. In questo modo, viene notevolmente ridotta la probabilità di errori determinati dalle differenze a livello di configurazione dei computer o di versione software. Gli sviluppatori, inoltre, possono usare gli strumenti con cui hanno maggiore familiarità, incluso il sistema operativo, in quanto i contenitori possono essere eseguiti in qualsiasi sistema operativo. In alcuni casi, le applicazioni distribuite che coinvolgono più contenitori possono richiedere un utilizzo di risorse elevato per poter essere eseguite in una singola macchina di sviluppo. In questi scenari potrebbe essere utile passare all'utilizzo di Kubernetes e di Azure Dev Spaces, come illustrato nella sezione successiva.

Quando parti di applicazioni più grandi vengono suddivise in *microservizi* indipendenti più piccoli, è possibile usare schemi progettuali aggiuntivi per migliorare il comportamento dell'app. Anziché eseguire direttamente le operazioni sui singoli servizi, è possibile usare un *gateway API* per semplificare l'accesso e separare il client dal relativo back-end. La disponibilità di back-end di servizio distinti per front-end diversi consente anche l'evoluzione dei servizi parallelamente ai relativi consumer. È possibile accedere ai servizi comuni tramite un contenitore *collaterale* separato, che può contenere librerie di connettività client comuni grazie allo schema *Ambassador*.

![Esempio di architettura di microservizi con vari modelli progettuali comuni specificati.](./media/image1-10.png)

[Altre informazioni sui modelli progettuali da prendere in considerazione quando si creano sistemi basati su microservizi.](https://docs.microsoft.com/azure/architecture/microservices/design/patterns)

### <a name="azure-kubernetes-service"></a>Servizio Azure Kubernetes

Il servizio Azure Kubernetes gestisce l'ambiente Kubernetes ospitato consentendo di distribuire e gestire applicazioni in contenitori in modo semplice e rapido senza competenze nell'orchestrazione di contenitori. Elimina anche l'impegno delle operazioni in corso e della manutenzione effettuando il provisioning, l'aggiornamento e il ridimensionamento delle risorse su richiesta, senza portare le applicazioni offline.

servizio Azure Kubernetes riduce la complessità e costi operativi di gestione di un cluster Kubernetes addossando gran parte di tale responsabilità ad Azure. Come servizio Kubernetes ospitato, Azure gestisce attività critiche quali il monitoraggio dell'integrità e la manutenzione per l'utente. Inoltre, vengono addebitati solo i costi relativi ai nodi agente all'interno del cluster, non per i master. Come servizio Kubernetes gestito, servizio Azure Kubernetes fornisce:

- Aggiornamenti e patch automatizzati della versione di Kubernetes.
- Ridimensionamento semplice dei cluster.
- Piano di controllo ospitato di riparazione automatica (master).
- Risparmio sui costi: vengono addebitati solo i costi di esecuzione dei nodi dei pool di agenti.

Con la gestione dei nodi da parte di Azure nel cluster servizio Azure Kubernetes non è più necessario eseguire manualmente numerose attività, ad esempio gli aggiornamenti dei cluster. Poiché Azure gestisce queste attività di manutenzione critiche per l'utente, il servizio Azure Kubernetes non fornisce accesso diretto (ad esempio con SSH) al cluster.

I team che usano il servizio Azure Kubernetes possono avvalersi anche di Azure Dev Spaces. Con Azure Dev Spaces i team possono concentrarsi sullo sviluppo e sulla rapida iterazione della propria applicazione di microservizi, grazie alla possibilità di lavorare direttamente con l'intera architettura o applicazione di microservizi nel servizio Azure Kubernetes. Azure Dev Spaces consente anche di aggiornare parti dell'architettura di microservizi in modo indipendente e in completo isolamento, senza alcun impatto sul resto del cluster del servizio Azure Kubernetes o su altri sviluppatori.

![Esempio di flusso di lavoro di Azure Dev Spaces](./media/image1-9.gif)

Azure Dev Spaces:

- Riduce al minimo i requisiti di risorse e il tempo di configurazione dei computer locali
- Consente ai team di velocizzare le operazioni di iterazione
- Riduce il numero di ambienti di integrazione necessari ai team
- Elimina la necessità di simulare determinati servizi nel sistema distribuito durante le fasi di sviluppo/test

[Altre informazioni su Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/about)

### <a name="azure-virtual-machines"></a>Macchine virtuali di Azure

Se un'applicazione esistente richiede modifiche sostanziali per l'esecuzione nel servizio app di Azure, la scelta delle macchine virtuali può semplificare la migrazione al cloud. Tuttavia la configurazione, la protezione e la gestione ottimale delle macchine virtuali richiedono molto più tempo e molte più competenze IT rispetto al servizio app di Azure. Se si prevede di usare le macchine virtuali di Azure, prendere in considerazione il carico di lavoro continuativo necessario per applicare patch, aggiornare e gestire l'ambiente delle macchine virtuali. Macchine virtuali di Azure è una soluzione infrastruttura distribuita come servizio (IaaS), mentre il servizio app e una soluzione PaaS. È anche necessario considerare se la distribuzione dell'app come un contenitore Windows nell'app Web per contenitori potrebbe essere un'opzione valida per il proprio scenario.

## <a name="logical-processes"></a>Processi logici

I singoli processi logici separabili dal resto dell'applicazione possono essere distribuiti in modo indipendente a Funzioni di Azure con la modalità "senza server". Funzioni di Azure consente di scrivere solo il codice necessario per un problema specifico, senza preoccuparsi dell'applicazione o dell'infrastruttura necessarie per eseguire l'applicazione. È possibile scegliere il linguaggio più produttivo per l'attività in questione tra una vasta gamma di linguaggi di programmazione, che include C\#, F\#, Node.js, Python e PHP. Come per la maggior parte delle soluzioni basate sul cloud si paga solo per il tempo d'uso ed è possibile espandere Funzioni di Azure a piacere per soddisfare qualsiasi esigenza.

## <a name="data"></a>Data

Azure offre una vasta gamma di opzioni per l'archiviazione di dati, pertanto l'applicazione può usare il provider appropriato per i dati in questione.

Per i dati transazionali e relazionali la soluzione migliore è rappresentata dai database SQL di Azure. Per dati che richiedono prestazioni elevate e sono prevalentemente di sola lettura, una cache Redis supportata da un database SQL di Azure può essere una soluzione ottimale.

I dati JSON non strutturati possono essere archiviati in diversi modi, dalle colonne del database SQL ai BLOB o alle tabelle in Archiviazione di Azure, al database Cosmos di Azure.Unstructured JSON data can be stored in a variety of ways, from SQL Database columns to Blobs or Tables in Azure Storage, to Azure Cosmos DB. Di questi, Azure Cosmos DB offre la migliore funzionalità di query ed è l'opzione consigliata per un numero elevato di documenti basati su JSON che devono supportare l'esecuzione di query.

Per i dati temporanei basati su comandi o eventi e usati per orchestrare il comportamento dell'applicazione è consigliabile usare il bus di servizio di Azure o le code di Archiviazione di Azure. Il bus di archiviazione di Azure offre maggior flessibilità ed è il servizio consigliato per la messaggistica non semplice all'interno dell'applicazione e tra le applicazioni.

## <a name="architecture-recommendations"></a>Suggerimenti per l'architettura

L'architettura dovrebbe dipendere dai requisiti dell'applicazione. Sono disponibili molti servizi di Azure diversi. La scelta di quello giusto è una decisione importante. Microsoft offre una raccolta di architetture di riferimento per favorire l'identificazione delle architetture tipiche ottimizzate per scenari comuni. È possibile associare l'architettura di riferimento più conforme ai requisiti dell'applicazione o quantomeno un'architettura che garantisca un punto di partenza.

Nella figura 11-1 viene illustrata un'architettura di riferimento di esempio. Questo diagramma illustra un approccio di architettura consigliato per un sito Web CMS (Content Management System) Sitecore, ottimizzato per il marketing.

![Figura 11-1](./media/image11-2.png)

**figura 11-1.** Architettura di riferimento del sito Web di marketing Sitecore.

**Riferimenti – Consigli per l'hosting di AzureReferences – Azure hosting recommendations**

- Architetture delle soluzioni Azure\
  <https://azure.microsoft.com/solutions/architecture/>

- Architettura delle applicazioni Web di base di Azure\
  <https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app>

- Schemi progettuali per microservizi\
  <https://docs.microsoft.com/azure/architecture/microservices/design/patterns>

- Guida per gli sviluppatori per Microsoft Azure\
  <https://azure.microsoft.com/campaigns/developer-guide/>

- Panoramica sulle app Web\
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- App Web per contenitori\
  <https://azure.microsoft.com/services/app-service/containers/>

- Introduzione al servizio Azure Kubernetes\
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[Indietro](development-process-for-azure.md)
