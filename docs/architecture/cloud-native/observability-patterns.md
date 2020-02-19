---
title: Modelli di osservabilità
description: Modelli di osservabilità per le applicazioni native del cloud
ms.date: 02/05/2020
ms.openlocfilehash: a821235835b4553760b19887d500a29ca75e133e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448521"
---
# <a name="observability-patterns"></a>Modelli di osservabilità

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Così come i modelli sono stati sviluppati per facilitare il layout del codice nelle applicazioni, esistono modelli per le applicazioni operative in modo affidabile. Sono emersi tre modelli utili per la gestione delle applicazioni: **registrazione**, **monitoraggio**e **avvisi**.

## <a name="when-to-use-logging"></a>Quando usare la registrazione

Indipendentemente dall'attenzione, le applicazioni si comportano quasi sempre in modi imprevisti nell'ambiente di produzione. Quando gli utenti segnalano problemi con un'applicazione, è molto utile essere in grado di vedere cosa stava accadendo con l'app quando si è verificato il problema. Uno dei modi più efficaci e reali per acquisire informazioni sulle operazioni eseguite da un'applicazione mentre è in esecuzione è quello di fare in modo che l'applicazione scriva il risultato dell'operazione. Questo processo è noto come registrazione. Ogni volta che si verificano errori o problemi in produzione, l'obiettivo è quello di riprodurre le condizioni in cui si sono verificati gli errori in un ambiente non di produzione. La corretta registrazione offre una guida di orientamento che gli sviluppatori possono seguire per duplicare i problemi in un ambiente che può essere testato e sperimentato.

### <a name="challenges-when-logging-with-cloud-native-applications"></a>Problemi durante la registrazione con applicazioni native del cloud

Nelle applicazioni tradizionali, i file di log vengono in genere archiviati nel computer locale. In realtà, nei sistemi operativi simili a UNIX è definita una struttura di cartelle che contenga tutti i log, in genere in `/var/log`.

