---
title: Progettazione di un'applicazione orientata ai microservizi
description: Architettura di microservizi .NET per applicazioni .NET incluse in contenitori | Conoscere i vantaggi e gli svantaggi di un'applicazione orientata ai microservizi, in modo da poter prendere una decisione consapevole.
ms.date: 10/02/2018
ms.openlocfilehash: 619440c02c1a82e05adb2cec9ddba933cd3e0a65
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965763"
---
# <a name="design-a-microservice-oriented-application"></a>Progettare un'applicazione orientata ai microservizi

Questa sezione illustra lo sviluppo di un'ipotetica applicazione aziendale sul lato server.

## <a name="application-specifications"></a>Specifiche dell'applicazione

L'ipotetica applicazione gestisce le richieste eseguendo la logica di business, effettuando l'accesso ai database e quindi restituendo risposte HTML, JSON o XML. Si può affermare che l'applicazione deve supportare un'ampia gamma di client, inclusi i browser desktop che eseguono applicazioni a pagina singola, app Web tradizionali, app Web per dispositivi mobili e app per dispositivi mobili native. L'applicazione potrebbe inoltre esporre un'API utilizzabile da terze parti. Dovrebbe essere anche in grado di integrare in modo asincrono i relativi microservizi o le applicazioni esterne, pertanto questo approccio contribuirà alla resilienza dei microservizi in caso di errori parziali.

L'applicazione sarà costituita da questi tipi di componenti:

- Componenti della presentazione, responsabili della gestione dell'interfaccia utente e dell'utilizzo dei servizi remoti.

- Logica di business o di dominio, ovvero la logica di dominio dell'applicazione.

- Logica di accesso al database, costituita dai componenti di accesso ai dati responsabili dell'accesso ai database (SQL o NoSQL).

- Logica di integrazione dell'applicazione, che include un canale di messaggistica basato principalmente su broker di messaggi.

L'applicazione richiederà una scalabilità elevata, consentendo ai relativi sottosistemi verticali di aumentare il numero di istanze in modo autonomo, dal momento che alcuni sottosistemi richiederanno maggiore scalabilità rispetto ad altri.

L'applicazione deve poter essere distribuita in più ambienti infrastrutturali (più cloud pubblici e locali) e idealmente dovrebbe essere multipiattaforma, in grado di passare facilmente da Linux a Windows (o viceversa).

## <a name="development-team-context"></a>Contesto del team di sviluppo

Si presuppongono inoltre le informazioni seguenti sul processo di sviluppo per l'applicazione:

- Sono presenti più team di sviluppo che si occupano delle diverse aree di attività dell'applicazione.

- I nuovi membri dei team devono diventare produttivi rapidamente e l'applicazione deve essere facile da comprendere e modificare.

- L'applicazione avrà un'evoluzione a lungo termine e regole business in continuo cambiamento.

- È necessaria una buona manutenibilità a lungo termine, ovvero flessibilità durante l'implementazione di nuove modifiche future pur essendo in grado di aggiornare più sottosistemi con un impatto minimo sugli altri sottosistemi.

- È necessario assicurare l'integrazione e la distribuzione continue dell'applicazione.

- Si vogliono sfruttare i vantaggi delle tecnologie emergenti (framework, linguaggi di programmazione e così via) durante l'evoluzione dell'applicazione. Non si vogliono eseguire migrazioni complete dell'applicazione durante il passaggio a nuove tecnologie, dal momento che potrebbero comportare costi elevati e incidere sulla prevedibilità e sulla stabilità dell'applicazione.

## <a name="choosing-an-architecture"></a>Scelta di un'architettura

Quale dovrebbe essere l'architettura di distribuzione dell'applicazione? Le specifiche per l'applicazione, insieme al contesto di sviluppo, suggeriscono che è opportuno progettare l'applicazione scomponendola in sottosistemi autonomi sotto forma di microservizi e contenitori in collaborazione, dove un microservizio è un contenitore.

