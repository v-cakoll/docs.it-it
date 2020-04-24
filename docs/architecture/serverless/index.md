---
title: 'App serverless: architettura, modelli e implementazione di Azure'
description: Guida all'architettura serverless. Informazioni su quando, come e perché implementare un'architettura serverless, anziché un'architettura IaaS [infrastruttura distribuita come servizio] o PaaS [piattaforma distribuita come servizio], per le applicazioni aziendali.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/22/2020
ms.openlocfilehash: 16e658a99feda6537189a45b53da514e67766999
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135691"
---
# <a name="serverless-apps-architecture-patterns-and-azure-implementation"></a>App serverless: architettura, modelli e implementazione di Azure

![Screenshot che mostra le app senza server e-book cover.](./media/index/serverless-apps-cover-v3.png)

**Edizione v 3.0** -aggiornata in funzioni di Azure V3

> Download disponibile all'indirizzo: <https://aka.ms/serverlessbookpdf>

PUBBLICATO DA

Microsoft Developer Division, team dei prodotti .NET e Visual Studio

Una divisione di Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright &copy; 2018-2020 di Microsoft Corporation

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.

 Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi. Nessuna associazione reale o connessione è intenzionale o può essere desunta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.

Mac e macOS sono marchi registrati di Apple Inc.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Author (Autore):

