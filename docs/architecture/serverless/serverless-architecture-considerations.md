---
title: Considerazioni sull'architettura senza server - App senza server
description: Comprendere le sfide dell'architettura di applicazioni senza server, dalla gestione dello stato e l'archiviazione permanente alla scalabilità, alla registrazione, alla traccia e alla diagnostica.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: c856683cf6910be98661e634246cd003b93a6d76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522436"
---
# <a name="serverless-architecture-considerations"></a>Considerazioni sull'architettura serverless

L'adozione di un'architettura serverless comporta alcune difficoltà. In questa sezione vengono esaminate alcune delle considerazioni più comuni da tenere presenti. Tutte queste sfide hanno delle soluzioni. Come con tutte le scelte di architettura, la decisione di andare senza server dovrebbe essere presa solo dopo aver considerato attentamente i pro ei contro. A seconda delle esigenze dell'applicazione, è possibile decidere che un'implementazione senza server non sia la soluzione giusta per determinati componenti.

## <a name="managing-state"></a>Gestione dello stato

Le funzioni senza server, come per i microservizi in generale, sono senza stato per impostazione predefinita. Evitare lo stato consente a serverless di essere temporaneo, di scalare orizzontalmente e di fornire resilienza senza un punto centrale di errore. In alcune circostanze, i processi aziendali richiedono lo stato. Se il processo richiede lo stato, sono disponibili due opzioni. È possibile adottare un modello diverso da serverless o interagire con un servizio separato che fornisce lo stato. L'aggiunta di stato può complicare la soluzione e renderne più difficile la scalabilità e creare potenzialmente un singolo punto di errore. Valutare attentamente se la funzione richiede assolutamente lo stato. Se la risposta è "yes", determinare se ha ancora senso implementarla con serverless.

Esistono diverse soluzioni per adottare lo stato senza compromettere i vantaggi di serverless. Alcune delle soluzioni più popolari includono:

- Usare un archivio dati temporaneo o una cache distribuita, ad esempio RedisUse a temporary data store or distributed cache, like Redis
- Archiviare lo stato in un database, ad esempio SQL o CosmosDB
- Gestire lo stato tramite un motore del flusso di lavoro come le funzioni durevoliHandle state through a workflow engine like durable functions

La linea di fondo è che si dovrebbe essere consapevoli della necessità di qualsiasi gestione dello stato all'interno di processi che si sta considerando di implementare con serverless.

## <a name="long-running-processes"></a>Processi a esecuzione prolungata

Molti vantaggi di serverless si basano sui processi che sono effimeri. Tempi di esecuzione brevi rendono più semplice per il provider senza server liberare le risorse quando le funzioni terminano e condividono funzioni tra gli host. La maggior parte dei provider di cloud limita il tempo totale a cui la funzione può essere eseguita a circa 10 minuti. Se il processo può richiedere più tempo, è possibile prendere in considerazione un'implementazione alternativa.

Ci sono alcune eccezioni e soluzioni. Una soluzione può essere quella di suddividere il processo in componenti più piccoli che richiedono meno tempo per l'esecuzione. Se il processo viene eseguito a lungo a causa delle dipendenze, è anche possibile prendere in considerazione un flusso di lavoro asincrono usando una soluzione come le funzioni durevoli. Le funzioni durevoli sospendono e mantengono lo stato del processo mentre è in attesa del completamento di un processo esterno. La gestione asincrona riduce il tempo di esecuzione del processo effettivo.

## <a name="startup-time"></a>Tempo di avvio

Una potenziale preoccupazione per le implementazioni senza server è il tempo di avvio. Per risparmiare risorse, molti provider senza server creano l'infrastruttura "su richiesta". Quando una funzione senza server viene attivata dopo un periodo di tempo, potrebbe essere necessario creare o riavviare le risorse per ospitare la funzione. In alcune situazioni, le partenze a freddo possono causare ritardi di alcuni secondi. Il tempo di avvio varia a seconda dei provider e dei livelli di servizio. Esistono alcuni approcci per risolvere il tempo di avvio se è importante ridurre al minimo per il successo dell'app.

