---
title: Progettazione di un'applicazione orientata ai servizi microservizio
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Progettazione di un'applicazione orientata ai servizi microservizio
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1e1dc919c7e35580576c86b4cf9872b4f8cea2c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="designing-a-microservice-oriented-application"></a>Progettazione di un'applicazione orientata ai servizi microservizio

Questa sezione viene illustrato lo sviluppo di un'applicazione del ipotetica enterprise sul lato server.

## <a name="application-specifications"></a>Specifiche dell'applicazione

L'applicazione del ipotetica gestisce le richieste dalla logica di business in esecuzione, l'accesso ai database e quindi restituire risposte HTML, JSON o XML. Si indicherà che l'applicazione deve supportare un'ampia gamma di client, inclusi i browser desktop che eseguono applicazioni a pagina singola (stabilimenti termali), App web tradizionali, App web per dispositivi mobili e App native per dispositivi mobili. L'applicazione potrebbe inoltre esporre un'API per terze parti di utilizzare. Inoltre deve essere in grado di integrare in modo asincrono, il relativo microservizi o applicazioni esterne in modo che l'approccio consentirà di resilienza di microservizi in caso di errori parziali.

L'applicazione è costituita da questi tipi di componenti:

-   Componenti di presentazione. Questi sono responsabili per l'interfaccia utente di gestione e utilizzo di servizi remoti.

-   Dominio o la regola business. Si tratta di logica di dominio dell'applicazione.

-   Logica di accesso ai database. Si tratta di componenti di accesso ai dati responsabile per l'accesso ai database (SQL o NoSQL).

-   Logica di integrazione dell'applicazione. Sono inclusi un canale di messaggistica, soprattutto in base a gestori di messaggi.

L'applicazione richiederà ad alta scalabilità, consentendo la sottosistemi verticale per scalare in orizzontale in modo autonomo, perché alcuni sottosistemi richiedono maggiore scalabilità rispetto ad altri.

L'applicazione deve essere in grado di essere distribuita in più ambienti di infrastruttura (più cloud pubblici e locali) e deve essere idealmente multipiattaforma, in grado di spostarsi facilmente da Linux a Windows (o viceversa).

## <a name="development-team-context"></a>Contesto del team di sviluppo

Si presuppongono inoltre le seguenti informazioni sul processo di sviluppo per l'applicazione:

-   Sono presenti più team di sviluppo con particolare attenzione ad aree diverse di business dell'applicazione.

-   Nuovi membri del team devono diventare rapidamente produttivi e l'applicazione deve essere facile da comprendere e modificare.

-   L'applicazione avrà un andamento a lungo termine e regole di business in continua evoluzione.

-   È necessario una buona manutenibilità a lungo termine, ovvero con flessibilità durante l'implementazione di nuove modifiche in futuro pur essendo in grado di aggiornare più sottosistemi con un impatto minimo sugli altri sottosistemi.

-   Si desidera integrazione continua pratica e la distribuzione continua dell'applicazione.

-   Si desidera sfruttare i vantaggi di nuove tecnologie (Framework, linguaggi di programmazione e così via) durante l'evoluzione dell'applicazione. Non si desidera rendere migrazioni complete dell'applicazione durante lo spostamento in nuove tecnologie, poiché che potrebbe comportare costi elevati e impatto della prevedibilità e della stabilità dell'applicazione.

## <a name="choosing-an-architecture"></a>Scelta dell'architettura

Quale deve essere l'architettura di distribuzione dell'applicazione? Le specifiche per l'applicazione, insieme al contesto di sviluppo, suggeriscono che è necessario progettare l'applicazione per la scomposizione in sottosistemi autonomi sotto forma di microservizi in collaborazione e contenitori, dove un microservizio è un contenitore.

In questo approccio, ogni servizio (contenitore) implementa un set di funzioni coesiva e ristretto correlati. Ad esempio, un'applicazione può essere costituito da servizi come il servizio di catalogo, ordinamento service, servizio carrello, servizio profili utente e così via.

