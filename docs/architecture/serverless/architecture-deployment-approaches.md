---
title: Approcci di distribuzione dell'architettura-app senza server
description: Una guida a diversi modi per le architetture aziendali viene distribuita nel cloud, con confronto tra IaaS, PaaS, contenitori e senza server.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: c745a4eb1c6f4a00bf139100b02f31cf3327d01e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522735"
---
# <a name="architecture-deployment-approaches"></a>Approcci alla distribuzione dell'architettura

Indipendentemente dall'approccio dell'architettura utilizzato per progettare un'applicazione aziendale, l'implementazione o la distribuzione di tali applicazioni può variare. Le aziende ospitano applicazioni su tutti gli elementi, dall'hardware fisico alle funzioni senza server.

## <a name="n-tier-applications"></a>Applicazioni a più livelli

Il [modello di architettura](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier) a più livelli è un'architettura avanzata e si riferisce semplicemente a applicazioni che separano diversi livelli logici in livelli fisici distinti. L'architettura a più livelli è un'implementazione fisica dell'architettura a N livelli. L'implementazione più comune di questa architettura include:

- Un livello di presentazione, ad esempio un'app Web.
- Un'API o un livello di accesso ai dati, ad esempio un'API REST.
- Livello dati, ad esempio un database SQL.

![Architettura a più livelli](./media/n-tier-architecture.png)

Le soluzioni a più livelli hanno le caratteristiche seguenti:

- I progetti sono in genere allineati con i livelli.
- Il test può essere affrontato in modo diverso in base al livello.
- I livelli forniscono livelli di astrazione, ad esempio il livello di presentazione è in genere ignaro dei dettagli di implementazione del livello dati.
- In genere, i livelli interagiscono solo con i livelli adiacenti.
- Le versioni vengono spesso gestite a livello di progetto e, di conseguenza, di livello. Una semplice modifica API potrebbe richiedere una nuova versione di un intero livello intermedio.

Questo approccio offre diversi vantaggi, tra cui:

- Isolamento del database (spesso il front-end non ha accesso diretto al back-end del database).
- Il riutilizzo dell'API (ad esempio, i client di app per dispositivi mobili, desktop e Web possono riutilizzare le stesse API).
- Possibilità di scalare in orizzontale i livelli indipendentemente l'uno dall'altro.
- Refactoring dell'isolamento: è possibile effettuare il refactoring di un livello senza influire sugli altri livelli.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>Locale e infrastruttura distribuita come servizio (IaaS)

L'approccio tradizionale per l'hosting di applicazioni richiede l'acquisto di hardware e la gestione di tutte le installazioni software, incluso il sistema operativo. In origine, era necessario disporre di costosi Data Center e hardware fisico. I problemi relativi all'hardware fisico operativo sono molti, tra cui:

- La necessità di acquistare un eccesso per gli scenari "just in case" o Peak demand.
- Protezione dell'accesso fisico all'hardware.
- Responsabilità degli errori hardware, ad esempio errori del disco.
- Raffreddamento.
- Configurazione di router e di bilanciamento del carico.
- Ridondanza dell'alimentazione.
- Sicurezza dell'accesso al software.

![Approccio IaaS](./media/iaas-approach.png)

La virtualizzazione dell'hardware, tramite "macchine virtuali", Abilita l'infrastruttura distribuita come servizio (IaaS). I computer host sono partizionati in modo efficace per fornire risorse alle istanze con allocazioni per la memoria, la CPU e l'archiviazione. Il team effettua il provisioning delle macchine virtuali necessarie e configura le reti associate e l'accesso alla risorsa di archiviazione.

Per ulteriori informazioni, vedere [architettura di riferimento a più livelli della macchina virtuale](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier).