In questo approccio ogni servizio (contenitore) implementa un set di funzioni coerenti e strettamente correlate. Ad esempio, un'applicazione potrebbe essere costituita da servizi come il servizio catalogo, il servizio di gestione degli ordini, il servizio carrello, il servizio profilo utente e così via.

I microservizi comunicano usando protocolli quali HTTP (REST), ma anche in modo asincrono (ad esempio, tramite AMQP) ogni volta che è possibile, soprattutto quando si propagano gli aggiornamenti con eventi di integrazione.

I microservizi vengono sviluppati e distribuiti come contenitori indipendentemente uno dall'altro. Ciò significa che un team di sviluppo può sviluppare e distribuire un determinato microservizio senza alcun impatto sugli altri sottosistemi.

Ogni microservizio dispone del proprio database, in modo da poter essere completamente separato dagli altri. Se necessario, la coerenza tra database di microservizi diversi viene ottenuta usando eventi di integrazione a livello di applicazione (tramite un bus di eventi logici), così come vengono gestiti in Command and Query Responsibility Segregation (CQRS). Per questo motivo, i vincoli aziendali devono prevedere la coerenza finale tra i diversi microservizi e i relativi database.

### <a name="eshoponcontainers-a-reference-application-for-net-core-and-microservices-deployed-using-containers"></a>eShopOnContainers: un'applicazione di riferimento per .NET Core e microservizi distribuiti tramite contenitori

Nell'intento di concentrarsi maggiormente sull'architettura e le tecnologie anziché pensare a un ipotetico dominio aziendale sconosciuto, è stato scelto un dominio aziendale noto, per l'esattezza un'applicazione e-commerce (e-shop) semplificata che presenta un catalogo di prodotti, accetta gli ordini dei clienti, verifica l'inventario ed esegue altre funzioni aziendali. Il codice sorgente di questa applicazione basata su contenitori è disponibile nel repository GitHub [eShopOnContainers](https://aka.ms/MicroservicesArchitecture).

L'applicazione è costituita da più sottosistemi, inclusi diversi front-end con interfaccia utente per negozi (un'applicazione Web e un'app per dispositivi mobili nativa), oltre a microservizi e contenitori back-end per tutte le operazioni richieste sul lato server con diversi gateway API come punti di ingresso consolidati ai microservizi interni. La figura 6-1 illustra l'architettura dell'applicazione di riferimento.

![Diagramma delle app client che usano eShopOnContainers in un singolo host docker.](./media/microservice-application-design/eshoponcontainers-reference-application-architecture.png)

**Figura 6-1**. L'architettura dell'applicazione di riferimento eShopOnContainers per l'ambiente di sviluppo

Il diagramma precedente mostra che i client per dispositivi mobili e SPA comunicano con endpoint di gateway API singoli, che quindi comunicano con i microservizi. I client Web tradizionali comunicano con microservizi MVC, che comunica con i microservizi tramite il gateway API.

**Ambiente host**. Nella figura 6-1 sono visibili diversi contenitori distribuiti all'interno di un singolo host Docker, ovvero la situazione che si verifica durante la distribuzione in un singolo host Docker con il comando docker-compose up. Tuttavia, se si usa un agente di orchestrazione o un cluster di contenitori, ogni contenitore potrebbe essere eseguito in un host (nodo) differente e i nodi potrebbero eseguire un numero qualsiasi di contenitori, come illustrato in precedenza nella sezione sull'architettura.

**Architettura di comunicazione**. L'applicazione eShopOnContainers usa due tipi di comunicazione, a seconda del tipo di azione funzionale (query o aggiornamenti e transazioni):

- Comunicazione da client a microservizio HTTP attraverso i gateway API. Viene usata per le query e quando si accettano comandi di aggiornamento o transazionali dalle app client. L'approccio con i gateway API è spiegato in dettaglio nelle sezioni successive.

- Comunicazione asincrona basata su eventi. Si verifica tramite un bus di eventi per la propagazione degli aggiornamenti tra i microservizi o per l'integrazione con applicazioni esterne. Il bus di eventi può essere implementato con qualsiasi tecnologia di infrastruttura di broker di messaggistica, ad esempio RabbitMQ, o con bus di servizio di livello superiore (livello di astrazione), ad esempio il bus di servizio di Azure, NServiceBus, MassTransit o Brighter.