Microservizi comunicano utilizzando protocolli quali HTTP (REST), ma anche in modo asincrono, ovvero AMQP, laddove possibile, soprattutto quando la propagazione Aggiorna con eventi di integrazione.

Microservizi vengono sviluppati e distribuiti come contenitori indipendentemente uno da altro. Ciò significa che un team di sviluppo può essere lo sviluppo e distribuzione di un determinato microservizio senza alcun impatto sugli altri sottosistemi.

Ogni microservizio dispone del proprio database, in modo che possa essere completamente separato da altri microservizi. Se necessario, la coerenza tra i database da diversi microservizi avviene mediante gli eventi di integrazione a livello di applicazione (tramite un bus di eventi logici), come gestiti nei comandi e Query Responsibility Segregation (CQRS). Per questo motivo, i vincoli di business devono prevedere l'eventualità di coerenza finale tra le più microservizi e i relativi database.

### <a name="eshoponcontainers-a-reference-application-for-net-core-and-microservices-deployed-using-containers"></a>eShopOnContainers: un'applicazione di riferimento per .NET Core e microservizi distribuito utilizzando contenitori

In modo che sia possibile concentrarsi sull'architettura e le tecnologie anziché pensare a un dominio di business hypothetic che potrebbe non essere noto, è stato selezionato un dominio aziendale noto, vale a dire, un'applicazione di e-commerce semplificata (e-bar) che presenta un catalogo di i prodotti, accetta gli ordini dei clienti, verifica di inventario e consente di eseguire altre funzioni di business. È disponibile in questo codice sorgente dell'applicazione contenitore in base il [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) repository GitHub.