![la registrazione in un file in un'app monolitica.](./media/single-monolith-logging.png)
**figura 7-1**. Registrazione in un file in un'app monolitica.

L'utilità di registrazione in un file flat in un singolo computer è notevolmente ridotta in un ambiente cloud. Le applicazioni che producono log potrebbero non avere accesso al disco locale o il disco locale può essere estremamente temporaneo perché i contenitori vengono mescolati intorno ai computer fisici. Anche una semplice scalabilità verticale di applicazioni monolitiche in più nodi può rendere difficile l'individuazione del file di log appropriato basato su file.

![la registrazione ai file in un'app monolitica ridimensionata.](./media/multiple-node-monolith-logging.png)
**figura 7-2**. Accesso ai file in un'app monolitica ridimensionata.

Le applicazioni native del cloud sviluppate usando un'architettura di microservizi presentano anche alcune problemi per i logger basati su file. È ora possibile che le richieste utente si estendano su più servizi che vengono eseguiti in computer diversi e possono includere funzioni senza server senza accesso a una file system locale. Sarebbe molto difficile correlare i log di un utente o di una sessione tra questi numerosi servizi e computer.

![la registrazione in file locali in un'app di microservizi.](./media/local-log-file-per-service.png)
**figura 7-3**. Registrazione in file locali in un'app di microservizi.

Infine, il numero di utenti in alcune applicazioni native del cloud è elevato. Si supponga che ogni utente generi un centinaio di righe di messaggi di log durante l'accesso a un'applicazione. In isolamento, è gestibile, ma si moltiplicano gli utenti di 100.000 e il volume dei log diventa sufficientemente grande che siano necessari strumenti specializzati per supportare l'uso efficace dei log.

### <a name="logging-in-cloud-native-applications"></a>Registrazione nelle applicazioni native del cloud

Ogni linguaggio di programmazione dispone di strumenti che consentono di scrivere log e in genere il sovraccarico per la scrittura di questi log è basso. Molte delle librerie di registrazione consentono di registrare diversi tipi di criticità, che possono essere ottimizzate in fase di esecuzione. Ad esempio, la [libreria Serilog](https://serilog.net/) è una famosa libreria di registrazione strutturata per .NET che fornisce i livelli di registrazione seguenti:

* Dettagliato
* Debug
* Informazioni
* Avviso
* Errore
* Fatal

Questi livelli di log diversi forniscono la granularità nella registrazione. Quando l'applicazione funziona correttamente nell'ambiente di produzione, può essere configurata in modo da registrare solo i messaggi importanti. Quando l'applicazione si comporta in modo errato, è possibile aumentare il livello di registrazione, in modo che vengano raccolti log più dettagliati. Questo bilancia le prestazioni in base alla facilità di debug.

Le prestazioni elevate degli strumenti di registrazione e della tunability del livello di dettaglio devono incoraggiare gli sviluppatori a registrarsi di frequente. Molti prediligono un modello di registrazione della voce e dell'uscita di ogni metodo. Questo approccio può sembrare eccessivo, ma non è frequente che gli sviluppatori vogliano una minore registrazione. In realtà, non è insolito eseguire le distribuzioni per l'unico scopo di aggiungere la registrazione intorno a un metodo problematico. Errore sul lato di una registrazione eccessiva e non su un importo troppo basso. È possibile utilizzare alcuni strumenti per fornire automaticamente questo tipo di registrazione.

A causa dei problemi associati all'uso di log basati su file nelle app native del cloud, i log centralizzati sono preferiti. I log vengono raccolti dalle applicazioni e spediti a un'applicazione di registrazione centrale che indicizza e archivia i log. Questa classe di sistema può inserire decine di gigabyte di log ogni giorno.

È inoltre utile seguire alcune procedure standard per la creazione di registrazioni che si estendono su molti servizi. Ad esempio, la generazione di un [ID di correlazione](https://blog.rapid7.com/2016/12/23/the-value-of-correlation-ids/) all'inizio di un'interazione lunga e la relativa registrazione in ogni messaggio correlato all'interazione, semplifica la ricerca di tutti i messaggi correlati. È sufficiente trovare un solo messaggio ed estrarre l'ID di correlazione per trovare tutti i messaggi correlati. Un altro esempio è garantire che il formato di log sia lo stesso per ogni servizio, indipendentemente dalla lingua o dalla libreria di registrazione utilizzata. Questa standardizzazione rende molto più semplice la lettura dei log. La figura 7-4 illustra il modo in cui un'architettura di microservizi può sfruttare la registrazione centralizzata come parte del proprio flusso di lavoro.

![log da varie origini vengono inseriti in un archivio di log centralizzato.](./media/centralized-logging.png)
**figura 7-4**. I log da varie origini vengono inseriti in un archivio di log centralizzato.

## <a name="challenges-with-detecting-and-responding-to-potential-app-health-issues"></a>Problemi di rilevamento e risposta a potenziali problemi di integrità delle app

Alcune applicazioni non sono cruciali. È possibile che vengano usati solo internamente e, quando si verifica un problema, l'utente può contattare il team responsabile e l'applicazione può essere riavviata. Tuttavia, i clienti hanno spesso aspettative più elevate per le applicazioni che utilizzano. È necessario sapere quando si verificano problemi con l'applicazione *prima* che gli utenti eseguano o prima di inviare una notifica agli utenti. In caso contrario, è possibile che si verifichi un problema quando si nota un diluvio indesiderato di post di social media che descrivono l'applicazione o anche la propria organizzazione.

Di seguito sono riportati alcuni scenari che può essere necessario considerare:

- Un servizio nell'applicazione continua a non riuscire e a riavviare, causando risposte lente intermittenti.
- In alcuni momenti della giornata, il tempo di risposta dell'applicazione è lento.
- Dopo una distribuzione recente, il carico sul database è stato triplicato.

Implementate correttamente, il monitoraggio può consentire di conoscere le condizioni che causano problemi, consentendo di risolvere le condizioni sottostanti prima di ottenere un impatto significativo sugli utenti.

### <a name="monitoring-cloud-native-apps"></a>Monitoraggio delle app native del cloud

Alcuni sistemi di registrazione centralizzati accettano un ruolo aggiuntivo nella raccolta dei dati di telemetria all'esterno dei log puri. Possono raccogliere le metriche, ad esempio il tempo necessario per eseguire una query sul database, il tempo medio di risposta da un server Web e anche le medie di carico della CPU e la quantità di memoria richieste dal sistema operativo. Insieme ai log, questi sistemi possono fornire una visualizzazione olistica dell'integrità dei nodi del sistema e dell'applicazione nel suo complesso.

Le funzionalità di raccolta delle metriche degli strumenti di monitoraggio possono anche essere trasmesse manualmente dall'interno dell'applicazione. I flussi aziendali con particolare interesse, ad esempio i nuovi utenti che effettuano l'iscrizione o gli ordini, possono essere instrumentati in modo da incrementare un contatore nel sistema di monitoraggio centrale. Questa operazione sblocca gli strumenti di monitoraggio in modo da non solo monitorare l'integrità dell'applicazione, ma l'integrità dell'azienda.

Le query possono essere create negli strumenti di aggregazione dei log per cercare determinate statistiche o modelli, che possono essere visualizzati in formato grafico, nei dashboard personalizzati. Spesso, i team investono in schermi di grandi dimensioni e montati in modo che ruotino le statistiche correlate a un'applicazione. In questo modo, è semplice vedere i problemi non appena si verificano.

Gli strumenti di monitoraggio nativi del cloud forniscono dati di telemetria in tempo reale e informazioni dettagliate sulle app, indipendentemente dal fatto che si tratti di applicazioni monolitiche a processo singolo o architetture di microservizi distribuiti. Sono inclusi gli strumenti che consentono la raccolta di dati dall'app, oltre a strumenti per l'esecuzione di query e la visualizzazione di informazioni sull'integrità dell'app.

## <a name="challenges-with-reacting-to-critical-problems-in-cloud-native-apps"></a>Problemi con la reazione a problemi critici nelle app native del cloud

Se è necessario reagire ai problemi con l'applicazione, è necessario un modo per avvisare il personale appropriato. Si tratta del terzo modello di osservabilità delle applicazioni native del cloud e dipende dalla registrazione e dal monitoraggio. È necessario che l'applicazione disponga di una registrazione per consentire la diagnosi dei problemi e, in alcuni casi, per inserire gli strumenti di monitoraggio. È necessario il monitoraggio per aggregare le metriche dell'applicazione e i dati di integrità in un'unica posizione. Una volta stabilita questa, è possibile creare regole che attiveranno avvisi quando determinate metriche non rientrano nei livelli accettabili.

In genere, gli avvisi sono sovrapposti al monitoraggio in modo che determinate condizioni attivino avvisi appropriati per notificare ai membri del team problemi urgenti. Di seguito sono riportati alcuni scenari che possono richiedere avvisi:

- Uno dei servizi dell'applicazione non risponde dopo 1 minuto di tempo di inattività.
- L'applicazione sta restituendo risposte HTTP non riuscite a più dell'1% delle richieste.
- Il tempo medio di risposta dell'applicazione per gli endpoint chiave supera 2000 ms.

### <a name="alerts-in-cloud-native-apps"></a>Avvisi nelle app native del cloud

È possibile creare query sugli strumenti di monitoraggio per individuare le condizioni di errore note. Ad esempio, le query possono eseguire ricerche nei log in ingresso per indicazioni sul codice di stato HTTP 500, che indica un problema in un server Web. Non appena viene rilevata una di queste, è possibile inviare un messaggio di posta elettronica o un SMS al proprietario del servizio di origine che può iniziare a esaminare.

In genere, tuttavia, un singolo errore 500 non è sufficiente per determinare se si è verificato un problema. Potrebbe significare che un utente ha digitato la password in modo errato o ha immesso dati in formato non valido. È possibile creare query di avviso in modo che vengano attivate solo quando vengono rilevati un numero di errori 500 superiore alla media.

Uno dei modelli più dannosi per gli avvisi consiste nel generare un numero eccessivo di avvisi per l'analisi da parte degli utenti. I proprietari del servizio diventeranno rapidamente desensibili agli errori che hanno esaminato in precedenza e che risultano benigni. Quindi, quando si verificano errori reali, andranno persi nel rumore di centinaia di falsi positivi. La parabola del [ragazzo che piangeva Wolf](https://en.wikipedia.org/wiki/The_Boy_Who_Cried_Wolf) viene spesso rilasciata agli elementi figlio per avvertire questi rischi. È importante assicurarsi che gli avvisi generati siano indicativi di un problema reale.

>[!div class="step-by-step"]
>[Precedente](monitoring-health.md)
>[Successivo](logging-with-elastic-stack.md)
