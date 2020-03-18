---
title: Approcci di distribuzione dell'architettura - App senza server
description: Guida ai diversi modi in cui le architetture aziendali vengono distribuite nel cloud, con un confronto tra IaaS, PaaS, contenitori e serverless.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: c745a4eb1c6f4a00bf139100b02f31cf3327d01e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522735"
---
# <a name="architecture-deployment-approaches"></a>Approcci alla distribuzione dell'architettura

Indipendentemente dall'approccio dell'architettura utilizzato per progettare un'applicazione aziendale, l'implementazione o la distribuzione di tali applicazioni può variare. Le aziende ospitano applicazioni su tutto, dall'hardware fisico alle funzioni senza server.

## <a name="n-tier-applications"></a>Applicazioni a più livelli

Il [modello di architettura a più livelli](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier) è un'architettura matura e si riferisce semplicemente alle applicazioni che separano vari livelli logici in livelli fisici separati. L'architettura a più livelli è un'implementazione fisica dell'architettura A più livelli. L'implementazione più comune di questa architettura include:The most common implementation of this architecture includes:

- Un livello di presentazione, ad esempio un'app Web.
- Un'API o un livello di accesso ai dati, ad esempio un'API REST.
- Un livello dati, ad esempio un database SQL.

![Architettura a più livelli](./media/n-tier-architecture.png)

Le soluzioni a più livelli presentano le caratteristiche seguenti:N-tier solutions have the following characteristics:

- I progetti sono in genere allineati con i livelli.
- I test possono essere affrontati in modo diverso in base al livello.
- I livelli forniscono livelli di astrazione, ad esempio il livello di presentazione ignora in genere i dettagli di implementazione del livello dati.
- In genere, i livelli interagiscono solo con i livelli adiacenti.
- I rilasci vengono spesso gestiti a livello di progetto e quindi di livello. Una semplice modifica dell'API può richiedere una nuova versione di un intero livello intermedio.

Questo approccio offre diversi vantaggi, tra cui:This approach provides several benefits, including:

- Isolamento del database (spesso il front-end non ha accesso diretto al back-end del database).
- Il riutilizzo dell'API (ad esempio, i client per dispositivi mobili, desktop e app Web possono tutti riutilizzare le stesse API).
- Possibilità di scalare orizzontalmente i livelli indipendentemente l'uno dall'altro.
- Isolamento di refactoring: è possibile effettuare il refactoring di un livello senza influire sugli altri livelli.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>Locale e infrastruttura come servizio (IaaS)

L'approccio tradizionale alle applicazioni di hosting richiede l'acquisto di hardware e la gestione di tutte le installazioni software, incluso il sistema operativo. In origine questo comportava costosi data center e hardware fisico. Le sfide che derivano dall'utilizzo dell'hardware fisico sono molte, tra cui:

- La necessità di acquistare l'eccesso per "solo nel caso in cui" o scenari di domanda di picco.
- Protezione dell'accesso fisico all'hardware.
- Responsabilità per l'errore hardware (ad esempio un errore del disco).
- Raffreddamento.
- Configurazione di router e servizi di bilanciamento del carico.
- Ridondanza dell'alimentazione.
- Protezione dell'accesso al software.

![Approccio IaaS](./media/iaas-approach.png)

La virtualizzazione dell'hardware, tramite "macchine virtuali", consente l'infrastruttura come servizio (IaaS). I computer host sono partizionati in modo efficace per fornire risorse alle istanze con allocazioni per la propria memoria, CPU e archiviazione. Il team effettua il provisioning delle macchine virtuali necessarie e configura le reti associate e l'accesso all'archiviazione.

Per altre informazioni, vedere Architettura di riferimento a [più livelli della macchina virtuale.](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)