L'applicazione è costituita da più sottosistemi, inclusi diversi archivio dell'interfaccia utente front-end (un'applicazione Web e una app native per dispositivi mobili), insieme alla microservizi back-end e i contenitori per tutte le operazioni necessarie sul lato server. Figura 8-1 è illustrata l'architettura dell'applicazione di riferimento.

![](./media/image1.png)

**Figura 8-1**. Il eShopOnContainers riferimento applicazione, che mostra una comunicazione client-a-microservizio diretta e il bus di eventi

**Ambiente di hosting**. Nella figura 8-1, vedrai diversi contenitori distribuiti all'interno di un singolo host Docker. Che sarebbe durante la distribuzione in un singolo host Docker con docker-comporre il comando. Tuttavia, se si utilizzando l'agente di orchestrazione o cluster di contenitore, ogni contenitore può essere eseguito in un host diverso (nodo) e qualsiasi nodo potrebbe essere in esecuzione un numero qualsiasi di contenitori, come è illustrato in precedenza nella sezione architettura.

**Architettura di comunicazione**. L'applicazione eShopOnContainers utilizza due tipi di comunicazione, a seconda del tipo dell'azione funzionale (query e aggiornamenti e le transazioni):

-   Comunicazione client-a-microservizio diretta. Per le query e viene utilizzato per l'accettazione di aggiornamento o i comandi transazionali dalle App client.

-   Comunicazione asincrona basato su eventi. Questo errore si verifica a un bus di eventi per distribuire gli aggiornamenti in microservizi o per l'integrazione con applicazioni esterne. Il bus di eventi può essere implementato con qualsiasi tecnologia di infrastruttura di broker di messaggistica come RabbitMQ o tramite bus di servizio livello superiore come Azure Service Bus, NServiceBus, MassTransit o Brighter.

L'applicazione viene distribuita come un set di microservizi sotto forma di contenitori. Le applicazioni client possono comunicare con i contenitori, nonché la comunicazione tra microservizi. Come accennato, questa architettura iniziale utilizza un'architettura di comunicazione client-a-microservizio diretta, il che significa che un'applicazione client può richiedere a ognuna di microservizi direttamente. Ogni microservizio dispone di un endpoint pubblico come https://servicename.applicationname.companyname. Se necessario, ogni microservizio può utilizzare una porta TCP diversa. Nell'ambiente di produzione, che consente il mapping di URL di bilanciamento del carico degli microservizi, che distribuisce le richieste tra le istanze disponibili microservizio.

**Nota importante in vs API Gateway. Comunicazione diretta in eShopOnContainers.** Come illustrato nella sezione architettura di questa Guida, l'architettura di comunicazione client-a-microservizio diretta può presentare svantaggi quando si compila un'applicazione basata su microservizio grande e complessa. Ma può essere adeguata per una piccola applicazione, ad esempio nel eShopOnContainers applicazione, in cui l'obiettivo è di concentrarsi su un recupero più semplice avviata applicazioni basate sul contenitore Docker e non si desidera creare un singolo Gateway monolitico API che possono influire le autonomia di sviluppo di microservizi.

Tuttavia, se si intende progettare un'applicazione basata su microservizio grandi dimensioni con dozzine di microservizi, è consigliabile prendere in considerazione il modello API Gateway, come illustrato nella sezione architettura.
Una volta pensando di applicazioni in ambienti di produzione e aspetti apportate appositamente per i client remoti, è possibile effettuare il refactoring questa decisione dell'architettura. Presenza di più gateway API personalizzato in base al fattore di forma delle App client può offrire vantaggi per quanto riguarda l'aggregazione di dati diversi per ciascuna applicazione client inoltre è possibile nascondere microservizi interno o le API per le applicazioni client e autorizzare in tale livello di singolo. 

Tuttavia e come indicato, fare attenzione alle contro grandi e monolitico gateway API che potrebbe terminare l'autonomia di sviluppo di microservizi il.

### <a name="data-sovereignty-per-microservice"></a>Sovranità di dati per ogni microservizio

Nell'applicazione di esempio, ogni microservizio possiede il proprio database o l'origine dati e ogni database o origine dati viene distribuita come un altro contenitore. Questa decisione progettuale effettuata solo per semplificare lo sviluppatore può ottenere il codice da GitHub, clonarla e aprirlo in Visual Studio o Visual Studio Code. O, in alternativa, semplifica inoltre compilare le immagini Docker personalizzate usando .NET Core CLI e l'interfaccia CLI di Docker e quindi distribuire ed eseguirli in un ambiente di sviluppo di Docker. In entrambi i casi, l'utilizzo di contenitori per i dati di origini consente agli sviluppatori di compilare e distribuire in pochi minuti senza dover eseguire il provisioning di un database esterno o qualsiasi altra origine dati con dipendenze rigide sull'infrastruttura (cloud o locale).

In un ambiente di produzione reali, per la disponibilità elevata e scalabilità, i database dovrebbero essere basati su server di database nel cloud o locale, ma non nei contenitori.

Pertanto, le unità di distribuzione di microservizi e anche per i database in questa applicazione, sono contenitori di Docker e l'applicazione di riferimento è un'applicazione multi-contenitore basata sul modello microservizi principi.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **eShopOnContainers repository GitHub. Codice sorgente per l'applicazione di riferimento**
    *https://aka.ms/eShopOnContainers/*

## <a name="benefits-of-a-microservice-based-solution"></a>Vantaggi di una soluzione basata su microservizio

Una soluzione di base microservizio simile al seguente presenta numerosi vantaggi:

**Ogni microservizio è relativamente piccolo, semplice da gestire e sviluppare**. In particolare:

-   È facile per uno sviluppatore di comprendere e iniziare rapidamente con buona produttività.

-   Contenitori di avvio veloce, che consente agli sviluppatori più produttivi.

-   Un IDE come Visual Studio è possibile caricare i progetti di piccole dimensioni veloci, rendendo la produttività agli sviluppatori.

-   Ogni microservizio può essere progettato, sviluppato e distribuito in modo indipendente da altri microservizi, che offre flessibilità in quanto è più facile da distribuire nuove versioni di microservizi frequentemente.

**È possibile scalare le singole aree dell'applicazione**. Il servizio catalogo o il carrello, ad esempio, potrebbe essere necessario per la scalabilità, ma non il processo di ordinamento. Un'infrastruttura di microservizi sarà molto più efficiente per quanto riguarda le risorse usate quando si distribuisce orizzontalmente rispetto a un'architettura monolitica.

**È possibile dividere il lavoro tra più team di sviluppo**. Ogni servizio può essere di proprietà da un team di sviluppo singolo. Ogni team può gestire, sviluppare, distribuire e scalare il servizio in modo indipendente il resto dei team.

**I problemi sono più isolati**. Se si verifica un problema in un servizio, solo tale servizio è compromessa inizialmente (tranne quando viene utilizzata la progettazione errata, con le dipendenze dirette tra microservizi) e altri servizi possono continuare a gestire le richieste. Al contrario, un componente che non funziona correttamente in un'architettura di distribuzione monolitico può arrestare l'intero sistema, soprattutto quando implica risorse, ad esempio una perdita di memoria. Inoltre, quando un problema in un microservizio viene risolto, è possibile distribuire solo il microservizio interessato senza alcun impatto sul resto dell'applicazione.

**È possibile utilizzare le tecnologie più recenti**. Poiché è possibile iniziare a sviluppare servizi in modo indipendente ed eseguirli side-by-side (grazie a contenitori e .NET Core), iniziare a utilizzare le tecnologie e i framework più recente speditamente anziché rimanga bloccato su un framework per l'intero o un stack precedente applicazione.

## <a name="downsides-of-a-microservice-based-solution"></a>Negativi di una soluzione basata su microservizio

Una soluzione di base microservizio simile al seguente presenta alcuni svantaggi:

**Applicazione distribuita**. Distribuzione dell'applicazione aggiunge complessità per gli sviluppatori quando vengono la progettazione e i servizi di compilazione. Ad esempio, gli sviluppatori devono implementare comunicazioni interservizi mediante protocolli quali HTTP o AMPQ, che aggiunge complessità per i test e la gestione delle eccezioni. Aggiunge anche la latenza per il sistema.

**Complessità di distribuzione**. Un'applicazione che dispone di decine di tipi di microservizi e scalabilità elevate (deve essere in grado di creare molte istanze per ogni servizio e bilanciare i servizi su molti computer host) è necessario pertanto un elevato livello di complessità di distribuzione per la gestione e gli operatori IT. Se non si utilizza un'infrastruttura orientata ai servizi microservizio (ad esempio, un agente di orchestrazione e utilità di pianificazione), tale complessità può richiedere molto più attività di sviluppo rispetto all'applicazione di business stesso.

**Le transazioni atomiche**. Le transazioni atomiche tra più microservizi in genere non sono possibili. I requisiti aziendali sono necessario adottare la coerenza eventuale tra più microservizi.

**Aumento delle esigenze di risorse globali** (totale di memoria, le unità e risorse di rete per tutti i server o host). In molti casi, quando si sostituisce un'applicazione monolitica con un approccio di microservizi, la quantità di risorse globali necessari per la nuova applicazione microservizio sarà maggiore rispetto alle esigenze di infrastruttura dell'applicazione monolitico originale. Questo avviene perché il livello più elevato di granularità e i servizi distribuiti richiede risorse più globale. Tuttavia, dato il costo delle risorse in generale e il vantaggio di poter scalare orizzontalmente solo determinate aree dell'applicazione rispetto ai costi elevati a lungo termine quando si sviluppano applicazioni monolitiche, l'uso di un aumento delle risorse è in genere un buon compromesso per grandi dimensioni, applicazioni a lungo termine.

**Problemi di comunicazione diretta client‑to‑microservice**. Quando l'applicazione è di grandi dimensioni, con decine di microservizi, esistono problematiche e limitazioni se l'applicazione richiede le comunicazioni client-a-microservizio dirette. Un problema è una potenziale mancata corrispondenza tra le esigenze del client e le API esposte da ognuno di microservizi. In alcuni casi, l'applicazione client potrebbe essere necessario apportare molte richieste separate per comporre l'interfaccia utente, che può risultare inefficiente su Internet e non risulterebbe conveniente in una rete mobile. Pertanto, richieste dall'applicazione client per il sistema back-end devono essere ridotta a icona.

Un altro problema con le comunicazioni client-a-microservizio dirette è che alcune microservizi potrebbero avere utilizzato i protocolli che non sono adatti a Web. Un servizio può usare un protocollo binario, mentre un altro servizio utilizzi messaggistica AMQP. Tali protocolli non sono firewall‑friendly e vengono utilizzate internamente. In genere, un'applicazione deve utilizzare protocolli quali HTTP e WebSockets per la comunicazione all'esterno del firewall.

Ancora un altro svantaggio con questo approccio diretto client‑to‑service è che rende difficile eseguire il refactoring i contratti per tali microservizi. Nel tempo agli sviluppatori potrebbe essere opportuno modificare il modo in cui il sistema è partizionato in servizi. Ad esempio, potrebbero unire i due servizi o suddividere un servizio in due o più servizi. Tuttavia, se i client comunicano direttamente con i servizi, l'esecuzione di questo tipo di refactoring può interrompere la compatibilità con le applicazioni client.

Come indicato nella sezione architettura, durante la progettazione e creazione di un'applicazione complessa basata su microservizi, è possibile considerare l'utilizzo di più gateway API con granularità fine anziché l'approccio più semplice di comunicazione client‑to‑microservice diretto.

**Partizionamento di microservizi**. Infine, indipendentemente dall'approccio adottato per l'architettura del microservizio, un'altra richiesta di verifica deve decidere come un'applicazione end-to-end in più microservizi di partizione. Come indicato nella sezione della Guida all'architettura, esistono diverse tecniche e approcci. In pratica, è necessario identificare le aree dell'applicazione che vengono disaccoppiati da altre aree e che hanno un numero basso di dipendenze rigide. In molti casi, questo è allineato al partizionamento servizi dal caso d'uso. Ad esempio, nell'applicazione e reparto, è necessario un servizio di ordinamento che è responsabile di tutta la logica di business relative al processo di ordine. È necessario anche il servizio del catalogo e il servizio di basket che implementano le altre funzionalità. Idealmente, ogni servizio deve avere solo un piccolo set di responsabilità. È simile al singolo responsabilità principio (criteri di restrizione software) applicato alle classi, che indica che una classe debba avere solo uno dei motivi per modificare. Ma in questo caso, è su microservizi, in modo che l'ambito sia maggiore di una singola classe. Soprattutto, un microservizio deve essere completamente autonomo, to end, compresa la responsabilità per le proprie origini dati.

## <a name="external-versus-internal-architecture-and-design-patterns"></a>Esterni e interni modelli di architettura e progettazione

L'architettura esterno è composto da più servizi, seguendo i principi descritti nella sezione architettura di questa Guida all'architettura di microservizio. Tuttavia, a seconda della natura di ogni microservizio e indipendentemente dall'architettura di alto livello microservizio si sceglie, è comune e in alcuni casi è consigliabile disporre di diverse architetture interne, ognuna basata su modelli differenti, per diversi microservizi. Il microservizi è anche possono utilizzare diverse tecnologie e linguaggi di programmazione. Figura 8-2 viene illustrata questa diversità.

![](./media/image2.png)

**Figura 8-2**. Esterni e di architettura e progettazione

Ad esempio, nel nostro *eShopOnContainers* microservizi profilo di esempio, il catalogo, basket e utente sono semplici (in pratica, sottosistemi CRUD). Pertanto, la progettazione e l'architettura interna è semplice. Tuttavia, potrebbe essere altri microservizi, ad esempio l'ordinamento microservizio, che è più complessa e rappresenta le regole di business in continua evoluzione con un elevato livello di complessità di dominio. In questi casi si consiglia di implementare i modelli più avanzati all'interno di un particolare microservizio, come quelli definiti con gli approcci di progettazione basati su dominio (DDD), come *eShopOnContainers* ordinamento microservizio. (Questi modelli DDD della sezione in un secondo momento in cui viene illustrata l'implementazione di verranno esaminate le *eShopOnContainers* ordinamento microservizio.)

