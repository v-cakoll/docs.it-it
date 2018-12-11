---
title: Approcci alla distribuzione di architettura - App senza server
description: Una Guida per le architetture enterprise modi diversi vengono distribuiti nel cloud, confronto tra IaaS, PaaS, contenitori e senza server.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5477b8c4531780fdebf194e4f798564e59cd2953
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152669"
---
# <a name="architecture-deployment-approaches"></a>Approcci alla distribuzione di architettura

Indipendentemente dall'architettura di approccio utilizzato per progettare un'applicazione aziendale, l'implementazione o la distribuzione di tali applicazioni può variare. Le aziende ospitano applicazioni su tutti gli elementi dall'hardware fisico per le funzioni senza server.

## <a name="n-tier-applications"></a>Applicazioni a più livelli

Il [modello di architettura a più livelli](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier) è un'architettura matura e fa semplicemente riferimento alle applicazioni che separano i diversi livelli logici in livelli fisici. Architettura a più livelli è un'implementazione fisica di architettura a più livelli. L'implementazione più comune di questa architettura include:

* Un livello di presentazione, ad esempio un'app web.
* Un'API o i dati livello di accesso, ad esempio un'API REST.
* Un livello di dati, ad esempio un database SQL.

![Architettura a più livelli](./media/n-tier-architecture.png)

Soluzioni a più livelli hanno le caratteristiche seguenti:

* I progetti sono in genere allineati con i livelli.
* Test può essere eseguito in modo diverso dal livello.
* Livelli offrono livelli di astrazione, ad esempio il livello di presentazione è in genere che non riconoscono la dei dettagli di implementazione del livello dati.
* In genere, i livelli interagiscono solo con i livelli adiacenti.
* Le versioni vengono spesso gestite il progetto e pertanto il livello, a livello di. Una semplice modifica API può richiedere una nuova versione di un intero livello intermedio.

Questo approccio offre diversi vantaggi, tra cui:

* Isolamento del database (front-end, spesso non ha accesso diretto al database back-end).
* Riutilizzo dell'API (ad esempio, per dispositivi mobili, desktop e client dell'app web può riutilizzare tutte le stesse API).
* Possibilità di scalare orizzontalmente i livelli indipendenti tra loro.
* Isolamento di refactoring: un livello può essere effettuato il refactoring senza alcun impatto sugli altri livelli.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>On-premises e Infrastructure as a Service (IaaS)

L'approccio tradizionale per l'hosting di applicazioni richiede l'acquisto di hardware e la gestione di tutte le installazioni di software, incluso il sistema operativo. In origine questo comportava costosa data center e l'hardware fisico. I problemi relativi all'utilizzo di hardware fisico sono numerosi, tra cui:

* La necessità di acquistare in eccesso per "Just-in caso di" o picchi di scenari di richiesta.
* Proteggere l'accesso fisico all'hardware.
* Responsabilità di un errore hardware (ad esempio, l'errore del disco).
* Sistema di raffreddamento.
* Configurazione di router e i servizi di bilanciamento del carico.
* Ridondanza di alimentazione.
* Protezione dell'accesso al software.

![Approccio IaaS](./media/iaas-approach.png)

Virtualizzazione dell'hardware, tramite "macchine virtuali" consente l'infrastruttura come servizio (IaaS). Computer host sono partizionate in modo efficace per rendere disponibili risorse per le istanze con allocazioni per la propria memoria, CPU e archiviazione. Il team esegue il provisioning di macchine virtuali necessarie e consente di configurare le reti associate e l'accesso all'archiviazione.

Per altre informazioni, vedere [macchina virtuale l'architettura di riferimento a più livelli](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier).

Sebbene la virtualizzazione e infrastruttura distribuita come servizio (IaaS) risolvere numerosi problemi, lascia molto responsabilità messi a disposizione del team dell'infrastruttura. Il team mantiene le versioni del sistema operativo, applica patch di sicurezza e installa le dipendenze di terze parti nei computer di destinazione. Le app si comportano spesso in modo diverso nei computer di produzione rispetto all'ambiente di test. Si verificano problemi a causa di dipendenza diverse versioni e/o livelli SKU del sistema operativo. Sebbene molte organizzazioni distribuiscono applicazioni a più livelli in queste destinazioni, molte aziende trarre vantaggio dalla distribuzione in un altro modello nativa cloud, ad esempio [piattaforma distribuita come servizio](#platform-as-a-service-paas). Le architetture con microservizi sono più complesso a causa dei requisiti per la scalabilità orizzontale per l'elasticità e resilienza.

Per altre informazioni, vedere [macchine virtuali](https://docs.microsoft.com/azure/virtual-machines/).

## <a name="platform-as-a-service-paas"></a>Piattaforma distribuita come servizio (PaaS)

Piattaforma come servizio (PaaS) offre soluzioni che gli sviluppatori possono collegare direttamente in configurato. PaaS è un altro termine di hosting gestiti. Elimina la necessità di gestire il sistema operativo di base, le patch di sicurezza e in molti casi le dipendenze di terze parti. Esempi di piattaforme di applicazioni web, database, e back-end mobili.

PaaS per affrontare le sfide comuni a IaaS. PaaS consente allo sviluppatore di concentrarsi sullo schema del database o di codice piuttosto che ottiene la modalità distribuita. I vantaggi delle soluzioni PaaS includono:

* Paga per i modelli di utilizzo che eliminano il sovraccarico di investire nelle macchine inattive.
* Indirizzare la distribuzione e DevOps migliorato, integrazione continua (CI) e le pipeline di recapito continuo (CD).
* Gli aggiornamenti automatici, gli aggiornamenti e patch di sicurezza.
* Pulsanti con scalabilità orizzontale e scalabilità verticale (scalabilità elastica).

Lo svantaggio principale di PaaS è stato tradizionalmente blocco aggiuntivo fornitore. Alcuni provider PaaS, ad esempio, supportano solo ASP.NET, Node. js, o altri linguaggi specifici del dominio e le piattaforme. Prodotti come il servizio App di Azure si sono evolute per risolvere più piattaforme e supporta un'ampia gamma di linguaggi e Framework per l'hosting di App web.

![Piattaforma distribuita come un'architettura di servizio](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>Software as a Service (SaaS)

Software come un servizio o a soluzioni SaaS è a livello centrale ospitato e disponibile senza alcuna installazione locale o provisioning. SaaS è spesso ospitato su PaaS come piattaforma per la distribuzione del software. SaaS offre servizi per l'esecuzione e connettersi con il software esistente. SaaS è spesso specifico verticale e del settore. Spesso è concesso in licenza e SaaS offre in genere un modello client/server. Più recenti offerte SaaS usano le app basate sul web per il client. Le aziende in genere considerano SaaS come soluzione di business alle offerte di licenza. Spesso non è implementato come considerazione di architettura per la scalabilità e gestibilità di un'applicazione. In effetti, la maggior parte delle soluzioni SaaS sono basate su IaaS, PaaS e/o senza server back-end.

Altre informazioni sul modello SaaS tramite un [applicazione di esempio](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).

## <a name="containers-and-functions-as-a-service-faas"></a>I contenitori e le funzioni come servizio (FaaS)

I contenitori sono una soluzione interessante che consente i vantaggi di PaaS-like senza l'overhead di IaaS. Un contenitore è essenzialmente un runtime che contiene le funzionalità minime necessarie per eseguire un'applicazione univoca. La parte del kernel o core dei sistema operativo host e dei servizi, ad esempio archiviazione sono condivise tra un host. Il kernel condiviso consente ai contenitori leggeri (alcuni sono puramente MB, rispetto alle dimensioni delle macchine virtuali tipici gigabyte). Con gli host già in esecuzione, i contenitori possono essere avviati rapidamente, agevolando la disponibilità elevata. La possibilità di creare rapidamente contenitori offre inoltre livelli aggiuntivi di resilienza. Docker è una delle implementazioni più diffuse dei contenitori.

I vantaggi dei contenitori includono:

* Leggera e portatile
* Self-contained in modo che non è necessario installare le dipendenze
* Fornire un ambiente coerente indipendentemente dall'host (che esegue esattamente le stesse in un computer portatile come in un server cloud)
* È possibile fornire rapidamente per scalabilità orizzontale
* È possibile riavviare rapidamente per eseguire il ripristino da errore

Un contenitore viene eseguito in un host contenitore (che a sua volta può essere eseguito in un computer bare metal o una macchina virtuale). Più contenitori o le istanze dei contenitori stessi possono essere eseguite in un singolo host. Per il failover true e la resilienza, i contenitori devono essere ridimensionati in host.

Per altre informazioni sui contenitori di Docker, vedere [che cos'è Docker](../microservices-architecture/container-docker-introduction/docker-defined.md)?

La gestione di contenitori tra host in genere richiede un strumento di orchestrazione come Kubernetes. Configurazione e gestione delle soluzioni di orchestrazione possono aggiungere ulteriori overhead e complessità per i progetti. Per fortuna, molti provider di servizi cloud offrono servizi di orchestrazione tramite le soluzioni PaaS per semplificare la gestione dei contenitori.

L'immagine seguente illustra un esempio di installazione di Kubernetes. Indirizzo di nodi nell'installazione di scalabilità orizzontale e failover. Eseguono Docker istanze di contenitore che vengono gestite dal server master. Il *kubelet* è il client che inoltra i comandi da Kubernetes per Docker.

![Kubernetes](./media/kubernetes-example.png)

Per altre informazioni sull'orchestrazione, vedere [Kubernetes in Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).

Funzioni come servizio (FaaS) è un servizio contenitore specializzato che è simile a senza server. Un'implementazione specifica di FaaS, chiamato [OpenFaaS](https://github.com/openfaas/faas), si sovrappone a contenitori per fornire funzionalità senza server. OpenFaaS fornisce modelli di tale pacchetto tutte le dipendenze di contenitore necessarie per l'esecuzione di un frammento di codice. Usando i modelli semplifica il processo di distribuzione del codice come un'unità funzionale. OpenFaaS ha come destinazione le architetture che includono già i contenitori e gli agenti di orchestrazione perché può usare l'infrastruttura esistente. Anche se fornisce la funzionalità senza server, in particolare richiede di usare Docker e un agente di orchestrazione.

## <a name="serverless"></a>Senza server

Un'architettura senza server garantisce una netta separazione tra il codice e il relativo ambiente host. Implementare il codice in un *funzione* che viene richiamato da un *trigger*. Dopo tale funzione viene chiusa, tutte le risorse necessarie potrebbero essere liberate. Il trigger può essere manuale, un processo programmato, una richiesta HTTP o caricare un file. Il risultato del trigger è l'esecuzione del codice. Sebbene le piattaforme senza server variano, più forniscono l'accesso alle API e le associazioni predefinite per semplificare attività quali la scrittura in un database o accodamento dei risultati.

Senza server è un'architettura che dipende profondamente astrarre l'ambiente host di concentrarsi sul codice. Può essere considerato *inferiore server*.

Le soluzioni contenitore offrono agli sviluppatori esistente creare script per pubblicare codice in immagini senza server per. Altre implementazioni di usano le soluzioni PaaS esistenti per fornire un'architettura scalabile.

L'astrazione significa che il team DevOps non deve effettuare il provisioning o gestire server, né contenitori specifici. Il codice di piattaforma senza server host, come script o eseguibili nel pacchetto creato con un SDK correlati e alloca le risorse necessarie per il codice per la scalabilità.

Nella figura seguente i diagrammi di quattro componenti senza server. Una richiesta HTTP fa sì che il codice dell'API di completamento della transazione per l'esecuzione. L'API di completamento della transazione inserisce codice in un database e diverse altre funzioni per l'esecuzione per eseguire attività come attività di calcolo ed evasione dell'ordine di trigger insert.

![Implementazione senza server](./media/serverless-implementation.png)

I vantaggi degli strumenti senza server comprendono:

* **Ad alta densità.** Numero di istanze dello stesso codice senza server è possibile eseguire nello stesso host rispetto alle macchine virtuali o i contenitori. La scala di istanze tra più host aumento e la resilienza.
* **Micro-fatturazione**. Bill provider più senza server basata su esecuzioni senza server, consentendo enormi risparmi in determinati scenari.
* **Scalabilità immediata**. Serverless scalabilità necessaria per soddisfare i carichi di lavoro in modo rapido e automaticamente.
* **Tempi di immissione sul mercato** gli sviluppatori di concentrarsi sul codice e distribuire direttamente alla piattaforma senza server. I componenti possono essere rilasciati indipendenti tra loro.

Un'infrastruttura senza server è in genere descritti nel contesto di calcolo, ma può anche applicare ai dati. Ad esempio, [SQL di Azure](https://docs.microsoft.com/azure/sql-database) e [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db) offrono entrambe i database di cloud che non devono essere configurate macchine host o cluster. Questo libro è incentrato sull'elaborazione senza server.

## <a name="summary"></a>Riepilogo

È disponibile un'ampia gamma di scelte disponibili per l'architettura, tra cui un approccio ibrido. Serverless semplifica l'approccio, la gestione e dei costi delle funzionalità dell'applicazione a scapito di controllo e la portabilità. Tuttavia, molte piattaforme senza server espone configurazione in modo da ottimizzarne la soluzione. Le procedure di programmazione possono causare al codice più portabile e meno blocco aggiuntivo piattaforma senza server. La tabella seguente illustra gli approcci di architettura fianco a fianco. Scegliere senza server base di scalabilità di esigenze, se si desidera gestire il runtime e come è possibile suddividere i carichi di lavoro in piccoli componenti. Si apprenderà sulle potenziali sfide da affrontare con senza server e altri punti di decisione nel capitolo successivo.

|         |IaaS     |PaaS     |Contenitore|Senza server|
|---------|---------|---------|---------|----------|
|**Scala**|MACCHINA VIRTUALE       |Istanza |App      |Funzione  |
|**Consente di astrarre**|Hardware|Piattaforma|Sistema operativo Host|Runtime   |
|**Unità** |MACCHINA VIRTUALE       |Progetto  |Image    |Codice      |
|**Durata**|Mesi|Giorni o mesi|Minuti a giorni|Millisecondi a pochi minuti|
|**responsabilità**|Le applicazioni, le dipendenze, runtime e del sistema operativo|Le applicazioni e dipendenze|Le applicazioni, le dipendenze e runtime|Funzione

* **Scalabilità** fa riferimento all'unità in cui viene utilizzata per ridimensionare l'applicazione
* **Consente di astrarre** si riferisce al livello che viene astratto dall'implementazione
* **Unità** fa riferimento all'ambito dell'implementazione
* **Durata** fa riferimento al runtime tipico di un'istanza specifica
* **Responsabilità** si intende l'overhead per compilare, distribuire e gestire l'applicazione

Il capitolo successivo verrà concentrati sull'architettura senza server, casi d'uso e modelli di progettazione.

## <a name="recommended-resources"></a>Risorse consigliate

* [Guida all'architettura delle applicazione Azure](https://docs.microsoft.com/azure/architecture/guide/)
* [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)
* [SQL di Azure](https://docs.microsoft.com/azure/sql-database)
* [Modello di architettura a più livelli](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
* [Kubernetes in Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes)
* [Microservizi](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
* [Architettura di riferimento a più livelli di macchine virtuali](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
* [Macchine virtuali](https://docs.microsoft.com/azure/virtual-machines/)
* [Che cos'è Docker?](../microservices-architecture/container-docker-introduction/docker-defined.md)
* [Applicazione Wingtip Tickets SaaS](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[Precedente](architecture-approaches.md)
>[Successivo](serverless-architecture.md)