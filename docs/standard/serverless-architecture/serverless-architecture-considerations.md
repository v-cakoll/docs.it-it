---
title: Considerazioni sull'architettura senza server - App senza server
description: Comprendere le sfide di progettazione di applicazioni senza server, da un archivio permanente per la scalabilità di gestione dello stato di registrazione e traccia e diagnostica.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b12a09c0fcef7e7ff954a3f959fb9e3080a6e859
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155064"
---
# <a name="serverless-architecture-considerations"></a>Considerazioni sull'architettura senza server

Adottare un'architettura senza server dotati di alcuni problemi. In questa sezione illustra alcune delle considerazioni più comune da tenere presenti. Tutti questi problemi sono soluzioni. Come con tutte le scelte di architettura, la decisione di operatività senza server deve essere presa solo dopo aver considerato con attenzione i vantaggi e svantaggi. A seconda delle esigenze dell'applicazione, è possibile decidere che la soluzione ideale per alcuni componenti non è un'implementazione senza server.

## <a name="managing-state"></a>La gestione dello stato

Le funzioni senza server, come i microservizi in generale, sono senza state per impostazione predefinita. Stato evitando Abilita senza server per essere temporanei, per la scalabilità orizzontale e per offrire resilienza senza un punto centrale di errore. In alcuni casi, i processi aziendali richiedono lo stato. Se il processo richiede lo stato, sono disponibili due opzioni. È possibile adottare un modello diverso da quello senza server, o interagire con un servizio separato che fornisce lo stato. Aggiunta dello stato può complicare la soluzione e rendono più difficile a scalabilità e potenzialmente creare un singolo punto di guasto. Valutare attentamente se la funzione richiede assolutamente dello stato. Se la risposta è "Sì", determinare se è tuttavia utile per l'implementazione con senza server.

Esistono diverse soluzioni adottare stato senza compromettere i vantaggi degli strumenti senza server. Alcune delle soluzioni più comuni includono:

* Usare un archivio dati temporaneo o una cache distribuita, ad esempio Redis
* Stato di Store in un database, ad esempio SQL o COSMOS DB
* Gestire lo stato tramite un motore del flusso di lavoro come funzioni permanenti

La conclusione è che è necessario essere consapevoli della necessità di una gestione dello stato all'interno di processi che stai valutando da implementare grazie a senza server.

## <a name="long-running-processes"></a>Processi a esecuzione prolungata

Molti vantaggi degli strumenti senza server si basano sui processi in corso temporanee. Tempi di esecuzione brevi rendono più semplice per il provider senza server liberare risorse come funzioni di funzioni end e la condivisione tra gli host. La maggior parte dei provider di servizi cloud limitare il tempo complessivo che di funzione può essere eseguita per circa 10 minuti. Se il processo potrebbe richiedere più tempo, è possibile considerare un'implementazione alternativa.

Esistono alcune eccezioni e le soluzioni. Una soluzione può consistere per interrompere il processo in componenti più piccoli che singolarmente richiedono meno tempo per l'esecuzione. Se il processo venga eseguito lungo a causa delle dipendenze, è anche possibile considerare un flusso di lavoro asincrono tramite una soluzione come funzioni permanenti. Funzioni permanenti sospendere e mantengono lo stato del processo mentre è in attesa di un processo esterno per terminare. Gestione asincrona riduce il tempo che viene eseguito il processo effettivo.

## <a name="startup-time"></a>Tempo di avvio

Un potenziale problema con le implementazioni senza server è il tempo di avvio. Per conservare risorse, molti provider senza server creare infrastruttura "su"richiesta. Quando viene attivata una funzione senza server dopo un periodo di tempo, le risorse per ospitare la funzione potrebbe essere necessario creare o riavviato. In alcune situazioni, avvii a freddo potrebbero causare ritardi di alcuni secondi. Tempo di avvio varia tra provider e i livelli di servizio. Esistono diversi approcci per il tempo di avvio di indirizzo, se è importante per ridurre al minimo per il successo dell'app.