Un altro motivo per una tecnologia diversa per ogni microservizio potrebbe essere la natura di ogni microservizio. Ad esempio, potrebbe essere preferibile utilizzare un linguaggio di programmazione funzionale, ad esempio F\#, o anche un linguaggio come R Se la destinazione è AI e machine learning domini, anziché un linguaggio di programmazione orientata ad esempio C\#.

La riga inferiore è che ogni microservizio può avere un'architettura interna diversa in base ai modelli di progettazione diverse. Microservizi tutti non devono essere implementate utilizzando modelli avanzati DDD, perché che potrebbe essere eccessivo engineering li. Analogamente, microservizi complessi con la logica di business in continua evoluzione non devono essere implementata come componenti CRUD oppure possono finire con codice di bassa qualità.



## <a name="the-new-world-multiple-architectural-patterns-and-polyglot-microservices"></a>Il nuovo ambiente: più modelli di architettura e microservizi polyglot

Esistono molti modelli di architettura utilizzati da sviluppatori e progettisti software. Di seguito sono riportati alcuni (combinazione di stili di architettura e i modelli di architettura):

-   Semplice CRUD, a livello di singolo, solo livello.

-   [Tradizionale a più livelli N](https://msdn.microsoft.com/en-us/library/ee658109.aspx#Layers).

-   [Basati su dominio progettazione a più livelli N](https://blogs.msdn.microsoft.com/cesardelatorre/2011/07/03/published-first-alpha-version-of-domain-oriented-n-layered-architecture-v2-0/).

-   [Eseguire la pulizia architettura](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html) (se utilizzato con [eShopOnWeb](http://aka.ms/WebAppArchitecture))

-   [Comando ed eseguire Query di separazione delle responsabilità](https://martinfowler.com/bliki/CQRS.html) (CQRS).

-   [Architettura basata sugli eventi](https://en.wikipedia.org/wiki/Event-driven_architecture) (EDA).

È anche possibile compilare microservizi con numerose tecnologie e i linguaggi, ad esempio API Web di ASP.NET Core, NancyFx, ASP.NET Core SignalR (disponibile con .NET Core 2), F\#, Node.js, Python, Java, C++, GoLang e molto altro.

L'aspetto importante è che nessun motivo particolare architettura o stile né qualsiasi tecnologia specifica, è appropriato per tutte le situazioni. Figura 8-3 illustra alcuni approcci e delle tecnologie (anche se non in un ordine particolare) che possono essere utilizzati nel microservizi diversi.

![](./media/image3.png)

**Figura 8-3**. I modelli di architettura più e con il mondo microservizi polyglot

Come illustrato nella figura 8-3, nelle applicazioni costituito da molti microservizi (delimitata contesti nella terminologia di progettazione basati su dominio, o semplicemente "sottosistemi" come microservizi autonomo), è possibile implementare ogni microservizio in modo diverso. Ogni potrebbe dispongono di un modello di architettura diversi e utilizzare diversi linguaggi e i database a seconda della natura dell'applicazione, i requisiti di business e priorità. In alcuni casi il microservizi potrebbero essere simile. Ma che non è in genere il caso, poiché il limite di contesto e requisiti di ogni sottosistema sono in genere diversi.

Ad esempio, per una semplice applicazione di manutenzione CRUD, non potrebbe non senso per progettare e implementare DDD modelli. Ma per il dominio di base o business di base, potrebbe essere necessario applicare i modelli più avanzati per gestire la complessità di business con regole di business in continua evoluzione.

Soprattutto quando si gestiscono con applicazioni di grandi dimensioni composte da più sistemi secondari, è consigliabile non applicare un'unica architettura di primo livello in base a un modello di architettura single. Ad esempio, CQRS non deve essere applicato come un'architettura di primo livello per un'intera applicazione, ma potrebbero essere utili per un set specifico di servizi.

È presente alcun punto argento o un modello di architettura per ogni case specificato. Non è possibile avere "uno schema di architettura per tutte le regole." A seconda della priorità di ogni microservizio, è necessario scegliere un approccio diverso per ognuno, come illustrato nelle sezioni seguenti.


>[!div class="step-by-step"]
[Precedente] [Avanti] (data-driven-crud-microservice.md) (index.md)
