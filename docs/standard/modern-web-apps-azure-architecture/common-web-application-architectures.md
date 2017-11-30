---
title: Architetture di applicazioni web comuni
description: Architettura di moderne applicazioni web con ASP.NET Core e Microsoft Azure | architetture di applicazioni web comuni
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: b6236cfab290211f930d6a1987075abeade4fd6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
#<a name="common-web-application-architectures"></a>Architetture di applicazioni Web comuni

> "Se si ritiene che l'architettura ottimale è costoso, provare a architettura non valido."  
> _-Piè di pagina Brian e Yoder massimo_

## <a name="summary"></a>Riepilogo

Applicazioni .NET più tradizionali vengono distribuite come singola unità di misura corrispondente a un file eseguibile o una singola applicazione web in esecuzione all'interno di un singolo dominio di applicazione IIS. Questo è il modello di distribuzione più semplice e ha molte applicazioni interne e pubbliche più piccolo molto bene. Tuttavia, più applicazioni di business non semplice anche se questa singola unità di distribuzione, trarre vantaggio da una separazione logica in livelli diversi.

## <a name="what-is-a-monolithic-application"></a>Che cos'è un'applicazione monolitica?

Un'applicazione monolitica è quello che è completamente indipendente, in termini di comportamento. Può interagire con altri servizi o archivi dati nel corso dell'esecuzione delle operazioni, ma il nucleo del comportamento viene eseguito all'interno di un proprio processo e l'intera applicazione viene in genere distribuito come una singola unità. Se un'applicazione deve ridimensionare in senso orizzontale, in genere l'intera applicazione è duplicato in più server o macchine virtuali.

## <a name="all-in-one-applications"></a>Applicazioni all-in-One

Il minor numero possibile di progetti per un'architettura dell'applicazione è uno. In questa architettura, l'intera logica dell'applicazione è contenuta in un unico progetto compilata in un singolo assembly e distribuita come una singola unità.

Un nuovo progetto ASP.NET Core, se create in Visual Studio o dalla riga di comando, inizia come un semplice monolito "all-in-one". Contiene tutti i comportamenti dell'applicazione, inclusi la logica di accesso di presentazione, business e dati. Figura 5-1 mostra la struttura di file di una singolo progetto di app.

**Figura 5-1.** Un singolo progetto app di ASP.NET Core

![](./media/image5-1.png)

In uno scenario singolo progetto, la separazione dei compiti viene ottenuta tramite l'utilizzo di cartelle. Il modello predefinito include cartelle separate per le responsabilità di modello MVC di modelli, visualizzazioni e controller, nonché cartelle aggiuntive per i dati e servizi. In questo caso, i dettagli di presentazione devono essere limitati il più possibile alla cartella viste e i dettagli di implementazione di accesso ai dati devono essere limitati a classi mantenute nella cartella dei dati. Logica di business deve trovarsi in servizi e le classi all'interno della cartella di modelli.