> **[Jeremy Likness](https://twitter.com/jeremylikness)**, Senior .NET Data Program Manager, Microsoft Corp.

Collaboratore:

> **[Cecil Phillip](https://twitter.com/cecilphillip)**, senior cloud Advocate, Microsoft Corp.

Editor:

> **[Bill Wagner](https://twitter.com/billwagner)**, Senior Content Developer, Microsoft Corp.

> **[Maira Wenzel](https://twitter.com/mairacw)**, Senior Content Developer, Microsoft Corp.

Collaboratori e revisori:

> **[Steve Smith](https://twitter.com/ardalis)**, Owner, Ardalis Services.

## <a name="introduction"></a>Introduzione

Il senza [Server](https://azure.microsoft.com/solutions/serverless/) è l'evoluzione delle piattaforme cloud nella direzione del codice nativo cloud puro. Un'infrastruttura serverless avvicina gli sviluppatori alla logica di business senza le preoccupazioni derivanti dall'infrastruttura. Questo modello non implica che non è richiesto "alcun server", ma piuttosto che sono richiesti "meno server". Il codice serverless è basato sugli eventi. Il codice può essere attivato da qualsiasi elemento, da una richiesta Web HTTP tradizionale a un timer o dal risultato del caricamento di un file. L'infrastruttura serverless consente la scalabilità immediata per soddisfare richieste diverse e offre la micro-fatturazione per un reale "pagamento a consumo". L'elaborazione serverless richiede un nuovo approccio e un nuovo modo di pensare alla compilazione delle applicazioni e non è la soluzione ideale per tutti i problemi. Come sviluppatore, è necessario stabilire:

- Quali sono i vantaggi e gli svantaggi dell'elaborazione serverless?
- Perché sarebbe opportuno considerare l'elaborazione serverless per le proprie applicazioni?
- Come è possibile compilare, testare, distribuire e gestire il codice serverless?
- Dove avrebbe senso migrare il codice a serverless nelle applicazioni esistenti e qual è il modo migliore per compiere questa trasformazione?

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida è incentrata sullo sviluppo nativo nel cloud delle applicazioni che usano l'elaborazione serverless. Il manuale evidenzia i vantaggi ed espone i potenziali svantaggi dello sviluppo di app serverless e fornisce un sondaggio sulle architetture serverless. Molti esempi di come usare l'elaborazione serverless sono illustrati insieme a diversi schemi progettuali serverless.

Questa guida illustra i componenti della piattaforma serverless di Azure e si concentra in modo specifico nell'implementazione serverless mediante [Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-overview). Verranno fornite informazioni sui trigger e sulle associazioni e su come implementare le app serverless che si basano sullo stato usando funzioni durevoli. Infine, scenari aziendali e case study forniranno contesto e frame di riferimento per determinare se serverless è l'approccio giusto per i progetti.

## <a name="evolution-of-cloud-platforms"></a>Evoluzione di piattaforme cloud

L'elaborazione serverless rappresenta il culmine delle varie iterazioni delle piattaforme cloud. L'evoluzione è iniziata con i componenti in metallo nel data center e ha progredito attraverso l'architettura IaaS (infrastruttura distribuita come servizio) e PaaS (piattaforma distribuita come servizio).

![Evoluzione da locale a serverless](./media/serverless-evolution-iaas-paas.png)

Prima del cloud, esisteva un confine distinguibile tra lo sviluppo e le operazioni. Distribuire un'applicazione significava rispondere a una miriade di domande come:

- Che tipo di hardware deve essere installato?
- Come è protetto l'accesso fisico al computer?
- Il data center richiede un gruppo di continuità (UPS)?
- Dove vengono inviati i backup di archiviazione?
- È necessaria l'alimentazione ridondante?

L'elenco continua e i costi erano altissimi. In molte situazioni, i reparti IT sono stati costretti a gestire incredibili sprechi. Gli sprechi sono dovuti all'eccessiva allocazione di server come computer di backup per il ripristino di emergenza e i server di standby per abilitare la scalabilità orizzontale. Fortunatamente, l'introduzione della tecnologia di virtualizzazione, ad esempio [Hyper-V](/virtualization/hyper-v-on-windows/about/), con macchine virtuali (VM) ha dato luogo all'infrastruttura distribuita come servizio (IaaS). L'infrastruttura virtualizzata ha consentito operazioni di configurazione di un set standard di server backbone, determinando un ambiente flessibile in grado di eseguire il provisioning di server univoci "su richiesta". Ancora più importante, la virtualizzazione ha posto le basi per l'utilizzo del cloud per fornire macchine virtuali "come servizio". Le aziende hanno potuto facilmente smettere di preoccuparsi dell'alimentazione ridondante o dei computer fisici. Si sono concentrate invece sull'ambiente virtuale.

IaaS ha comunque un costo importante perché ci sono varie attività che richiedono interventi. Queste attività includono:

- L'applicazione di patch e il backup dei server.
- L'installazione di pacchetti.
- Mantenere aggiornato il sistema operativo.
- Monitoraggio dell'applicazione.

L'evoluzione successiva ha ridotto i costi grazie a PaaS (piattaforma distribuita come servizio). Con PaaS, il provider di servizi cloud gestisce i sistemi operativi, le patch di protezione e anche i pacchetti necessari per supportare una determinata piattaforma. Anziché creare una macchina virtuale e quindi configurare .NET e i server Internet Information Services (IIS), gli sviluppatori scelgono semplicemente una "destinazione della piattaforma", ad esempio "applicazione Web" o "endpoint API", e distribuiscono il codice direttamente. Le domande sull'infrastruttura vengono ridotte a:

- Quali sono le dimensioni necessarie dei servizi?
- Come avviene la scalabilità orizzontale dei servizi (aggiunta di altri server o nodi)?
- Come si aumentano i servizi (aumento della capacità dei server o dei nodi di hosting)?

Grazie al codice basato sugli eventi, serverless riduce ulteriormente la necessità di usare i server. Invece di una piattaforma, gli sviluppatori possono concentrarsi su un microservizio che esegue una singola operazione. Le due domande chiave per la compilazione del codice serverless sono:

- Che cosa attiva il codice?
- Che operazioni esegue il codice?

Con serverless, l'infrastruttura non è necessaria. In alcuni casi, lo sviluppatore non avrà necessità di un host. Se un'istanza di IIS Kestrel, Apache o un altro Web server è in esecuzione per gestire le richieste Web, lo sviluppatore si concentra su un trigger HTTP. Il trigger fornisce il payload standard e multipiattaforma per la richiesta. Il payload non solo semplifica il processo di sviluppo, ma facilita il testing e in alcuni casi rende il codice facilmente portabile tra le piattaforme.

Un'altra funzionalità serverless è la micro-fatturazione. È comune per le applicazioni Web ospitare gli endpoint Web API. Nei server tradizionali, nelle implementazioni IaaS e anche PaaS, le risorse per ospitare le API vengono pagate in modo continuativo. Ciò significa che si paga per ospitare gli endpoint, anche quando non vi si accede. Spesso avviene che un'API viene chiamata più di altre e l'intero sistema viene ridimensionato per supportare gli endpoint più diffusi. Serverless consente di ridimensionare ogni endpoint in modo indipendente e pagarne l'utilizzo, in modo che non vengono addebitati costi quando non sono in corso chiamate alle API. La migrazione può in molte circostanze ridurre notevolmente i costi di esercizio per il supporto degli endpoint.

## <a name="what-this-guide-doesnt-cover"></a>Argomenti non trattati dalla guida

Questa guida tratta in particolare degli approcci di architettura e gli schemi progettuali e non è un'analisi approfondita dei dettagli dell'implementazione di Funzioni di Azure, [App per la logica](https://docs.microsoft.com/azure/logic-apps/logic-apps-what-are-logic-apps) o altre piattaforme serverless. Questa Guida non tratta, ad esempio, dei flussi di lavoro avanzati con le app per la logica o funzionalità di Funzioni di Azure, ad esempio la configurazione di Condivisione di risorse tra le origini (CORS), l'applicazione di domini personalizzati o del caricamento di certificati SSL. Questi dettagli sono disponibili nella [documentazione delle Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-reference) online.

### <a name="additional-resources"></a>Risorse aggiuntive

- [Centro architetture di Azure](https://docs.microsoft.com/azure/architecture/)
- [Procedure consigliate per le applicazioni cloud](https://docs.microsoft.com/azure/architecture/best-practices/api-design)

## <a name="who-should-use-the-guide"></a>Destinatari della guida

Questa guida è stata scritta per gli sviluppatori e architetti di soluzioni che desiderano creare applicazioni aziendali con .NET che potrebbero usare componenti serverless in locale o nel cloud. È utile per gli sviluppatori, architetti e responsabili decisionali tecnici interessati a:

- Comprendere i vantaggi e gli svantaggi dello sviluppo serverless
- Scoprire come affrontare l'architettura serverless
- Implementazioni di esempio di app serverless

## <a name="how-to-use-the-guide"></a>Come usare questa guida

La prima parte di questa guida esamina i motivi per cui serverless è un'opzione praticabile tramite il confronto dei vari approcci a diverse architetture. Esamina sia la tecnologia e lo sviluppo del ciclo di vita, perché le decisioni relative all'architettura hanno un impatto su tutti gli aspetti dello sviluppo del software. La guida esamina quindi casi d'uso e schemi progettuali e include le implementazioni di riferimento che usano Funzioni di Azure. Ogni sezione contiene risorse aggiuntive per altre informazioni su una determinata area. La guida termina con le risorse per procedure dettagliate ed esplorazione pratica dell'implementazione serverless.

## <a name="send-your-feedback"></a>Invia commenti e suggerimenti

La guida e gli esempi correlati sono in continua evoluzione, pertanto sono graditi commenti e suggerimenti. Se ci sono commenti sul modo in cui può essere migliorata la guida, usare la sezione commenti e suggerimenti nella parte inferiore di ogni pagina basata sui [problemi di GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Avanti](architecture-approaches.md)