- Alcuni provider consentono agli utenti di pagare per i livelli di servizio che garantiscono l'infrastruttura è "sempre acceso".
- Implementare un meccanismo keep-alive (ping dell'endpoint per mantenerlo "sveglio").
- Usare l'orchestrazione come Kubernetes con un approccio di funzione containerizzata (l'host è già in esecuzione, pertanto la rotazione di nuove istanze è estremamente veloce).

## <a name="database-updates-and-migrations"></a>Aggiornamenti e migrazioni dei database

Un vantaggio del codice senza server è che è possibile rilasciare nuove funzioni senza dover ridistribuire l'intera applicazione. Questo vantaggio può diventare uno svantaggio quando è coinvolto un database relazionale. Le modifiche apportate agli schemi di database sono difficili da sincronizzare con gli aggiornamenti senza server. Ulteriori sfide vengono poste quando le cose vanno male e le modifiche devono essere annullate. L'integrità dei dati è uno dei motivi per cui una procedura consigliata per i microservizi e le funzioni senza server è che possiedono i propri dati. È possibile distribuire le modifiche come una singola unità di calcolo e dati. La realtà è che molti sistemi legacy dispongono di un database back-end di grandi dimensioni che deve essere riconciliato con l'architettura senza server.

Un approccio comune per risolvere il controllo delle versioni dello schema consiste nel non modificare mai le proprietà e le colonne esistenti, ma aggiungere nuove informazioni. Si consideri, ad esempio, una modifica per passare da un flag booleano "completato" per un elenco di attività a una "data di completamento". Invece di rimuovere il campo precedente, la modifica del database sarà:

1. Aggiungere un nuovo campo "Data di completamento".
1. Trasformare il campo booleano "completato" in una funzione calcolata che valuta se la data completata è successiva alla data corrente.
1. Aggiungere un trigger per impostare la data di completamento sulla data corrente quando il valore booleano completato è impostato su true.

La sequenza delle modifiche assicura che il codice legacy continui a essere eseguito "così com'è", mentre le funzioni senza server più recenti possono sfruttare il nuovo campo.

Per ulteriori informazioni sui dati nelle architetture senza server, vedere [Sfide e soluzioni per](../microservices/architect-microservice-container-applications/distributed-data-management.md)la gestione dei dati distribuiti .

## <a name="scaling"></a>Scalabilità

È un malinteso comune che serverless significa "nessun server". E 'in realtà "meno server." Il fatto che esista un'infrastruttura di backup è importante capire quando si tratta di scalabilità. La maggior parte delle piattaforme senza server fornisce un set di controlli per gestire la modalità di scalabilità dell'infrastruttura quando aumenta la densità degli eventi. È possibile scegliere tra una varietà di opzioni, ma la strategia può variare a seconda della funzione. Inoltre, le funzioni vengono in genere eseguite in un host correlato, in modo che le funzioni nello stesso host abbiano le stesse opzioni di scala. È pertanto necessario organizzare e scegliere quali funzioni sono ospitate insieme in base ai requisiti di scalabilità.

Le regole spesso specificano come aumentare la scalabilità verticale (aumentare le risorse host) e la scalabilità orizzontale (aumentare il numero di istanze host) in base a parametri variabili. I trigger per le bilance possono includere pianificazione, frequenza delle richieste, utilizzo della CPU e utilizzo della memoria. Prestazioni più elevate spesso hanno un costo maggiore. Gli approcci meno costosi basati sul consumo potrebbero non essere scalati con la velocità con cui la frequenza delle richieste aumenta improvvisamente. C'è un compromesso tra pagare prima "costo assicurativo" rispetto al pagamento rigorosamente "come si va" e rischiare risposte più lente a causa di improvvisi aumenti della domanda.

## <a name="monitoring-tracing-and-logging"></a>Monitoraggio, traccia e registrazione