* Alcuni provider consentono agli utenti di pagare per i livelli di servizio che garantiscono l'infrastruttura è "always on".
* Implementare un meccanismo keep-alive (ping all'endpoint di mantenerlo "attivi").
* Utilizzare l'orchestrazione come Kubernetes con un approccio di funzione nei contenitori (l'host è già in esecuzione in modo attivando nuove istanze è estremamente veloce).

## <a name="database-updates-and-migrations"></a>Le migrazioni e aggiornamenti del database

Un vantaggio del codice senza server consiste nel fatto che è possibile rilasciare nuove funzioni senza dover ridistribuire l'intera applicazione. Questo vantaggio può diventare uno svantaggio quando è coinvolto un database relazionale. Le modifiche agli schemi di database sono difficili da sincronizzare con gli aggiornamenti senza server. Problematiche aggiuntive vengono poste quando le cose vanno male e devono essere eseguito il rollback le modifiche. L'integrità dei dati è uno dei motivi che è una procedura consigliata per i microservizi e le funzioni senza server che possiedono i propri dati. È possibile distribuire le modifiche come singola unità di calcolo e di dati. La realtà è che molti sistemi legacy funzionalità di un database back-end di grandi dimensioni che deve essere riconciliato con l'architettura senza server.

Un approccio comune per risolvere il controllo delle versioni dello schema è per evitare di modificare le proprietà esistenti e le colonne, ma invece aggiungere le nuove informazioni. Si consideri ad esempio una modifica per passare da un valore booleano "completato" flag per un elenco di attività a una "Data di completamento". Invece di rimuovere il campo obsoleto, le modifiche al database saranno:

1. Aggiungere un campo nuovo "Data completamento".
1. Trasforma il campo booleano "completato" a una funzione calcolata che stabilisce se la data di completamento è successiva alla data corrente.
1. Aggiungere un trigger per impostare la data di completamento alla data corrente quando il valore booleano completato è impostato su true.

La sequenza di modifiche assicura che il codice legacy continui a funzionare "così com'è", mentre le funzioni senza server più recenti possono sfruttare i vantaggi del nuovo campo.

Per altre informazioni sui dati nelle architetture senza server, vedere [sfide e soluzioni per la gestione dei dati distribuiti](../microservices-architecture/architect-microservice-container-applications/distributed-data-management.md).

## <a name="scaling"></a>Ridimensionamento

Si tratta di un preconcetto comune che senza server non significa "Nessun server". È in effetti "meno server". Il fatto vi è che un'infrastruttura di backup è importante comprendere per quanto riguarda la scalabilità. Le piattaforme più senza server offrono un set di controlli per la gestione come l'infrastruttura deve aumentare quando si aumenta la densità di eventi. È possibile scegliere tra un'ampia gamma di opzioni, ma la strategia può variare a seconda della funzione. Inoltre, le funzioni sono in genere eseguite con un host correlate, in modo che le funzioni nello stesso host hanno le stesse opzioni di scalabilità. Di conseguenza è necessario organizzare e intervenirvi quali funzioni sono ospitate in base a requisiti di scalabilità.

