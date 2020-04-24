---
title: Considerazioni sull'architettura senza server-app senza server
description: Informazioni sulle problemi di architettura delle applicazioni senza server, dalla gestione dello stato e dall'archiviazione permanente per la scalabilità, la registrazione, la traccia e la diagnostica.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 3c07e1149e6af41a6b9a9317238e5c71015d2c4e
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135672"
---
# <a name="serverless-architecture-considerations"></a>Considerazioni sull'architettura serverless

L'adozione di un'architettura senza server comporta alcune problemi. In questa sezione vengono esaminate alcune delle considerazioni più comuni da tenere presenti. Tutti questi problemi hanno soluzioni. Come per tutte le opzioni di architettura, la decisione di passare al server non deve essere eseguita solo dopo aver valutato attentamente i vantaggi e gli svantaggi. A seconda delle esigenze dell'applicazione, è possibile decidere che un'implementazione senza server non sia la soluzione corretta per alcuni componenti.

## <a name="managing-state"></a>Gestione dello stato

Le funzioni senza server, come per i microservizi in generale, sono senza stato per impostazione predefinita. Evitare lo stato consente di rendere effimero il server, aumentare il livello di scalabilità orizzontale e fornire resilienza senza un punto centrale di errore. In alcune circostanze, i processi aziendali richiedono lo stato. Se il processo richiede lo stato, sono disponibili due opzioni. È possibile adottare un modello diverso da senza server o interagire con un servizio separato che fornisce lo stato. L'aggiunta dello stato può complicare la soluzione e renderla più difficile da scalare e potenzialmente creare un singolo punto di errore. Valutare attentamente se la funzione richiede assolutamente lo stato. Se la risposta è "Sì", determinare se è comunque opportuno implementarla con senza server.

Sono disponibili diverse soluzioni per adottare lo stato senza compromettere i vantaggi di senza server. Di seguito sono riportate alcune delle soluzioni più diffuse:

- Usare un archivio dati temporaneo o una cache distribuita, ad esempio Redis
- Archiviare lo stato in un database, ad esempio SQL o CosmosDB
- Gestire lo stato tramite un motore del flusso di lavoro come [funzioni permanenti](https://docs.microsoft.com/azure/azure-functions/durable/durable-functions-overview)

Il risultato finale è che è necessario tenere presente la necessità di qualsiasi gestione dello stato all'interno dei processi che si sta considerando di implementare senza server.

## <a name="long-running-processes"></a>Processi a esecuzione prolungata

Molti vantaggi offerti dai server si basano sui processi temporanei. I tempi di esecuzione brevi rendono più semplice per il provider senza server liberare risorse come funzioni terminano e condividono funzioni tra gli host. La maggior parte dei provider di servizi cloud consente di limitare il tempo totale di esecuzione della funzione a circa 10 minuti. Se il processo potrebbe richiedere più tempo, è possibile considerare un'implementazione alternativa.

Esistono alcune eccezioni e soluzioni. Una soluzione può consistere nel suddividere il processo in componenti più piccoli che imprendano individualmente meno tempo per l'esecuzione. Se il processo viene eseguito a lungo a causa di dipendenze, è anche possibile considerare un flusso di lavoro asincrono usando una soluzione come funzioni permanenti. Le funzioni permanenti sospendeno e mantengono lo stato del processo mentre è in attesa del completamento di un processo esterno. La gestione asincrona riduce il tempo di esecuzione del processo effettivo.

## <a name="startup-time"></a>Tempo di avvio

Un potenziale problema con le implementazioni senza server è la fase di avvio. Per conservare le risorse, molti provider senza server creano un'infrastruttura su richiesta. Quando una funzione senza server viene attivata dopo un periodo di tempo, potrebbe essere necessario creare o riavviare le risorse per ospitare la funzione. In alcune situazioni, l'avvio a freddo può causare ritardi di alcuni secondi. Il tempo di avvio varia a seconda del livello di servizio e provider. Ci sono alcuni approcci per risolvere i tempi di avvio se è importante ridurre al minimo il successo dell'app.

- Alcuni provider consentono agli utenti di pagare i livelli di servizio che garantiscono che l'infrastruttura sia "always on".
- Implementare un meccanismo Keep-Alive (effettuare il ping dell'endpoint per mantenerlo "sveglio").
- Utilizzare un'orchestrazione come Kubernetes con un approccio di funzione in contenitori (l'host è già in esecuzione, quindi la creazione di nuove istanze è estremamente veloce).

## <a name="database-updates-and-migrations"></a>Aggiornamenti e migrazioni del database

Un vantaggio del codice senza server è che è possibile rilasciare nuove funzioni senza dover ridistribuire l'intera applicazione. Questo vantaggio può diventare uno svantaggio quando è presente un database relazionale. Le modifiche apportate agli schemi del database sono difficili da sincronizzare con aggiornamenti senza server. Quando si verificano problemi ed è necessario eseguire il rollback delle modifiche, si verificano ulteriori problemi. L'integrità dei dati è un motivo per cui una procedura consigliata per i microservizi e le funzioni senza server è che possiedono i propri dati. È possibile distribuire le modifiche come una singola unità di calcolo e di dati. La realtà è che molti sistemi legacy includono un database back-end di grandi dimensioni che deve essere riconciliato con l'architettura senza server.

Un approccio comune per la risoluzione del controllo delle versioni dello schema consiste nel non modificare mai le colonne e le proprietà esistenti, bensì aggiungere nuove informazioni. Si consideri, ad esempio, una modifica per spostarsi da un flag "completed" booleano per un elenco todo a una "data di completamento". Anziché rimuovere il campo precedente, la modifica del database sarà:

1. Aggiungere un nuovo campo "data di completamento".
1. Trasformare il campo booleano "completed" in una funzione calcolata che valuta se la data completata è successiva alla data corrente.
1. Aggiungere un trigger per impostare la data di completamento sulla data corrente quando il valore booleano completed è impostato su true.

La sequenza di modifiche garantisce che il codice legacy continui a essere eseguito "così com'è", mentre le funzioni senza server più recenti possono sfruttare il nuovo campo.

Per ulteriori informazioni sui dati nelle architetture senza server, vedere [problemi e soluzioni per la gestione dei dati distribuiti](../microservices/architect-microservice-container-applications/distributed-data-management.md).

## <a name="scaling"></a>Scalabilità

Si tratta di un malinteso comune che significa "nessun server". È in effetti "less server". Il fatto che esista un'infrastruttura di supporto è importante comprendere quando si tratta di ridimensionare. La maggior parte delle piattaforme senza server fornisce un set di controlli per gestire la scalabilità dell'infrastruttura in caso di aumento della densità degli eventi. È possibile scegliere tra diverse opzioni, ma la strategia può variare a seconda della funzione. Inoltre, le funzioni vengono in genere eseguite in un host correlato, in modo che le funzioni nello stesso host abbiano le stesse opzioni di scalabilità. È pertanto necessario organizzare e elaborare strategie quali funzioni vengono ospitate insieme in base ai requisiti di scalabilità.

Le regole spesso specificano la modalità di scalabilità verticale (aumento delle risorse host) e la scalabilità orizzontale (aumentare il numero di istanze host) in base a parametri variabili. I trigger per le scale possono includere pianificazione, frequenza delle richieste, utilizzo della CPU e utilizzo della memoria. Le prestazioni più elevate spesso hanno un costo maggiore. Gli approcci meno costosi e basati sul consumo potrebbero non essere ridimensionati rapidamente quando la frequenza delle richieste aumenta improvvisamente. C'è un compromesso tra il pagamento anticipato di "costo assicurativo" e il pagamento rigoroso "Man mano" e il rischio di risposte più lente a causa di improvvisi incrementi di richiesta.

## <a name="monitoring-tracing-and-logging"></a>Monitoraggio, traccia e registrazione

Un aspetto spesso trascurato di DevOps è il monitoraggio delle applicazioni al termine della distribuzione. È importante avere una strategia per il monitoraggio di funzioni senza server. Il problema principale è spesso correlato o riconoscibile quando un utente chiama più funzioni come parte della stessa interazione. La maggior parte delle piattaforme senza server consente la registrazione della console che può essere importata in strumenti di terze parti. Sono disponibili anche opzioni per automatizzare la raccolta dei dati di telemetria, generare e tenere traccia degli ID di correlazione e monitorare azioni specifiche per fornire informazioni dettagliate. Azure fornisce la [piattaforma di Application Insights](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) avanzata per il monitoraggio e l'analisi.

## <a name="inter-service-dependencies"></a>Dipendenze tra servizi

Un'architettura senza server può includere funzioni che si basano su altre funzioni. In realtà, non è insolito in un'architettura senza server avere più servizi chiamati tra loro come parte di un'interazione o di una transazione distribuita. Per evitare un accoppiamento forte, è consigliabile che i servizi non facciano riferimento a vicenda direttamente. Quando è necessario modificare l'endpoint per un servizio, i riferimenti diretti possono comportare un refactoring principale. Una soluzione consigliata consiste nel fornire un meccanismo di individuazione dei servizi, ad esempio un registro, che fornisca l'endpoint appropriato per un tipo di richiesta. Un'altra soluzione consiste nell'utilizzare servizi di messaggistica come code o argomenti per la comunicazione tra servizi.

## <a name="managing-failure-and-providing-resiliency"></a>Gestione degli errori e fornitura della resilienza

È anche importante prendere in considerazione il *modello di interruttore*: se, per qualche motivo, un servizio continua a non riuscire, non è consigliabile chiamare tale servizio ripetutamente. Viene invece chiamato un servizio alternativo o viene restituito un messaggio finché non viene ristabilita l'integrità del servizio dipendente. L'architettura senza server deve prendere in considerazione la strategia per la risoluzione e la gestione delle dipendenze tra servizi.

Per continuare il modello di interruttore, i servizi devono essere a tolleranza d'errore e resilienti. La tolleranza di errore si riferisce alla capacità dell'applicazione di continuare l'esecuzione anche dopo che sono state rilevate eccezioni impreviste o Stati non validi. La tolleranza di errore è in genere una funzione del codice stesso e del modo in cui viene scritta per gestire le eccezioni. La resilienza si riferisce al modo in cui l'app è in fase di recupero da errori. La resilienza è spesso gestita dalla piattaforma senza server. La piattaforma dovrebbe essere in grado di creare una nuova istanza della funzione senza server in caso di errore di uno esistente. La piattaforma dovrebbe inoltre essere sufficientemente intelligente da interrompere la creazione di nuove istanze in caso di errore di ogni nuova istanza.

Per altre informazioni, vedere [implementazione del modello](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md)di interruttore.

## <a name="versioning-and-greenblue-deployments"></a>Controllo delle versioni e distribuzioni di verde/blu

Un vantaggio principale di senza server è la possibilità di aggiornare una funzione specifica senza dover ridistribuire l'intera applicazione. Affinché gli aggiornamenti abbiano esito positivo, è necessario eseguire il controllo delle versioni delle funzioni in modo che i servizi che li chiamano vengano indirizzati alla versione corretta del codice. È importante anche una strategia per la distribuzione di nuove versioni. Un approccio comune consiste nell'usare "distribuzioni verdi/blu". La distribuzione verde è la funzione corrente. Una nuova versione "blu" viene distribuita nell'ambiente di produzione e testata. Quando il test viene superato, vengono scambiate le versioni verde e blu, in modo da rendere disponibile la nuova versione. Se vengono rilevati problemi, è possibile scambiarli nuovamente. Per supportare le distribuzioni di versioni verdi e blu, è necessario usare una combinazione di funzioni per la modifica delle versioni e l'utilizzo della piattaforma senza server per gestire le distribuzioni.

>[!div class="step-by-step"]
>[Precedente](serverless-architecture.md)
>[successivo](serverless-design-examples.md)