Un aspetto spesso trascurato di DevOps è il monitoraggio delle applicazioni una volta distribuite. È importante disporre di una strategia per il monitoraggio delle funzioni senza server. La sfida più grande è spesso la correlazione, o riconoscere quando un utente chiama più funzioni come parte della stessa interazione. La maggior parte delle piattaforme senza server consente la registrazione della console che può essere importata in strumenti di terze parti. Sono inoltre disponibili opzioni per automatizzare la raccolta di dati di telemetria, generare e tenere traccia degli ID di correlazione e monitorare azioni specifiche per fornire informazioni dettagliate. Azure fornisce la [piattaforma Application Insights](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) avanzata per il monitoraggio e l'analisi.

## <a name="inter-service-dependencies"></a>Dipendenze tra servizi

Un'architettura senza server può includere funzioni che si basano su altre funzioni. Infatti, non è raro in un'architettura senza server avere più servizi si chiamano a vicenda come parte di un'interazione o di una transazione distribuita. Per evitare un accoppiamento forte, si consiglia di non fare riferimento direttamente ai servizi. Quando l'endpoint per un servizio deve essere modificato, i riferimenti diretti possono causare un refactoring importante. Una soluzione consigliata consiste nel fornire un meccanismo di individuazione dei servizi, ad esempio un Registro di sistema, che fornisce l'indirizzo finale appropriato per un tipo di richiesta. Un'altra soluzione consiste nell'utilizzare i servizi di messaggistica come code o argomenti per la comunicazione tra i servizi.

## <a name="managing-failure-and-providing-resiliency"></a>Gestione degli errori e fornitura di resilienza

È anche importante considerare il modello di *interruttore-interruttore*: Se, per qualche motivo, un servizio continua a non riuscire, non è consigliabile chiamare più volte tale servizio. Al contrario, viene chiamato un servizio alternativo o viene restituito un messaggio fino a quando non viene ristabilita l'integrità del servizio dipendente. L'architettura senza server deve tenere conto della strategia per la risoluzione e la gestione delle dipendenze tra servizi.

Per continuare il modello di interruttore, i servizi devono essere a tolleranza d'errore e resilienti. La tolleranza di errore si riferisce alla capacità dell'applicazione di continuare l'esecuzione anche dopo che vengono rilevate eccezioni impreviste o stati non validi. La tolleranza di errore è in genere una funzione del codice stesso e del modo in cui viene scritta per gestire le eccezioni. Per resilienza si intende la capacità dell'app di eseguire il ripristino da errori. La resilienza viene spesso gestita dalla piattaforma senza server. La piattaforma deve essere in grado di eseguire la creazione di una nuova istanza di funzione senza server quando si verifica un errore in quella esistente. La piattaforma dovrebbe anche essere abbastanza intelligente da interrompere la rotazione di nuove istanze quando ogni nuova istanza ha esito negativo.

Per ulteriori informazioni, vedere [Implementazione del modello Interruttore di circuito](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md).

## <a name="versioning-and-greenblue-deployments"></a>Controllo delle versioni e distribuzioni verde/blu

Uno dei principali vantaggi di serverless è la possibilità di aggiornare una funzione specifica senza dover ridistribuire l'intera applicazione. Affinché gli aggiornamenti abbiano esito positivo, è necessario eseguire il controllo delle versioni delle funzioni in modo che i servizi che li chiamano vengano indirizzati alla versione corretta del codice. È importante anche una strategia per la distribuzione di nuove versioni. Un approccio comune consiste nell'utilizzare "distribuzioni verde/blu". La distribuzione verde è la funzione corrente. Una nuova versione "blu" viene distribuita in produzione e testata. Quando il test passa, le versioni verde e blu vengono scambiate in modo che la nuova versione venga disponibile. Se si verificano problemi, è possibile scambiare nuovamente. Il supporto del controllo delle versioni e delle distribuzioni in verde/blu richiede una combinazione di funzioni di creazione per supportare le modifiche alla versione e l'utilizzo della piattaforma senza server per gestire le distribuzioni. Un possibile approccio consiste nell'usare i proxy, descritti nel capitolo Piattaforma senza server di Azure.One possible approach is to use proxyies, which are described in the [Azure serverless platform](azure-functions.md#proxies) chapter.

>[!div class="step-by-step"]
>[Successivo](serverless-architecture.md)
>[precedente](serverless-design-examples.md)