Le regole specificano spesso come scalabilità verticale (aumentare le risorse host) e scalabilità orizzontale (aumentare il numero di istanze dell'host) in base a diversi parametri. I trigger per le scale potrebbero includere pianificazione, frequenza delle richieste, utilizzo della CPU e utilizzo della memoria. Prestazioni più elevate spesso ha un costo maggiore. Gli approcci meno costosi, in base al consumo non possono scalare rapidamente quando la frequenza delle richieste potrebbe trovarsi improvvisamente aumentare. Non c'è un compromesso tra pagare in anticipo "assicurata" e pagare esclusivamente "come si go" ed rischiando risposte più lente a causa dell'improvviso aumento della domanda.

## <a name="monitoring-tracing-and-logging"></a>La registrazione, traccia e monitoraggio

Un aspetto spesso sottovalutato della metodologia DevOps è il monitoraggio delle applicazioni dopo la distribuzione. È importante disporre di una strategia per il monitoraggio funzioni senza server. Il problema maggiore consiste spesso correlazione oppure il riconoscimento quando un utente chiama le funzioni più come parte dell'interazione stessa. Piattaforme senza server più consentono console registrazione che può essere importati in strumenti di terze parti. Sono disponibili anche opzioni per automatizzare la raccolta dei dati di telemetria, generare e registrare gli ID di correlazione e monitorare le azioni specifiche per fornire informazioni dettagliate. Azure offre l'avanzata [piattaforma di Application Insights](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) per il monitoraggio e analitica.

## <a name="inter-service-dependencies"></a>Dipendenze tra servizi

Un'architettura senza server può includere funzioni che si basano su altre funzioni. Infatti, non è insolito in un'architettura senza server per avere più servizi comunicano tra loro come parte di una transazione distribuita o di interazione. Per evitare l'accoppiamento forte, è consigliabile che i servizi non di riferimento tra loro direttamente. Quando è necessario modificare l'endpoint per un servizio, può comportare principali refactoring riferimenti diretti. Soluzione suggerita è fornire un meccanismo di individuazione del servizio, ad esempio un registro di sistema, che fornisce il punto di fine appropriato per un tipo di richiesta. Un'altra soluzione consiste nello sfruttare servizi di messaggistica come code o argomenti per la comunicazione tra servizi.

## <a name="managing-failure-and-providing-resiliency"></a>La gestione di errori e fornire resilienza

È anche importante tenere in considerazione la *schema circuit breaker*: Se, per qualche motivo, un servizio continua ad avere esito negativo, non è consigliabile chiamare più volte tale servizio. Al contrario, viene chiamato un servizio alternativo o un messaggio restituito fino a quando non viene ristabilita l'integrità dei servizi dipendenti. L'architettura senza server deve prendere in considerazione la strategia per la risoluzione e la gestione delle dipendenze tra servizi.

Per continuare il modello a interruttore, servizi devono essere resilienti e a tolleranza di errore. Tolleranza di errore si riferisce alla capacità dell'applicazione per continuare l'esecuzione anche dopo le eccezioni impreviste o stati non validi vengono rilevati. Tolleranza di errore è in genere una funzione del codice stesso e che la modalità è scritta gestire le eccezioni. Resilienza fa riferimento al modo in cui in grado di supportare l'app è in il ripristino da errori. La resilienza è spesso gestita dalla piattaforma senza server. La piattaforma deve essere in grado di creare rapidamente una nuova istanza della funzione senza server quando si verifica un errore di quello esistente. La piattaforma deve essere anche abbastanza intelligente da arrestare attivando nuove istanze quando ha esito negativo di ogni nuova istanza.

Per altre informazioni, vedere [implementazione dello schema Circuit Breaker](../microservices-architecture/implement-resilient-applications/implement-circuit-breaker-pattern.md).

## <a name="versioning-and-greenblue-deployments"></a>Distribuzioni blue/green e controllo delle versioni

Dei principali vantaggi degli strumenti senza server è la possibilità di eseguire l'aggiornamento di una funzione specifica senza dover ridistribuire l'intera applicazione. Per l'aggiornamento abbia esito positivo, le funzioni devono essere con controllo delle versioni in modo che servizi chiamandole vengono indirizzati alla versione corretta del codice. È importante anche una strategia per la distribuzione di nuove versioni. Un approccio comune consiste nell'usare "verde/blu le distribuzioni." La distribuzione verde è la funzione corrente. Una nuova versione "blu" viene distribuita nell'ambiente di produzione e testata. Durante il test passa, le versioni di verde e blue vengono scambiate in modo che la nuova versione viene fornito in tempo reale. Se vengono rilevati eventuali problemi, è possibile scambiare nuovamente. Il supporto di controllo delle versioni e le distribuzioni blue/green richiede una combinazione di creazione di funzioni per supportare le modifiche di versione e l'utilizzo con la piattaforma senza server per gestire le distribuzioni. Un possibile approccio consiste nell'utilizzare i proxy, che sono descritte nel [piattaforma senza server Azure](azure-functions.md#proxies) capitolo.

>[!div class="step-by-step"]
>[Precedente](serverless-architecture.md)
>[Successivo](serverless-design-examples.md)