L'applicazione viene distribuita come un set di microservizi sotto forma di contenitori. Le app client possono comunicare con tali microservizi se eseguite come contenitori attraverso gli URL pubblici pubblicati dai gateway API.

### <a name="data-sovereignty-per-microservice"></a>Sovranità dei dati per microservizio

Nell'applicazione di esempio ogni microservizio è proprietario di un database o un'origine dati, benché tutti i database di SQL Server vengano distribuiti come un singolo contenitore. Questa decisione progettuale è stata presa solo per semplificare l'acquisizione del codice da GitHub, la clonazione e l'apertura in Visual Studio o Visual Studio Code da parte dello sviluppatore. In alternativa, consente di compilare facilmente le immagini Docker personalizzate usando il interfaccia della riga di comando di .NET Core e l'interfaccia della riga di comando di Docker e quindi di distribuirle ed eseguirle in un ambiente di sviluppo docker. In entrambi i casi, l'uso di contenitori per le origini dati consente agli sviluppatori di compilare e distribuire in pochi minuti senza dover eseguire il provisioning di un database esterno o di qualsiasi altra origine dati con dipendenze rigide dall'infrastruttura (cloud o locale).

In un ambiente di produzione reale, per la disponibilità elevata e la scalabilità i database dovrebbero essere basati su server di database nel cloud o in locale, ma non nei contenitori.

Pertanto, le unità di distribuzione per i microservizi (e anche per i database in questa applicazione) sono contenitori Docker e l'applicazione di riferimento è un'applicazione a più contenitori basata sui principi dei microservizi.

### <a name="additional-resources"></a>Risorse aggiuntive

- **repository GitHub eShopOnContainers. Codice sorgente per l'applicazione di riferimento** \
  <https://aka.ms/eShopOnContainers/>

## <a name="benefits-of-a-microservice-based-solution"></a>Vantaggi di una soluzione basata su microservizi

Una soluzione basata su microservizi come questa presenta molti vantaggi:

**Ogni microservizio è relativamente piccolo, semplice da gestire e da sviluppare**. In particolare:

- Sono concetti facili da comprendere e gli sviluppatori possono essere rapidamente operativi e ottenere una buona produttività.

- I contenitori possono essere usati subito, rendendo più produttivi gli sviluppatori.

- Un ambiente di sviluppo integrato come Visual Studio può caricare rapidamente progetti di dimensioni minori, assicurando la produttività degli sviluppatori.

- Ogni microservizio può essere progettato, sviluppato e distribuito in modo indipendente dagli altri, il che garantisce una maggiore flessibilità dal momento che è più facile distribuire con regolarità nuove versioni dei microservizi.

**È possibile aumentare il numero delle singole aree dell'applicazione**. Ad esempio, potrebbe essere necessario aumentare il numero delle istanze del servizio catalogo o del servizio carrello, ma non quello del processo di gestione degli ordini. Un'infrastruttura di microservizi sarà molto più efficiente di un'architettura monolitica per quel che riguarda le risorse usate quando si aumenta il numero delle istanze.

**È possibile dividere le attività di sviluppo tra più team**. Ogni servizio può essere di proprietà di un unico team di sviluppo. Ogni team può gestire, sviluppare, distribuire e ridimensionare il servizio in modo indipendente dal resto dei team.

**I problemi sono più isolati**. Se si verifica un problema in un servizio, solo tale servizio risulta interessato inizialmente (tranne quando si usa una progettazione errata, con dipendenze dirette tra i microservizi) e gli altri servizi possono continuare a gestire le richieste. Al contrario, un componente che non funziona correttamente in un'architettura di distribuzione monolitica può arrestare l'intero sistema, soprattutto quando si ripercuote sulle risorse, come nel caso di una perdita di memoria. Inoltre, quando un problema in un microservizio viene risolto, è possibile distribuire solo il microservizio interessato senza ripercussioni sul resto dell'applicazione.