Anche se la virtualizzazione e l'infrastruttura distribuita come servizio (IaaS) affrontano molti problemi, il team dell'infrastruttura lascia sempre molta responsabilità. Il team gestisce le versioni del sistema operativo, applica le patch di sicurezza e installa le dipendenze di terze parti nei computer di destinazione. Le app spesso si comportano in modo diverso nei computer di produzione rispetto all'ambiente di test. I problemi si verificano a causa di diversi livelli di dipendenza e/o SKU del sistema operativo. Sebbene molte organizzazioni distribuiscano applicazioni a più livelli a tali destinazioni, molte aziende traggono vantaggio dalla distribuzione in un modello di cloud nativo, ad esempio [una piattaforma distribuita come servizio](#platform-as-a-service-paas). Le architetture con microservizi sono più complesse a causa dei requisiti per la scalabilità orizzontale per l'elasticità e la resilienza.

Per ulteriori informazioni, vedere [macchine virtuali](https://docs.microsoft.com/azure/virtual-machines/).

## <a name="platform-as-a-service-paas"></a>Piattaforma distribuita come servizio (PaaS)

Piattaforma distribuita come servizio (PaaS) offre soluzioni configurate che gli sviluppatori possono collegare direttamente. PaaS è un altro termine per l'hosting gestito. Elimina la necessità di gestire il sistema operativo di base, le patch di sicurezza e in molti casi tutte le dipendenze di terze parti. Esempi di piattaforme sono le applicazioni Web, i database e i back-end per dispositivi mobili.

PaaS risolve le questioni comuni a IaaS. PaaS consente allo sviluppatore di concentrarsi sul codice o sullo schema del database anziché su come viene distribuito. I vantaggi di PaaS includono:

- Pagare i modelli di utilizzo che eliminano il sovraccarico dovuto all'investimento in computer inattivi.
- Distribuzione diretta e pipeline di DevOps, integrazione continua (CI) e recapito continuo (CD).
- Aggiornamenti automatici, aggiornamenti e patch di protezione.
- Pulsante con scalabilità orizzontale e scalabilità verticale (scalabilità elastica).

Lo svantaggio principale di PaaS tradizionalmente è costituito dal blocco del fornitore. Alcuni provider PaaS, ad esempio, supportano solo ASP.NET, node. js o altre piattaforme e linguaggi specifici. I prodotti come app Azure Service si sono evoluti per indirizzare più piattaforme e supportare un'ampia gamma di linguaggi e Framework per l'hosting di app Web.

![Architettura di piattaforma distribuita come servizio](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>SaaS (software as a Service)

Il software come servizio o SaaS è ospitato centralmente e disponibile senza installazione o provisioning locale. SaaS è spesso ospitato in PaaS come piattaforma per la distribuzione di software. SaaS fornisce servizi per l'esecuzione e la connessione con il software esistente. SaaS è spesso specifico del settore e verticale. SaaS è spesso concesso in licenza e in genere fornisce un modello client/server. La maggior parte delle moderne offerte SaaS USA app basate sul Web per il client. Le aziende in genere considerano SaaS come una soluzione aziendale per le offerte di licenza. Non viene spesso implementato come considerazione dell'architettura per la scalabilità e la gestibilità di un'applicazione. In realtà, la maggior parte delle soluzioni SaaS si basa su IaaS, PaaS e/o back-end senza server.

Altre informazioni su SaaS tramite un' [applicazione di esempio](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).

## <a name="containers-and-functions-as-a-service-faas"></a>Contenitori e funzioni come servizio (FaaS)

I contenitori sono una soluzione interessante che consente di ottenere vantaggi simili a PaaS senza l'overhead di IaaS. Un contenitore è essenzialmente un runtime che contiene gli elementi essenziali necessari per eseguire un'applicazione univoca. Il kernel o la parte principale del sistema operativo host e i servizi, ad esempio l'archiviazione, sono condivisi tra un host. Il kernel condiviso consente ai contenitori di essere leggeri (alcune dimensioni sono semplici megabyte rispetto alla dimensione Gigabyte delle macchine virtuali tipiche). Con gli host già in esecuzione, i contenitori possono essere avviati rapidamente, facilitando la disponibilità elevata. La possibilità di creare rapidamente i contenitori fornisce anche livelli aggiuntivi di resilienza. Docker è una delle implementazioni più diffuse dei contenitori.

I vantaggi dei contenitori includono:

- Leggero e portatile
- Indipendenti, quindi non è necessario installare le dipendenze
- Fornire un ambiente coerente indipendentemente dall'host (esegue esattamente la stessa cosa in un computer portatile come in un server cloud)
- È possibile eseguire rapidamente il provisioning per la scalabilità orizzontale
- Può essere riavviato rapidamente per il ripristino da un errore

Un contenitore viene eseguito in un host contenitore, che a sua volta può essere eseguito in un computer bare metal o in una macchina virtuale. Più contenitori o istanze degli stessi contenitori possono essere eseguiti in un singolo host. Per il failover e la resilienza reali, i contenitori devono essere ridimensionati tra gli host.

Per altre informazioni sui contenitori Docker, vedere [che cos'è Docker](../microservices/container-docker-introduction/docker-defined.md).

Per gestire i contenitori tra gli host è in genere necessario uno strumento di orchestrazione, ad esempio Kubernetes. La configurazione e la gestione di soluzioni di orchestrazione possono aggiungere ulteriore sovraccarico e complessità ai progetti. Fortunatamente, molti provider di servizi cloud offrono servizi di orchestrazione attraverso soluzioni PaaS per semplificare la gestione dei contenitori.

L'immagine seguente illustra un esempio di installazione di Kubernetes. Nodi nell'indirizzo di installazione con scalabilità orizzontale e failover. Eseguono istanze di contenitore Docker gestite dal server master. *Kubelet* è il client che inoltra i comandi da Kubernetes a docker.

![Kubernetes](./media/kubernetes-example.png)

Per ulteriori informazioni sull'orchestrazione, vedere [Kubernetes in Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).

Functions as a Service (FaaS) è un servizio contenitore specializzato simile a senza server. Un'implementazione specifica di FaaS, denominata [OpenFaaS](https://github.com/openfaas/faas), si trova sopra i contenitori per fornire funzionalità senza server. OpenFaaS fornisce modelli che comportano il pacchetto di tutte le dipendenze del contenitore necessarie per l'esecuzione di un frammento di codice. L'uso di modelli semplifica il processo di distribuzione del codice come unità funzionale. OpenFaaS è destinato a architetture che includono già contenitori e agenti di orchestrazione, perché possono usare l'infrastruttura esistente. Sebbene fornisca funzionalità senza server, in particolare è necessario usare Docker e un agente di orchestrazione.

## <a name="serverless"></a>Senza server

Un'architettura senza server offre una netta separazione tra il codice e il relativo ambiente host. Il codice viene implementato in una *funzione* richiamata da un *trigger*. Una volta terminata la funzione, è possibile liberare tutte le risorse necessarie. Il trigger può essere manuale, un processo temporizzato, una richiesta HTTP o un caricamento di file. Il risultato del trigger è l'esecuzione del codice. Sebbene le piattaforme senza server variano, la maggior parte fornisce l'accesso a API e associazioni predefinite per semplificare le attività, ad esempio la scrittura in un database o l'accodamento dei risultati.

Senza server si intende un'architettura che si basa molto sull'astrazione dell'ambiente host per concentrarsi sul codice. Può essere considerato *meno server*.

Le soluzioni contenitore offrono agli sviluppatori script di compilazione esistenti per pubblicare codice in immagini pronte per il server. Altre implementazioni usano soluzioni PaaS esistenti per fornire un'architettura scalabile.

L'astrazione significa che il team di DevOps non deve effettuare il provisioning o gestire i server, né contenitori specifici. La piattaforma senza server ospita il codice, ad esempio script o file eseguibili in pacchetto compilati con un SDK correlato, e alloca le risorse necessarie per la scalabilità del codice.

Nella figura seguente vengono illustrati quattro componenti senza server. Una richiesta HTTP comporta l'esecuzione del codice dell'API di estrazione. L'API checkout inserisce il codice in un database e l'inserimento attiva diverse altre funzioni da eseguire per eseguire attività quali l'elaborazione di attività e l'evasione dell'ordine.

![Implementazione senza server](./media/serverless-implementation.png)

I vantaggi offerti da senza server includono:

- **Densità elevata.** Molte istanze dello stesso codice senza server possono essere eseguite nello stesso host rispetto a contenitori o macchine virtuali. Le istanze vengono ridimensionate in più host con scalabilità orizzontale e resilienza.
- **Micro-fatturazione.** La maggior parte dei provider senza server viene fatturata in base alle esecuzioni senza server, consentendo un notevole risparmio sui costi in determinati scenari.
- **Scala immediata.** La scalabilità senza server può corrispondere ai carichi di lavoro in modo automatico e rapido.
- **Tempi di immissione sul mercato più rapidi.** Gli sviluppatori si concentrano sul codice e vengono distribuiti direttamente alla piattaforma senza server. I componenti possono essere rilasciati in modo indipendente l'uno dall'altro.

Il server è spesso discusso nel contesto di calcolo, ma può anche essere applicato ai dati. Ad esempio, [SQL di Azure](https://docs.microsoft.com/azure/sql-database) e [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db) forniscono entrambi i database cloud che non richiedono la configurazione di computer o cluster host. Questo libro è incentrato sulle risorse di calcolo senza server.

## <a name="summary"></a>Riepilogo

Esiste una vasta gamma di opzioni disponibili per l'architettura, incluso un approccio ibrido. Senza server semplifica l'approccio, la gestione e i costi delle funzionalità delle applicazioni a scapito del controllo e della portabilità. Tuttavia, molte piattaforme senza server espongono una configurazione per ottimizzare la soluzione. Procedure di programmazione valide possono anche avere un codice più portabile e un blocco di piattaforma senza server. La tabella seguente illustra gli approcci di architettura affiancati. Scegliere senza server in base alle esigenze di scalabilità, se si vuole o meno gestire il runtime e in che modo è possibile suddividere i carichi di lavoro in componenti di piccole dimensioni. Nel prossimo capitolo verranno fornite informazioni sulle potenziali problemi con i punti di decisione senza server e altri punti decisionali.

|         |IaaS     |PaaS     |Contenitore|Senza server|
|---------|---------|---------|---------|----------|
|**Scala**|VM       |Istanza |App      |Funzione  |
|**Astrae**|Hardware|Piattaforma|Host sistema operativo|Runtime   |
|**Unità** |VM       |Progetto  |Immagine    |Codice      |
|**Durata**|Mesi|Da giorni a mesi|Da minuti a giorni|Da millisecondi a minuti|
|**Responsabilità**|Applicazioni, dipendenze, Runtime e sistema operativo|Applicazioni e dipendenze|Applicazioni, dipendenze e Runtime|Funzione

- La **scala** si riferisce all'unità utilizzata per ridimensionare l'applicazione
- **Abstracts** si riferisce al livello astratto dall'implementazione
- L' **unità** si riferisce all'ambito degli elementi distribuiti
- **Lifetime** si riferisce al runtime tipico di un'istanza specifica
- La **responsabilità** si riferisce al sovraccarico per la compilazione, la distribuzione e la gestione dell'applicazione

Il capitolo successivo si focalizzerà sull'architettura senza server, sui casi di utilizzo e sui modelli di progettazione.

## <a name="recommended-resources"></a>Risorse consigliate

- [Guida all'architettura delle applicazioni Azure](https://docs.microsoft.com/azure/architecture/guide/)
- [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)
- [SQL di Azure](https://docs.microsoft.com/azure/sql-database)
- [Modello di architettura a più livelli](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
- [Kubernetes in Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes)
- [Microservizi](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
- [Architettura di riferimento a più livelli della macchina virtuale](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
- [Macchine virtuali](https://docs.microsoft.com/azure/virtual-machines/)
- [Che cos'è Docker?](../microservices/container-docker-introduction/docker-defined.md)
- [Applicazione SaaS Wingtip Tickets](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[Precedente](architecture-approaches.md)
>[Successivo](serverless-architecture.md)