Sebbene semplice, la soluzione di progetto singolo monolitica presenta alcuni svantaggi. Man mano che aumenta le dimensioni e la complessità del progetto, il numero di file e cartelle continuerà ad aumentare anche. Problemi dell'interfaccia utente (modelli, visualizzazioni, controller) si trovano in più cartelle, non vengono raggruppate in ordine alfabetico. Questo problema Ottiene peggiore solo quando vengono aggiunti altri costrutti di livello di interfaccia utente, ad esempio filtri o ModelBinders, nelle rispettive cartelle. Logica di business è sparse tra le cartelle di modelli e i servizi e sarà presente alcuna indicazione chiara dei quali classi cartelle in cui devono dipendere che altri utenti. La mancanza dell'organizzazione a livello di progetto in modo frequente [assai complicato](http://deviq.com/spaghetti-code/).

Per risolvere questi problemi, le applicazioni si trasformano spesso nelle soluzioni multiprogetto, in cui ogni progetto viene considerato a risiedere in un particolare *livello* dell'applicazione.

## <a name="what-are-layers"></a>Quali sono i livelli?

Come applicazioni aumentano della complessità, è possibile gestire la complessità è suddividere l'applicazione in base al relativo responsabilità o problemi. In questo segue la separazione del principio di problemi e consente di mantenere una codebase crescente organizzata in modo che gli sviluppatori in cui viene implementato determinate funzionalità possono trovare con facilità. Architettura a più livelli offre una serie di vantaggi oltre appena organizzazione di codice, tuttavia.

Organizzando codice in livelli, la funzionalità di basso livello comune può essere riutilizzata in tutta l'applicazione. In questo modo è utile poiché significa che deve essere scritto meno codice e può consentire l'applicazione di una singola implementazione, attenendosi al principio secco standardizzare.

Con un'architettura a più livelli, le applicazioni possono imporre restrizioni in cui i livelli possono comunicare con altri livelli. Ciò consente di ottenere l'incapsulamento. Quando un livello viene modificato o sostituito, dovrebbero essere interessati solo i livelli che funzionano con esso. Limitando che dipendono dal livelli in cui gli altri livelli, l'impatto delle modifiche possono essere ridotti in modo che una singola modifica non influisce sull'intera applicazione.

Livelli (e l'incapsulamento) rendono molto più semplice sostituire la funzionalità all'interno dell'applicazione. Ad esempio, un'applicazione utilizzi inizialmente il proprio database di SQL Server per la persistenza, ma in seguito possibile scegliere di usare una strategia di persistenza basato su cloud, o uno dietro un'API web. Se l'applicazione è incapsulato correttamente l'implementazione di persistenza all'interno di un livello logico, tale livello specifico di SQL Server potrebbe essere sostituita con una nuova implementazione dell'interfaccia pubblica stesso.

Oltre a potenziale di swapping implementazioni in risposta alle modifiche future nei requisiti, livelli dell'applicazione possono rendere più semplice eseguire lo swapping su implementazioni a scopo di test. Anziché scrivere test che operano con il livello di dati reali o dell'interfaccia utente dell'applicazione, questi livelli possono essere sostituiti in fase di test con implementazioni false che forniscono noti le risposte alle richieste. In genere i test in questo modo molto più veloce e più semplici da scrivere rispetto all'esecuzione di esecuzione test nuovamente infrastruttura reale dell'applicazione.

Disposizione logica è una tecnica comune per migliorare l'organizzazione del codice nelle applicazioni software aziendali e sono disponibili diversi modi in cui codice può essere organizzato in livelli.

> [!NOTE]
> *Livelli* rappresentano la separazione logica all'interno dell'applicazione. Nel caso in cui la logica dell'applicazione viene distribuita fisicamente per separare i processi o i server, tali destinazioni di distribuzione fisica separata sono detti *livelli*. È possibile e molto comune, disporre di un'applicazione di N livelli che viene distribuita in un singolo livello.

## <a name="traditional-n-layer-architecture-applications"></a>Applicazioni di architettura tradizionale "Livello di N"

L'organizzazione più comune di logica dell'applicazione in livelli è illustrato nella figura 5-2.

**Figura 5-2.** Livelli di una tipica applicazione.

![](./media/image5-2.png)

Questi livelli vengono spesso abbreviati come interfaccia utente, BLL (Business Logic Layer) e DAL (Data Access Layer). Utilizzando questa architettura, gli utenti inviano richieste attraverso il livello di interfaccia utente, interagisce solo con il livello Business LOGIC. Il livello Business LOGIC, a sua volta, può chiamare per le richieste di accesso ai dati. Il livello di interfaccia utente consigliabile non apportare tutte le richieste alle DAL direttamente, né deve interagire con la persistenza direttamente tramite altri mezzi. Allo stesso modo, il livello Business LOGIC devono solo interagire con la persistenza passando DAL. In questo modo, ogni livello è la propria responsabilità nota.

Uno svantaggio di questo approccio a livelli tradizionale è che le dipendenze in fase di compilazione eseguono dall'alto verso il basso. Vale a dire il livello di interfaccia utente dipende da BLL, che dipende DAL. Ciò significa che il livello Business LOGIC, che in genere contiene la logica più importante nell'applicazione, è dipendente nel dettagli di implementazione di accesso ai dati (e spesso l'esistenza di un database). Test di logica di business in un'architettura di questo tipo è spesso difficile, che richiedono un database di prova. Il principio di inversione di dipendenza è utilizzabile per risolvere questo problema, come illustrato nella sezione successiva.

Figura 5-3 viene illustrata una soluzione di esempio, suddividere l'applicazione in tre progetti da responsabilità (o livello).

**Figura 5-3.** Una semplice applicazione monolitica con tre progetti.

![](./media/image5-3.png)

Anche se l'applicazione utilizza diversi progetti per scopi organizzativi, viene ancora distribuito come una singola unità e i relativi client verranno interagire con esso come un'app web singolo. In questo modo molto semplice processo di distribuzione. Figura 5-4 viene illustrata la modalità cui tale applicazione potrebbe essere ospitato utilizzando Windows Azure.

![](./media/image5-4.png)

**Figura 5-4.** Distribuzione semplice dell'App Web di Azure

Come l'applicazione deve aumentare, soluzioni di distribuzione più complesso e affidabile possono essere necessarie. Figura 5-5 viene mostrato un esempio di un piano di distribuzione più complesso che supporta funzionalità aggiuntive.

![](./media/image5-5.png)

**Figura 5-5.** Distribuzione di un'app web a un servizio App di Azure

Internamente, organizzazione del progetto in più progetti in base alle responsabilità consente di migliorare la manutenibilità dell'applicazione.

Questa unità può essere scalata verticale o in modo da sfruttare la scalabilità su richiesta basato su cloud. La scalabilità verticale comporta l'aggiunta aggiuntivi della CPU, memoria, spazio su disco o altre risorse per i server che ospita l'app. Scalabilità orizzontale si intende aggiungere altre istanze di tali server, se si tratta di server fisici o macchine virtuali. Quando l'applicazione è ospitata in più istanze, un bilanciamento del carico viene utilizzato per assegnare le richieste a istanze singole app.

L'approccio più semplice per il ridimensionamento di un'applicazione web in Azure consiste nel configurare manualmente la scalabilità nel piano di servizio App dell'applicazione. Figura 5-6 mostra una schermata dashboard Azure appropriato per configurare il numero di istanze definiti da un'app.

![](./media/image5-6.png)

**Figura 5-6.** Piano di servizio App scalabilità in Azure.

## <a name="clean-architecture"></a>Nuova architettura

Le applicazioni che seguono il principio di inversione di dipendenza, nonché i principi di progettazione la (DDD) tendono a giungere a un'architettura simile. Questa architettura è passato molti nomi nel corso degli anni. Uno dei nomi è stato architettura vite, seguita dalle porte e schede. Più di recente, è stato indicato come la [architettura ad anello](http://jeffreypalermo.com/blog/the-onion-architecture-part-1/) o [architettura pulita](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html). È questo il cognome, architettura pulita, che viene utilizzato come base per descrivere l'architettura di questa e-book.

> [!NOTE]
> Il termine che parziale architettura può essere applicato alle applicazioni che utilizzano principi DDD anche per quelli che non vengono compilati utilizzando DDD. Nel caso della prima, può essere indicata questa combinazione come "Architettura DDD pulita".

Architettura pulita inserisce il modello di applicazione e la logica di business al centro dell'applicazione. Anziché logica di business dipendono da altri problemi di infrastruttura o accesso ai dati, questa dipendenza è invertita: dettagli dell'infrastruttura e l'implementazione variano a seconda di base dell'applicazione. Questo risultato viene ottenuto mediante la definizione di astrazioni o interfacce, nell'elemento principale dell'applicazione, che quindi vengono implementati da tipi definiti nel livello di infrastruttura. Un modo comune per la visualizzazione di questa architettura consiste nell'utilizzare una serie di cerchi concentrici, simile a un anello. Figura 5-X Mostra un esempio di questo tipo di rappresentazione dell'architettura.

![](./media/image5-7.png)

**Figura 5-7.** Architettura pulita. visualizzazione ad anello

In questo diagramma, le dipendenze del flusso verso il cerchio più interno. In questo modo, si noterà che i componenti di base di applicazione (che accetta il nome dalla relativa posizione alla base di questo diagramma) non ha dipendenze da altri livelli applicazione. Al centro molto sono entità e le interfacce dell'applicazione. All'esterno, ma ancora nell'elemento principale dell'applicazione, sono servizi di dominio, che in genere implementano le interfacce definite in cerchio interno. Di fuori di componenti di base dell'applicazione, sia l'interfaccia utente e i livelli di infrastruttura dipendono dalle Application Core, ma non tra loro (necessariamente).

Figura 5-X viene illustrato un diagramma livello orizzontale più tradizionale che rispecchia maggiormente la dipendenza tra l'interfaccia utente e ad altri livelli.

![](./media/image5-8.png)

**Figura 5-8.** Architettura pulita. visualizzazione orizzontale livello

Si noti che le frecce a tinta unita rappresentano le dipendenze in fase di compilazione, mentre la freccia tratteggiata rappresenta una dipendenza di runtime. Mediante la nuova architettura, il livello di interfaccia utente funziona con le interfacce definite nell'elemento principale dell'applicazione in fase di compilazione e idealmente non deve avere alcuna conoscenza dei tipi di implementazione definita nel livello di infrastruttura. In fase di esecuzione, tuttavia, questi tipi di implementazione sarà necessari per l'app da eseguire, in modo che dovrà essere presente e cablata fino alle interfacce di base dell'applicazione tramite l'inserimento di dipendenze.

Figura 5-9 è illustrata una visualizzazione più dettagliata dell'architettura di un'applicazione ASP.NET Core quando compilato seguendo questi suggerimenti.

![Architettura di base ASPNET](./media/image5-9.png)

**Figura 5-9.** Diagramma dell'architettura di ASP.NET Core seguente architettura pulita.

Poiché i componenti di base di applicazione non dipende da infrastruttura, è molto semplice scrivere unit test automatizzati per questo livello. Nelle figure da 5 a 10 e 11 di 5 mostra il test di adattamento in questa architettura.

![UnitTestCore](./media/image5-10.png)

**Figura 5-10.** Unit test di base dell'applicazione in isolamento.

![IntegrationTests](./media/image5-11.png)

**Figura 5-11.** Test di integrazione delle implementazioni di infrastruttura con dipendenze esterne.

Poiché il livello di interfaccia utente non dispone di qualsiasi dipendenza diretta per i tipi definiti nel progetto di infrastruttura, è allo stesso modo molto semplice eseguire lo swapping implementazioni per semplificare il test o in risposta alle variazioni dei requisiti dell'applicazione. Utilizzo predefinito di ASP.NET Core e il supporto per l'inserimento di dipendenze rende il modo più appropriato per applicazioni monolitico non semplice struttura questa architettura.

Per le applicazioni monolitiche i progetti di componenti di base dell'applicazione, l'infrastruttura e interfaccia utente vengono tutti eseguiti come una singola applicazione. Architettura dell'applicazione di runtime potrebbe essere simile a come nella figura 5-12.

![Architettura di base ASPNET 2](./media/image5-12.png)

**Figura 5-12.** Architettura del runtime dell'applicazione ASP.NET di base di esempio.

### <a name="organizing-code-in-clean-architecture"></a>Organizzazione del codice nella nuova architettura

In una soluzione nuova architettura, ogni progetto dispone di responsabilità precise. Di conseguenza, alcuni tipi apparterrà in ogni progetto e spesso sono disponibili le cartelle corrispondenti a questi tipi di progetto appropriato.

La base dell'applicazione contiene il modello di business, che include le entità, servizi e interfacce. Tali interfacce includono astrazioni per le operazioni che verranno eseguite utilizzando l'infrastruttura, ad esempio l'accesso ai dati, accesso al file system, chiamate di rete e così via. Talvolta i servizi o le interfacce definite in questo livello saranno necessario lavorare con i tipi non entità che non hanno dipendenze su un'interfaccia utente o dell'infrastruttura. Questi può essere definiti come semplice dati trasferire oggetti DTO.

> ### <a name="application-core-types"></a>Tipi di base dell'applicazione
> -   Entità (business classi del modello che vengono rese persistenti)
> -   Interfacce
> -   Servizi
> -   DTO

Il progetto di infrastruttura in genere comprendono le implementazioni di accesso ai dati. In una tipica applicazione web ASP.NET Core, si includerà DbContext Entity Framework, le migrazioni di Core EF che sono stati definiti e classi di implementazione di accesso ai dati. È il modo più comune per eseguire un'astrazione di codice di implementazione di accesso ai dati tramite l'utilizzo del [progettuale Repository](http://deviq.com/repository-pattern/).

Oltre alle implementazioni di accesso ai dati, il progetto di infrastruttura deve contenere le implementazioni dei servizi che devono interagire con problemi di infrastruttura. Questi servizi devono implementare le interfacce definite nell'elemento principale dell'applicazione e pertanto infrastruttura deve avere un riferimento al progetto principale dell'applicazione.

> ### <a name="infrastructure-types"></a>Tipi di infrastruttura
> -   Tipi di base EF (DbContext, migrazioni)
> -   Tipi di implementazione (repository) di accesso ai dati
> -   Servizi di infrastruttura specifici (FileLogger, SmtpNotifier e così via)

Il layer dell'interfaccia utente in un'applicazione ASP.NET MVC di base sarà il punto di ingresso per l'applicazione e sarà un progetto ASP.NET MVC di base. Questo progetto deve fare riferimento al progetto principale dell'applicazione e relativi tipi devono interagire con l'infrastruttura esclusivamente tramite le interfacce definite nell'applicazione principale. Nessun creazione diretta di istanze di (o statiche chiamate a) i tipi di livello dell'infrastruttura devono essere consentiti nel livello dell'interfaccia utente.

> ### <a name="ui-layer-types"></a>Tipi di livelli dell'interfaccia utente
> -   Controller
> -   Filtri
> -   Visualizzazioni
> -   ViewModel
> -   Avvio

La classe di avvio è responsabile per la configurazione dell'applicazione e per il collegamento dei tipi di implementazione di interfacce, consentendo l'inserimento di dipendenze per il corretto funzionamento in fase di esecuzione.

> [!NOTE]
> Per associare l'inserimento di dipendenze in ConfigureServices nel file Startup.cs del progetto dell'interfaccia utente, il progetto potrebbe essere necessario fare riferimento al progetto di infrastruttura. Questa dipendenza può essere eliminata più facilmente utilizzando un contenitore DI personalizzati. Ai fini di questo esempio, l'approccio più semplice è il progetto di interfaccia utente fare riferimento al progetto di infrastruttura.

## <a name="monolithic-applications-and-containers"></a>Contenitori e le applicazioni monolitiche 

È possibile compilare un singolo e monolitico distribuzione applicazione basata su Web o un servizio e distribuirlo come un contenitore. All'interno dell'applicazione, potrebbe non essere monolitico ma organizzati in diverse librerie, componenti o livelli. Esternamente è un singolo contenitore come un singolo processo, una singola applicazione web o singolo servizio.

Per gestire questo modello, si distribuisce un singolo contenitore per rappresentare l'applicazione. Per applicare la scalabilità, è sufficiente aggiungere altre copie con un bilanciamento del carico in primo piano. La semplicità proviene da un'unica distribuzione in un singolo contenitore o di una macchina virtuale di gestione.

![](./media/image5-13.png)

È possibile includere più componenti/librerie o interni livelli all'interno di ogni contenitore, come illustrato nella figura 5-X. Ma, dopo l'entità contenitore di *"svolge una funzione, un contenitore e fa in un unico processo*", il modello monolitico potrebbe verificarsi un conflitto.

Lo svantaggio di questo approccio viene fornito se/quando si espande l'applicazione, che li richiede di scala. Se l'intera applicazione ridimensionata, non è effettivamente un problema. Tuttavia, nella maggior parte dei casi, alcune parti dell'applicazione sono utilizzati i punti di riduzione che richiedono scalabilità, mentre gli altri componenti sono minore.

Utilizzando l'esempio tipico di e-commerce; che cos'è probabilmente necessario ridimensionare è il componente di informazioni di prodotto. Molti clienti più sfogliare i prodotti di acquistare le licenze. Numero di clienti Usa carrello di utilizzare la pipeline di pagamento. I clienti meno aggiungono commenti o visualizzarne la cronologia di acquisto. E, probabilmente è solo un numero limitato di dipendenti, in un'area singola, che devono gestire il contenuto e le campagne di marketing. Per la progettazione monolitica la scala, tutto il codice viene distribuito più volte.

Oltre a scala tutto il problema, le modifiche apportate a un singolo componente necessitano completa la riesecuzione del test dell'intera applicazione e una ridistribuzione completa di tutte le istanze.

L'approccio monolitico è comune e molte organizzazioni sono lo sviluppo con questo approccio architetturale. Molti hanno buone sufficiente risultati, mentre altri raggiunge i limiti. Molti progettati le applicazioni in questo modello, poiché gli strumenti e l'infrastruttura sono troppo difficili da creare architetture orientate ai servizi (SOA) e visualizzano non ha la necessità, fino a quando l'app di dimensioni sono aumentate. Se che si riscontrano i limiti dell'approccio monolitico, suddivisione dell'app per poter sfruttare più contenitori e microservizi potrebbe essere il successivo passaggio logico.

![](./media/image5-14.png)

Distribuzione di applicazioni monolitiche in Microsoft Azure, è possibile utilizzare le macchine virtuali dedicate per ogni istanza. Utilizzando [set di scalabilità di macchine Virtuali di Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), è possibile ridimensionare le macchine virtuali. [Servizi App Azure](https://azure.microsoft.com/services/app-service/) possono eseguire applicazioni monolitiche e scalare facilmente istanze senza la necessità di gestire le macchine virtuali. Servizi App di Azure è possibile eseguire singole istanze di contenitori di Docker, nonché semplificando la distribuzione. Usando Docker, è possibile distribuire una singola macchina virtuale come host Docker ed eseguire più istanze. Tramite il bilanciamento di Azure, come illustrato nella figura 5-14, è possibile gestire la scalabilità.

La distribuzione agli host diversi può essere gestita con le tecniche tradizionali di distribuzione. L'host Docker possono essere gestiti con comandi come **docker eseguire** eseguita manualmente o tramite l'automazione, ad esempio, la pipeline di recapito continuo (CD).

### <a name="monolithic-application-deployed-as-a-container"></a>Qualsiasi applicazione distribuita come contenitore

Esistono vantaggi dell'utilizzo di contenitori per gestire le distribuzioni applicazione monolitico. Le istanze di contenitori di ridimensionamento è molto più veloce e semplice rispetto alla distribuzione di macchine virtuali aggiuntive. Anche quando si usa il set di scalabilità di macchine Virtuali di scala di macchine virtuali, hanno ora all'istanza. Quando viene distribuita come istanze dell'applicazione, la configurazione dell'app viene gestita come parte della macchina virtuale.

Distribuzione degli aggiornamenti, come immagini Docker è molto più veloce e rete efficiente. Le immagini docker iniziano in genere espresso in secondi, velocizzando l'implementazione. Chiudere un'istanza di Docker è facile come emittente un **stop docker** comando, in genere completato in meno di un secondo.

I contenitori sono intrinsecamente non modificabili in base alla progettazione e non occorre preoccuparsi di macchine virtuali danneggiate, mentre gli script di aggiornamento abbia dimenticato di account per alcuni configurazione specifica o a sinistra di file su disco.

Mentre l'App monolitica possono trarre vantaggio da Docker, interruzione dell'applicazione monolitico nei sistemi di sottoscrizione che possono essere ridimensionati, sviluppato e distribuito singolarmente potrebbe essere il punto di ingresso nell'area di autenticazione di microservizi.

> ### <a name="references--common-web-architectures"></a>Riferimenti: architetture Web comuni
> - **L'architettura di pulizia**  
> <https://8thlight.com/blog/Uncle-Bob/2012/08/13/the-Clean-Architecture.HTML>
> - **L'architettura ad anello**  
> <http://jeffreypalermo.com/blog/the-Onion-Architecture-part-1/>
> - **Il modello di Repository**  
> <http://deviq.com/repository-pattern/>
> - **Esempio di architettura Pulisci soluzione**  
> <https://github.com/ardalis/cleanarchitecture>
> - **Architettura di e-book di Microservizi** <http://aka.ms/MicroservicesEbook>

>[!div class="step-by-step"]
[Precedente] (dell'architettura principles.md) [Avanti] (comuni-client-side-web-technologies.md)