**Possono essere usate le tecnologie più recenti**. Potendo iniziare a sviluppare i servizi in modo indipendente ed eseguirli side-by-side (grazie ai contenitori e a .NET Core), è possibile cominciare a usare agevolmente le tecnologie e i framework più recenti anziché rimanere ancorati a uno stack o a un framework obsoleto per l'intera applicazione.

## <a name="downsides-of-a-microservice-based-solution"></a>Svantaggi di una soluzione basata su microservizi

Una soluzione basata su microservizi come questa presenta anche alcuni svantaggi:

**Applicazione distribuita**. La distribuzione dell'applicazione aumenta la complessità per gli sviluppatori in fase di progettazione e compilazione dei servizi. Ad esempio, gli sviluppatori devono implementare la comunicazione tra servizi usando protocolli come HTTP o AMPQ, che aggiunge complessità per i test e la gestione delle eccezioni. Anche la latenza per il sistema aumenta.

**Complessità della distribuzione**. Un'applicazione che dispone di decine di tipi di microservizi e necessita di scalabilità elevata (dovendo essere in grado di creare molte istanze per ogni servizio e di bilanciare tali servizi su molti host) comporta un livello elevato di complessità di distribuzione per le operazioni IT e la gestione. Se non si usa un'infrastruttura orientata ai microservizi (come un agente di orchestrazione e un'utilità di pianificazione), questa ulteriore complessità può richiedere molte più attività di sviluppo dell'applicazione aziendale stessa.

**Transazioni atomiche**. Le transazioni atomiche tra più microservizi in genere non sono possibili. I requisiti aziendali devono prevedere la coerenza finale tra più microservizi.

**Aumento delle richieste di risorse globali** (memoria totale, unità e risorse di rete per tutti i server o gli host). In molti casi, quando si sostituisce un'applicazione monolitica con un approccio di tipo microservizi, la quantità iniziale di risorse globali necessarie per la nuova applicazione basata su microservizi sarà maggiore rispetto alle esigenze dell'infrastruttura dell'applicazione monolitica originale. Questo avviene perché il maggiore livello di granularità e di servizi distribuiti richiede più risorse globali. Tuttavia, considerato il costo minimo delle risorse in generale e il vantaggio di poter ridimensionare solo determinate aree dell'applicazione rispetto ai costi a lungo termine per lo sviluppo di applicazioni monolitiche, l'incremento nell'uso delle risorse in genere è un buon compromesso per applicazioni a lungo termine di grandi dimensioni.

**Problemi con la comunicazione da client a microservizio diretta**. Quando l'applicazione è di grandi dimensioni, con decine di microservizi, possono presentarsi diverse problematiche e limitazioni se l'applicazione richiede comunicazioni da client a microservizio dirette. Un problema è una potenziale mancata corrispondenza tra le esigenze del client e le API esposte da ognuno dei microservizi. In alcuni casi, l'applicazione client potrebbe aver bisogno di presentare molte richieste distinte per comporre l'interfaccia utente, causando problemi di inefficienza su Internet e di scarsa praticità in una rete mobile. Pertanto, le richieste dall'applicazione client al sistema back-end dovrebbero essere ridotte al minimo.

Un altro problema con le comunicazioni da client a microservizio dirette è che alcuni microservizi potrebbero usare protocolli non appropriati per il Web. Un servizio potrebbe usare un protocollo binario, mentre un altro servizio potrebbe fare ricorso alla messaggistica AMQP. Tali protocolli non sono indicati per il firewall e sono più adatti per un uso interno. In genere, un'applicazione dovrebbe usare protocolli quali HTTP e WebSocket per la comunicazione all'esterno del firewall.

Un altro svantaggio di questo approccio di tipo comunicazione da client a servizio diretta è che rende difficile effettuare il refactoring dei contratti per tali microservizi. Nel tempo, gli sviluppatori potrebbero avere bisogno di modificare il modo in cui il sistema è partizionato nei servizi. Ad esempio, potrebbero unire due servizi o suddividere un servizio in due o più servizi. Tuttavia, se i client comunicano direttamente con i servizi, l'esecuzione di questo tipo di refactoring può interrompere la compatibilità con le applicazioni client.

Come accennato nella sezione relativa all'architettura, durante la progettazione e la compilazione di un'applicazione complessa basata su microservizi è possibile prendere in considerazione l'uso di più gateway API con granularità fine, anziché l'approccio più semplice di tipo comunicazione da client a microservizio diretta.

**Partizionamento dei microservizi**. Infine, indipendentemente dall'approccio adottato per l'architettura basata su microservizi, un'altra questione cruciale è quella di decidere come partizionare un'applicazione end-to-end in più microservizi. Come indicato nella sezione sull'architettura di questa guida, esistono differenti tecniche e approcci che è possibile adottare. Fondamentalmente, è necessario identificare le aree dell'applicazione che vengono separate dalle altre e che hanno un numero ridotto di dipendenze rigide. In molti casi, questo approccio è allineato al partizionamento dei servizi in base al caso d'uso. Ad esempio, nell'applicazione e-shop è disponibile un servizio di gestione degli ordini che è responsabile di tutta la logica di business relativa al processo di ordine. Si dispone inoltre del servizio catalogo e del servizio carrello che implementano altre funzionalità. Idealmente, ogni servizio dovrebbe avere solo un piccolo set di responsabilità. Il concetto è analogo a quello del principio di singola responsabilità (SRP, Single Responsibility Principle) applicato alle classi, che indica che una classe deve avere un solo motivo per cambiare. Ma in questo caso si tratta di microservizi, pertanto l'ambito sarà maggiore rispetto a una singola classe. Soprattutto, un microservizio deve essere completamente autonomo, end-to-end, compresa la responsabilità per le relative origini dati.

## <a name="external-versus-internal-architecture-and-design-patterns"></a>Architettura e schemi progettuali esterni e interni a confronto

L'architettura esterna è costituita dall'architettura di microservizi composta da più servizi, in base ai principi descritti nella sezione sull'architettura di questa guida. Tuttavia, a seconda della natura di ogni microservizio e indipendentemente dall'architettura di microservizi di alto livello scelta, è comune e in alcuni casi consigliabile disporre di diverse architetture interne, ognuna basata su schemi differenti, per microservizi diversi. I microservizi possono anche usare tecnologie e linguaggi di programmazione differenti. La figura 6-2 illustra questa diversità.

![Diagramma che confronta modelli di architettura interni ed esterni.](./media/microservice-application-design/external-versus-internal-architecture.png)

**Figura 6-2**. Architettura e progettazione esterne e interne a confronto

Ad esempio, nell'esempio *eShopOnContainers* i microservizi del catalogo, del carrello e del profilo utente sono semplici (fondamentalmente, sottosistemi CRUD). Pertanto, la relativa architettura e la progettazione interne sono lineari. Tuttavia, potrebbero essere presenti altri microservizi, ad esempio quello di gestione degli ordini, che è più complesso e rappresenta le regole business in continua evoluzione con un livello elevato di complessità di dominio. In casi come questi, è consigliabile implementare schemi più avanzati all'interno di un determinato microservizio, come quelli definiti con l'approccio di tipo progettazione basata su domini (DDD), come nel caso del microservizio di gestione degli ordini di *eShopOnContainers*. Questi schemi DDD verranno riesaminati più avanti nella sezione che illustra l'implementazione del servizio di gestione degli ordini di *eShopOnContainers*.

Un altro motivo per usare una tecnologia differente per ogni microservizio potrebbe essere la natura dei diversi microservizi. Ad esempio, potrebbe essere preferibile usare un linguaggio di programmazione funzionale quale F\# o addirittura un linguaggio come R se si fa riferimento a domini di Machine Learning e intelligenza artificiale, invece di un linguaggio di programmazione più orientato a oggetti come C\#.

In conclusione, ogni microservizio può avere un'architettura interna differente in base ai diversi schemi progettuali. Non tutti i microservizi devono essere implementati usando schemi DDD avanzati, dal momento che questo approccio apporterebbe troppe modifiche alla progettazione. Analogamente, i microservizi complessi con una logica di business in continua evoluzione non dovrebbero essere implementati come componenti CRUD perché il risultato potrebbe essere un codice di scarsa qualità.

## <a name="the-new-world-multiple-architectural-patterns-and-polyglot-microservices"></a>Il nuovo mondo: più schemi architetturali e microservizi poliglotti

Esistono molti schemi architetturali usati dagli sviluppatori e dai progettisti software. Di seguito sono riportati alcuni esempi, che combinano stili e schemi architetturali:

- CRUD semplice a un solo livello.

- [Tradizionale a N livelli](https://docs.microsoft.com/previous-versions/msp-n-p/ee658109(v=pandp.10)).

- [Progettazione basata su domini a N livelli](https://devblogs.microsoft.com/cesardelatorre/published-first-alpha-version-of-domain-oriented-n-layered-architecture-v2-0/).

- [Architettura pulita](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html) (come quella usata con [eShopOnWeb](https://aka.ms/WebAppArchitecture))

- [Command and Query Responsibility Segregation](https://martinfowler.com/bliki/CQRS.html) (CQRS).

- [Architettura basata su eventi](https://en.wikipedia.org/wiki/Event-driven_architecture) (EDA).

È anche possibile compilare microservizi con molti linguaggi e tecnologie, come le API Web di ASP.NET Core, NancyFx, ASP.NET Core SignalR (disponibile con .NET Core 2), F\#, Node.js, Python, Java, C++, GoLang e molto altro ancora.

Il concetto fondamentale da comprendere è che nessuno stile o schema architetturale particolare né nessuna tecnologia specifica è appropriata per tutte le situazioni. La figura 6-3 illustra alcuni approcci e tecnologie (anche se non in un ordine specifico) che possono essere usati nei diversi microservizi.

![Diagramma che mostra 12 microservizi complessi in un'architettura del mondo poliglotta.](./media/microservice-application-design/multi-architectural-patterns-polyglot-microservices.png)

**Figura 6-3**. Il mondo dei diversi schemi architetturali e microservizi poliglotti

Usare uno schema a più architetture e microservizi poliglotti significa combinare linguaggi e tecnologie con le esigenze di ogni microservizio facendo in modo che comunichino tra loro. Come illustra la figura 6-3, nelle applicazioni costituite da molti microservizi (contesti delimitati nella terminologia della progettazione basata su domini o semplicemente "sottosistemi" come microservizi autonomi), è possibile implementare ogni microservizio in un modo diverso. Ognuno potrebbe avere uno schema architetturale differente e usare linguaggi e database diversi in base alla natura dell'applicazione, ai requisiti aziendali e alle priorità. In alcuni casi, i microservizi potrebbero essere simili. Ma non si tratta di un caso frequente, dal momento che il limite di contesto e i requisiti di ogni sottosistema in genere sono diversi.

Ad esempio, per una semplice applicazione di manutenzione CRUD, potrebbe non avere senso progettare e implementare schemi DDD. Ma per il dominio base o l'attività principale, potrebbe essere necessario applicare schemi più avanzati per gestire la complessità aziendale con regole business in continua evoluzione.

Soprattutto quando si gestiscono applicazioni di grandi dimensioni composte da più sottosistemi, è consigliabile non applicare una singola architettura di primo livello basata su un unico modello di architettura. Ad esempio, CQRS non dovrebbe essere applicato come un'architettura di primo livello per un'intera applicazione, ma potrebbe essere utile per un set specifico di servizi.

Non esiste un metodo infallibile o il giusto schema architetturale per ogni singolo caso. Non è possibile avere un solo schema architetturale applicabile a tutte le situazioni. In base alle priorità di ogni microservizio, è necessario scegliere un approccio differente, come illustrato nelle sezioni successive.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](data-driven-crud-microservice.md)