Anche se la virtualizzazione e l'infrastruttura come servizio (IaaS) affrontano molte preoccupazioni, lascia ancora molta responsabilità nelle mani del team dell'infrastruttura. Il team gestisce le versioni del sistema operativo, applica le patch di sicurezza e installa dipendenze di terze parti nei computer di destinazione. Le app spesso si comportano in modo diverso nei computer di produzione rispetto all'ambiente di test. I problemi si verificano a causa di diverse versioni delle dipendenze e/o livelli di SKU del sistema operativo. Sebbene molte organizzazioni distribuiscano applicazioni a più livelli a questi obiettivi, molte aziende traggono vantaggio dalla distribuzione in un modello nativo più cloud, ad esempio [Platform as a Service](#platform-as-a-service-paas). Le architetture con microservizi sono più impegnative a causa dei requisiti di scalabilità orizzontale per elasticità e resilienza.

Per ulteriori informazioni, vedere [Macchine virtuali](https://docs.microsoft.com/azure/virtual-machines/).

## <a name="platform-as-a-service-paas"></a>Platform as a Service (PaaS)

Platform as a Service (PaaS) offre soluzioni configurate che gli sviluppatori possono collegare direttamente. PaaS è un altro termine per l'hosting gestito. Elimina la necessità di gestire il sistema operativo di base, le patch di sicurezza e in molti casi eventuali dipendenze di terze parti. Esempi di piattaforme includono applicazioni Web, database e back-end mobili.

PaaS affronta le sfide comuni a IaaS. PaaS consente allo sviluppatore di concentrarsi sul codice o sullo schema del database anziché sulla modalità di distribuzione. I vantaggi di PaaS includono:

- Pagare per l'uso di modelli che eliminano l'overhead di investire in macchine inattive.
- Distribuzione diretta e DevOps migliorate, integrazione continua (CI) e pipeline di distribuzione continua (CD).
- Aggiornamenti automatici, aggiornamenti e patch di sicurezza.
- Barrata di ridimensionamento e scalabilità verticale (scala elastica).

Lo svantaggio principale di PaaS tradizionalmente è stato il lock-in del fornitore. Ad esempio, alcuni provider PaaS supportano solo ASP.NET, Node.js o altre lingue e piattaforme specifiche. Prodotti come il servizio app di Azure si sono evoluti per indirizzare più piattaforme e supportano una varietà di linguaggi e framework per l'hosting di app Web.

![Architettura della piattaforma come servizio](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>Software as a Service (SaaS)

Il software come servizio o SaaS è ospitato centralmente e disponibile senza installazione o provisioning locale. SaaS è spesso ospitato in cima a PaaS come piattaforma per la distribuzione di software. SaaS fornisce servizi per l'esecuzione e la connessione con il software esistente. SaaS è spesso specifico per settore e verticale. SaaS è spesso concesso in licenza e in genere fornisce un modello client/server. La maggior parte delle offerte SaaS moderne utilizzano app basate sul Web per il cliente. Le aziende in genere considerano SaaS come una soluzione aziendale per le offerte di licenze. Non viene spesso implementato come considerazione dell'architettura per la scalabilità e la manutenibilità di un'applicazione. In fatti, la maggior parte delle soluzioni SaaS sono costruite su back-end IaaS, PaaS e/o serverless.

Ulteriori informazioni su SaaS tramite [un'applicazione di esempio](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).

## <a name="containers-and-functions-as-a-service-faas"></a>Contenitori e funzioni come servizio (FaaS)Containers and Functions as a Service (FaaS)

I contenitori sono una soluzione interessante che consente vantaggi simili a PaaS senza l'overhead IaaS. Un contenitore è essenzialmente un runtime che contiene gli elementi essenziali necessari per eseguire un'applicazione univoca. Il kernel o la parte principale del sistema operativo host e servizi come l'archiviazione sono condivisi in un host. Il kernel condiviso consente ai contenitori di essere leggeri (alcuni sono di dimensioni semplici megabyte, rispetto alle dimensioni gigabyte delle macchine virtuali tipiche). Con gli host già in esecuzione, i contenitori possono essere avviati rapidamente, facilitando la disponibilità elevata. La possibilità di creare rapidamente spin up i contenitori fornisce anche ulteriori livelli di resilienza. Docker è una delle implementazioni più popolari di contenitori.

I vantaggi dei contenitori includono:

- Leggero e portatile
- Indipendente in modo da non dover installare le dipendenze
- Fornire un ambiente coerente indipendentemente dall'host (eseguito esattamente lo stesso su un computer portatile come su un server cloud)
- È possibile eseguire rapidamente il provisioning per la scalabilità orizzontale
- Può essere riavviato rapidamente per il ripristino in caso di errore

Un contenitore viene eseguito in un host contenitore (che a sua volta può essere eseguito su una macchina bare metal o una macchina virtuale). Più contenitori o istanze degli stessi contenitori possono essere eseguiti in un singolo host. Per eseguire il failover e la resilienza reali, i contenitori devono essere scalati tra gli host.

Per ulteriori informazioni sui contenitori Docker, vedere [Che cos'è Docker](../microservices/container-docker-introduction/docker-defined.md).

La gestione dei contenitori tra gli host richiede in genere uno strumento di orchestrazione, ad esempio Kubernetes.Managing containers across hosts typically requires an orchestration tool such as Kubernetes. La configurazione e la gestione delle soluzioni di orchestrazione possono aggiungere ulteriore sovraccarico e complessità ai progetti. Fortunatamente, molti provider di cloud forniscono servizi di orchestrazione tramite soluzioni PaaS per semplificare la gestione dei contenitori.

L'immagine seguente illustra un esempio di installazione di Kubernetes.The following image illustrates an example Kubernetes installation. Nodi nell'indirizzo di installazione scalabilità orizzontale e failover. Vengono eseguite istanze del contenitore Docker gestite dal server master. Il *kubelet* è il client che inoltra i comandi da Kubernetes a Docker.

![Kubernetes](./media/kubernetes-example.png)

Per altre informazioni sull'orchestrazione, vedere Kubernetes in Azure .For more information about orchestration, see [Kubernetes on Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).

Funzioni come servizio (FaaS) è un servizio contenitore specializzato che è simile a serverless. Una specifica implementazione di FaaS, denominata [OpenFaaS](https://github.com/openfaas/faas), si trova in cima ai contenitori per fornire funzionalità senza server. OpenFaaS fornisce modelli che commono tutte le dipendenze del contenitore necessarie per eseguire una parte di codice. L'utilizzo dei modelli semplifica il processo di distribuzione del codice come unità funzionale. OpenFaaS è destinato alle architetture che già includono contenitori e agenti di orchestrazione perché può utilizzare l'infrastruttura esistente. Sebbene fornisca funzionalità senza server, richiede in particolare l'utilizzo di Docker e di un agente di orchestrazione.

## <a name="serverless"></a>Senza server

Un'architettura senza server fornisce una netta separazione tra il codice e il relativo ambiente di hosting. Il codice viene implementato in una *funzione* richiamata da un *trigger*. Dopo la chiusura della funzione, tutte le risorse necessarie possono essere liberate. Il trigger può essere manuale, un processo a tempo, una richiesta HTTP o un caricamento di file. Il risultato del trigger è l'esecuzione del codice. Sebbene le piattaforme senza server varino, la maggior parte fornisce l'accesso ad API e associazioni predefinite per semplificare attività quali la scrittura in un database o la accodamento dei risultati.

Serverless è un'architettura che si basa fortemente sull'astrazione dell'ambiente host per concentrarsi sul codice. Può essere considerato come *meno server*.

Le soluzioni contenitore forniscono agli sviluppatori script di compilazione esistenti per pubblicare codice in immagini pronte per il server. Altre implementazioni utilizzano soluzioni PaaS esistenti per fornire un'architettura scalabile.

L'astrazione significa che il team DevOps non deve eseguire il provisioning o gestire i server, né contenitori specifici. La piattaforma senza server ospita il codice, come script o eseguibili in pacchetto compilati con un SDK correlato, e alloca le risorse necessarie per la scalabilità del codice.

Nella figura seguente vengono illustrati quattro componenti senza server. Una richiesta HTTP causa l'esecuzione del codice DELL'API di estrazione. L'API di estrazione inserisce codice in un database e l'inserimento attiva diverse altre funzioni da eseguire per eseguire attività come l'elaborazione di attività e l'evasione dell'ordine.

![Implementazione senza server](./media/serverless-implementation.png)

I vantaggi di serverless includono:

- **Alta densità.** Molte istanze dello stesso codice serverless possono essere eseguite nello stesso host rispetto a contenitori o macchine virtuali. Le istanze vengono scalate su più host con scalabilità orizzontale e resilienza.
- **Microfatturazione.** La maggior parte dei provider senza server fattura in base alle esecuzioni senza server, consentendo enormi risparmi sui costi in determinati scenari.
- **Scala istantanea.** Serverless può essere scalato in base alle corrispondenze dei carichi di lavoro in modo automatico e rapido.
- **Più veloce tempo di commercializzazione.** Gli sviluppatori si concentrano sul codice e distribuiscono direttamente alla piattaforma senza server. I componenti possono essere rilasciati indipendentemente l'uno dall'altro.

Serverless è più spesso discusso nel contesto del calcolo, ma può anche applicarsi ai dati. Ad esempio, [Azure SQL](https://docs.microsoft.com/azure/sql-database) e [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db) forniscono entrambi database cloud che non richiedono la configurazione di computer host o cluster. Questo libro è incentrato sull'elaborazione senza server.

## <a name="summary"></a>Summary

C'è un ampio spettro di scelte disponibili per l'architettura, tra cui un approccio ibrido. Serverless semplifica l'approccio, la gestione e il costo delle funzionalità dell'applicazione a scapito del controllo e della portabilità. Tuttavia, molte piattaforme serverless espongono la configurazione per ottimizzare la soluzione. Buone pratiche di programmazione possono anche portare a codice più portabile e meno lock-in della piattaforma senza server. Nella tabella seguente vengono illustrati gli approcci architetturali affiancati. Scegliere senza server in base alle esigenze di scalabilità, indipendentemente dal fatto che si desideri gestire il runtime e dalla possibilità di suddividere i carichi di lavoro in componenti di piccole dimensioni. Imparerai a conoscere le potenziali sfide con i punti di decisione senza server e altri nel prossimo capitolo.

|         |IaaS     |PaaS     |Contenitore|Senza server|
|---------|---------|---------|---------|----------|
|**Scala**|VM       |Istanza |App      |Funzione  |
|**Riassunti**|Hardware|Piattaforma|Host del sistema operativo|Runtime   |
|**Unità** |VM       |Project  |Immagine    |Codice      |
|**Durata**|Months|Da giorni a mesi|Da minuti a giorni|Da millisecondi a minuti|
|**Responsabilità**|Applicazioni, dipendenze, runtime e sistema operativo|Applicazioni e dipendenze|Applicazioni, dipendenze e runtime|Funzione

- **Scala** si riferisce all'unità utilizzata per scalare l'applicazione
- **Abstracts** si riferisce al livello astratto dall'implementazione
- **L'unità** si riferisce all'ambito di
- **Durata** si riferisce al runtime tipico di un'istanza specifica
- **La responsabilità** si riferisce all'overhead di compilazione, distribuzione e manutenzione dell'applicazione

Il prossimo capitolo si concentrerà sull'architettura senza server, sui casi d'uso e sui modelli di progettazione.

## <a name="recommended-resources"></a>Risorse consigliate

- [Guida all'architettura delle applicazioni di AzureAzure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/)
- [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)
- [SQL di AzureAzure SQL](https://docs.microsoft.com/azure/sql-database)
- [Modello di architettura a più livelli](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
- [Kubernetes in Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes)
- [Microservizi](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
- [Architettura di riferimento a più livelli della macchina virtualeVirtual machine N-tier reference architecture](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
- [Macchine virtuali](https://docs.microsoft.com/azure/virtual-machines/)
- [Che cos'è Docker?](../microservices/container-docker-introduction/docker-defined.md)
- [Wingtip Tickets SaaS applicazione](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[Successivo](architecture-approaches.md)
>[precedente](serverless-architecture.md)
