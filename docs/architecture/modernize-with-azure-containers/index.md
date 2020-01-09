---
title: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows (seconda edizione)
description: Questo e-book contiene informazioni su come trasferire in modalità lift-and-shift e modernizzare le applicazioni esistenti nei contenitori e nel cloud di Azure.
ms.date: 04/28/2018
ms.openlocfilehash: fa20e606c9a1364fbdf8c9a58c8703420d9e65a9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714577"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows (seconda edizione)

![Immagine di copertina della guida alla modernizzazione delle applicazioni .NET.](./media/index/web-application-guide-cover-image.png)

PUBBLICATO DA  
Microsoft Press e Microsoft DevDiv  
Divisioni di Microsoft Corporation  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2018 Microsoft Corporation  

Tutti i diritti riservati. Nessuna parte del contenuto di questo libro può essere riprodotta in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro è disponibile gratuitamente in formato di libro elettronico (e-book) tramite diversi canali Microsoft, ad esempio <https://dot.net/architecture>.

Per domande relative a questo libro, inviare un messaggio di posta elettronica all' [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.

Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi. Nessuna associazione o connessione reale è intenzionale o può essere presupposta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft. Tutti gli altri marchi appartengono ai rispettivi proprietari.

Autore:
> **Cesar de la Torre**, Senior PM, team del prodotto .NET, Microsoft Corp.

Collaboratori e revisori:
> **Scott Hunter**, Partner Director PM, team di .NET, Microsoft  
> **Paul Yuknewicz**, Principal PM Manager, team di Visual Studio Tools, Microsoft  
> **Lisa Guthrie**, Senior PM, team di Visual Studio Tools, Microsoft  
> **Ankit Asthana**, Principal PM Manager, team di .NET, Microsoft  
> **Unai Zorrilla**, sviluppatore capo, Plain Concepts  
> **Javier Valero**, Chief Operating Officer di Grupo Solutio  

## <a name="introduction"></a>Introduzione

Quando si decide di modernizzare applicazioni o servizi Web esistenti e spostarli nel cloud, non è necessario riprogettare le app completamente. La riprogettazione di un'applicazione tramite un approccio avanzato come quello dei microservizi non è sempre un'opzione possibile, a causa delle limitazioni di tempo e costi. A seconda del tipo di applicazione, la riprogettazione di un'app potrebbe anche non essere necessaria. Per ottimizzare l'efficacia della strategia di migrazione cloud dell'organizzazione dal punto di vista economico, è importante considerare le esigenze dell'azienda e i requisiti delle app. È necessario determinare:

- Quali app richiedono una trasformazione o una riprogettazione.

- Quali app devono essere modernizzate solo parzialmente.

- Quali app è possibile trasferire in modalità lift-and-shift direttamente nel cloud.

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida è incentrata principalmente sulla modernizzazione iniziale di applicazioni Web o orientate ai servizi Microsoft .NET Framework esistenti, ovvero sull'azione di spostare un carico di lavoro in un ambiente più recente o più moderno senza modificare in modo significativo il codice e l'architettura di base dell'applicazione.

La guida illustra anche i vantaggi dello spostamento delle app nel cloud e della modernizzazione parziale delle app usando un set specifico di nuovi approcci e tecnologie, ad esempio i contenitori di Windows e le piattaforme di calcolo correlate nei contenitori di Windows che supportano Azure.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Percorso di spostamento nel cloud delle applicazioni .NET esistenti

Le organizzazioni scelgono in genere di passare al cloud per ottenere flessibilità e velocità per le applicazioni. Nel cloud è possibile configurare migliaia di server (macchine virtuali) in minuti e non in settimane, che è il tempo in genere necessario per configurare i server locali.

Non c'è un'unica strategia adatta per tutti gli scenari di migrazione delle applicazioni nel cloud. La strategia di migrazione adatta dipende dalle esigenze e dalle priorità dell'organizzazione, oltre che dal tipo di applicazioni di cui si esegue la migrazione. Non tutte le applicazioni giustificano l'investimento per il passaggio a un modello di piattaforma distribuita come servizio ([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) o lo sviluppo di un modello applicativo [nativo del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). In molti casi è possibile adottare un approccio graduale o incrementale per l'investimento nello spostamento degli asset nel cloud, in base alle esigenze aziendali.

Per le applicazioni moderne che offrono il miglior valore e la maggiore flessibilità a lungo termine per l'organizzazione, può essere vantaggioso investire in architetture dell'applicazione *native del cloud*. Per ottenere vantaggi significativi dalle applicazioni che rappresentano asset esistenti o legacy, è tuttavia importante dedicare la minore quantità di tempo e denaro possibile al passaggio al cloud, evitando di riprogettare l'applicazione o modificare il codice.

La figura 1-1 illustra i percorsi che è possibile seguire quando si spostano applicazioni .NET esistenti nel cloud in fasi incrementali.

 ![Percorsi di modernizzazione per servizi e applicazioni .NET esistenti](./media/image1-1.png)

**Figura 1-1**. Percorsi di modernizzazione per servizi e applicazioni .NET esistenti

Ogni approccio alla migrazione presenta diversi vantaggi e motivi per sceglierlo. Per la migrazione di app nel cloud è possibile scegliere un approccio unico oppure scegliere determinati componenti da più approcci. Le singole applicazioni non sono limitate a un singolo approccio o stato di maturità. Ad esempio, un approccio ibrido comune prevede determinati componenti in locale e altri nel cloud.

La definizione e la breve spiegazione per ogni livello di maturità dell'applicazione sono le seguenti:

**Livello 1: applicazioni predisposte per l'infrastruttura cloud** : in questo approccio di migrazione è sufficiente migrare o riospitare le applicazioni locali correnti in una piattaforma di infrastruttura distribuita come servizio ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)). Le app hanno quasi la stessa composizione di prima, ma vengono ora distribuite in macchine virtuali nel cloud.
Questo semplice tipo di migrazione è in genere noto nel settore come "lift-and-shift".

**Livello 2: applicazioni ottimizzate** per il cloud: a questo livello e ancora senza riprogettare o modificare codice significativo, è possibile ottenere vantaggi aggiuntivi dall'esecuzione dell'app nel cloud con tecnologie moderne come contenitori e servizi aggiuntivi gestiti dal cloud. È possibile migliorare la flessibilità delle applicazioni per distribuirle più velocemente ridefinendo i processi delle operazioni di sviluppo aziendale (DevOps). A tale scopo, è possibile usare tecnologie come i contenitori di Windows, basati sul motore Docker. I contenitori rimuovono le complicazioni causate dalle dipendenze dell'applicazione quando si esegue la distribuzione in più fasi. In questo modello di maturità è possibile distribuire contenitori in infrastrutture IaaS o PaaS usando allo stesso tempo servizi aggiuntivi gestiti dal cloud correlati a database, cache come servizio, monitoraggio e pipeline di integrazione continua/distribuzione continua (CI/CD).

Il terzo livello di maturità rappresenta l'obiettivo finale nel cloud, ma è facoltativo per numerose app ed esula dall'ambito di questa guida:

**Livello 3: applicazioni native del cloud** : questo approccio di migrazione è in genere determinato dalle esigenze aziendali e mira alla modernizzazione delle applicazioni cruciali. A questo livello si usano servizi PaaS per spostare le app in piattaforme di elaborazione PaaS. Si implementa un'architettura di applicazioni e microservizi [nativa del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) per consentire l'evoluzione delle applicazioni con flessibilità a lungo termine e per raggiungere nuovi livelli di scalabilità. Questo tipo di modernizzazione richiede in genere una progettazione specifica per il cloud. Spesso è necessario scrivere nuovo codice, in particolare quando si passa a modelli basati su microservizi e applicazioni nativi del cloud. Questo approccio può consentire di ottenere vantaggi che sono difficili da ottenere in un ambiente applicativo monolitico e locale.

La tabella 1-1 descrive i vantaggi principali di ogni approccio alla migrazione o alla modernizzazione e i motivi per scegliere tale approccio.

| **Pronto per l'infrastruttura cloud** <br /> *Lift-and-shift* | **Ottimizzato per il cloud** <br /> *Modernizzare* | **Nativo del cloud** <br /> *Modernizzare, riprogettare e riscrivere* |
|---|---|---|
| **Destinazione di elaborazione dell'applicazione** |
| Applicazioni distribuite in macchine virtuali in Azure | App monolitiche o a più livelli distribuite in Servizio app di Azure, istanza di contenitore di Azure, macchine virtuali con contenitori o servizio Azure Kubernetes | Microservizi in contenitori nel servizio Azure Kubernetes e/o microservizi serverless basati su Funzioni di Azure. |
| **Destinazione dei dati** |
| SQL o qualsiasi database relazionale in una macchina virtuale | Istanza gestita di database SQL di Azure o un altro database gestito nel cloud. | Database con granularità fine per microservizio, basati sul database SQL di Azure, Azure Cosmos DB o un altro database gestito nel cloud |
| **Vantaggi**|
| <li>Nessuna necessità di riprogettazione o nuovo codice <li> Lavoro minimo per una migrazione rapida <li> Minimo comune denominatore supportato in Azure <li> Garanzie di disponibilità di base <li> Dopo lo spostamento nel cloud, è più semplice aumentare ancora di più il livello di modernizzazione | <li> Nessuna necessità di riprogettazione <li> Modifiche minime a codice/configurazione <li> Distribuzione migliorata e flessibilità DevOps per il rilascio grazie ai contenitori <li> Densità maggiore e costi di distribuzione minori <li> Portabilità di app e dipendenze <li> Flessibilità degli obiettivi host: approcci PaaS o IaaS | <li> Progettazione per il cloud, si ottengono i migliori vantaggi dal cloud, ma è necessario nuovo codice <li> Approcci nativi del cloud basati su microservizi <li> Applicazioni cruciali moderne, iperscalabile con resilienza del cloud <li> Servizi completamente gestiti <li> Ottimizzazione per la scalabilità <li> Ottimizzazione per la flessibilità autonoma in base al sottosistema <li> Approccio basato su distribuzione e DevOps |
| **Sfide** |
| <li> Valore cloud inferiore, all'infuori del cambiamento nelle spese operative e della chiusura di data center <li> Gestione minima: nessuna applicazione di patch del sistema operativo o del middleware; potrebbe usare soluzioni di infrastruttura, ad esempio bonifica, Spinnaker o Puppet | <li> L'uso di contenitori è un passaggio aggiuntivo della curva di apprendimento per gli sviluppatori e le operazioni IT <li> Le pipeline DevOps e CI/CD sono in genere obbligatorie per questo approccio. Se non sono già presenti nella cultura dell'organizzazione, potrebbe trattarsi di una sfida aggiuntiva| <li> Richiede la riprogettazione per le app cloud native e le architetture di microservizi e in genere richiede interventi notevoli di refactoring o riscrittura del codice durante la modernizzazione (aumento di tempi e budget)|
> **Tabella 1-1.** Vantaggi e sfide dei percorsi di modernizzazione per servizi e applicazioni .NET esistenti

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Principali tecnologie e architetture in base al livello di maturità

La prima versione delle applicazioni .NET Framework è stata .NET Framework 1.0, rilasciata verso la fine del 2001. Le aziende sono quindi passate a versioni più recenti (ad esempio 2.0, 3.5 e .NET 4.x). La maggior parte di queste applicazioni veniva eseguita in Windows Server e Internet Information Server (IIS) e usava un database relazionale, ad esempio SQL Server, Oracle, MySQL o un'altra soluzione RDBMS.

La maggior parte delle applicazioni .NET oggi si basa su .NET Framework 4. x o anche .NET Framework 3.5, e usa framework Web come ASP.NET MVC, Web Form ASP.NET, API Web ASP.NET, Windows Communication Foundation (WCF), ASP.NET SignalR e Pagine Web ASP.NET. Queste radicate tecnologie .NET Framework dipendono da Windows. Questa dipendenza è importante da considerare se si esegue semplicemente la migrazione di app legacy e si vuole apportare modifiche minime all'infrastruttura dell'applicazione.

La figura 1-2 mostra le tecnologie e gli stili di architettura principali usati per ognuno dei tre livelli di maturità cloud:

![Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti](./media/image1-2.png)

**Figura 1-2.** Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti

La figura 1-2 evidenzia gli scenari più comuni, ma per quanto riguarda l'architettura sono possibili numerose varianti ibride e miste. I modelli di maturità si applicano ad esempio non solo alle architetture monolitiche nelle app Web esistenti, ma anche alle varianti orientate ai servizi e a più livelli e ad altri stili dell'architettura. La maggiore concentrazione su uno o l'altro tipo di architettura e sulle tecnologie correlate determina il livello di maturità generale delle applicazioni.

Ogni livello di maturità nel processo di modernizzazione è associato alle tecnologie e agli approcci principali seguenti:

- **Pronto per l'infrastruttura cloud** (riallocazione o lift di base & Shift): come primo passaggio, molte organizzazioni vogliono solo eseguire rapidamente una strategia di migrazione cloud. In questo caso, le applicazioni vengono riallocate. La riallocazione, nella maggior parte dei casi, può essere automatizzata tramite [Azure Migrate](https://aka.ms/azuremigrate), un servizio che fornisce indicazioni, informazioni e meccanismi a supporto della migrazione in Azure tramite strumenti cloud come [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) e [Servizio Migrazione del database di Azure](https://azure.microsoft.com/campaigns/database-migration/). È anche possibile configurare la riallocazione manualmente, in modo da poter apprendere alcuni dettagli dell'infrastruttura per gli asset quando si spostano le app legacy nel cloud. È ad esempio possibile spostare le applicazioni nelle macchine virtuali in Azure con poche modifiche, probabilmente apportando solo modifiche minime alla configurazione. La rete, in questo caso, è simile a un ambiente locale, in particolare se si creano reti virtuali in Azure.

- **Ottimizzato** per il cloud (servizi gestiti e contenitori di Windows): questo modello sta per apportare alcune importanti ottimizzazioni di distribuzione per ottenere alcuni vantaggi significativi dal cloud, senza modificare l'architettura di base dell'applicazione. Il passaggio fondamentale consiste nell'aggiungere il supporto dei [contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) alle applicazioni .NET Framework esistenti. Questo passaggio importante di aggiunta a contenitori non richiede la modifica del codice, quindi il lavoro necessario per il trasferimento in modalità lift-and-shift è contenuto. È possibile usare strumenti come [Image2Docker](https://github.com/docker/communitytools-image2docker-win) o Visual Studio, con i relativi strumenti per [Docker](https://www.docker.com/). Visual Studio sceglie automaticamente impostazioni predefinite intelligenti per le applicazioni ASP.NET e le immagini dei contenitori di Windows. Questi strumenti offrono sia un ciclo interno rapido che un percorso veloce per l'uso dei contenitori in Azure. Ne risulta una maggiore flessibilità per la distribuzione in più ambienti.
Passando quindi all'ambiente di produzione, è possibile distribuire i contenitori di Windows in [app Web per contenitori di Azure](https://azure.microsoft.com/services/app-service/containers/), [Istanze di Azure Container](https://azure.microsoft.com/services/container-instances/) e macchine virtuali di Azure con Windows Server 2016 e i contenitori, se si preferisce un approccio IaaS. Per applicazioni multicontenitore più complesse, valutare la possibilità di usare agenti di orchestrazione come il [servizio Azure Kubernetes](https://azure.microsoft.com/services/container-service/).

Durante questa fase di modernizzazione iniziale, è anche possibile aggiungere asset dal cloud, ad esempio il monitoraggio con strumenti come [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview), pipeline di integrazione continua/distribuzione continua per i cicli di vita delle app con [Azure DevOps Services](https://azure.microsoft.com/services/devops/) e molti altri servizi per le risorse dati disponibili in Azure. È ad esempio possibile modificare un'app Web monolitica originariamente distribuita in modo tradizionale con [Web Form ASP.NET](https://www.asp.net/web-forms) o [ASP.NET MVC](https://www.asp.net/mvc), distribuendola invece con i contenitori di Windows. Quando si usano i contenitori di Windows, è anche necessario eseguire la migrazione dei dati in un database nell'[Istanza gestita di database SQL di Azure](https://docs.microsoft.com/azure/sql-database/), senza dover modificare l'architettura di base dell'applicazione.

- **Nativo del cloud**: come introdotto, è consigliabile pensare all'architettura di applicazioni [native del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) quando si è destinati a applicazioni di grandi dimensioni e complesse con più team di sviluppo indipendenti che lavorano su diversi microservizi che possono essere sviluppati e distribuiti autonomamente. Un altro motivo è la scalabilità granulare e indipendente di ogni microservizio. Questi approcci all'architettura presentano sfide e complessità molto importanti, ma possono essere notevolmente semplificati tramite PaaS cloud e agenti di orchestrazione come il [servizio Azure Kubernetes](https://azure.microsoft.com/services/container-service/) (Kubernetes gestito) e [Funzioni di Azure](https://azure.microsoft.com/services/functions/) per un approccio serverless. Tutti questi approcci (ad esempio microservizi e serverless) richiedono in genere la riprogettazione per il cloud e la scrittura di nuovo codice, adattato a piattaforme PaaS specifiche o allineato ad architetture specifiche, ad esempio i microservizi.

La figura 1-3 illustra le tecnologie interne che è possibile usare per ogni livello di maturità:

![Tecnologie interne per ogni livello di maturità della modernizzazione](./media/image1-3.png)

**Figura 1-3.** Tecnologie interne per ogni livello di maturità della modernizzazione

## <a name="lift-and-shift-scenario"></a>Scenario di trasferimento in modalità lift-and-shift

Per le migrazioni con trasferimento in modalità lift-and-shift, tenere presente che è possibile scegliere tra diverse varianti per gli scenari dell'applicazione. Se si rialloca solo l'applicazione, lo scenario potrebbe essere simile a quello illustrato nella figura 1-4, dove si usano le macchine virtuali nel cloud solo per l'applicazione e per il server di database.

![Esempio di scenario IaaS puro nel cloud](./media/image1-4.png)

**Figura 1-4**. Esempio di scenario IaaS puro nel cloud

## <a name="modernization-scenarios"></a>Scenari di modernizzazione

Per gli scenari di modernizzazione si potrebbe avere un'applicazione ottimizzata per il cloud pura che usa elementi solo di quel livello di maturità. Oppure si potrebbe avere un'applicazione con uno stato intermedio, con alcuni elementi pronti per l'infrastruttura cloud e altri ottimizzati per il cloud (un modello con possibilità di scelta o misto), come nella figura 1-5.

![Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori](./media/image1-5.png)

**Figura 1-5.** Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori

Come scenario ideale per la migrazione di numerose applicazioni .NET Framework esistenti, vi è poi la migrazione a un'applicazione ottimizzata per il cloud, che consente di ottenere grandi vantaggi con poco lavoro. Questo approccio apre anche la strada all'approccio nativo per il cloud, come possibile evoluzione futura. La figura 1-6 mostra un esempio.

![Scenario di esempio di app ottimizzate per il cloud, con contenitori di Windows e servizi gestiti](./media/image1-6.png)

**Figura 1-6.** Scenario di esempio di app ottimizzate per il cloud, con contenitori di Windows e servizi gestiti

Procedendo ulteriormente, è possibile estendere l'applicazione esistente ottimizzata per il cloud aggiungendo alcuni microservizi per scenari specifici. In questo modo si passerebbe parzialmente al livello del modello nativo per il cloud, che non rappresenta l'argomento centrale di queste linee guida.

## <a name="what-this-guide-does-not-cover"></a>Argomenti non trattati dalla guida

Questa guida descrive un sottoinsieme specifico di scenari di esempio, come illustrato nella figura 1-7. La guida è incentrata solo su scenari di trasferimento in modalità lift-and-shift e, in definitiva, sul modello ottimizzato per il cloud. Nel modello ottimizzato per il cloud un'applicazione .NET Framework viene modernizzata usando i contenitori di Windows e componenti aggiuntivi come il monitoraggio e le pipeline di integrazione continua e distribuzione continua. Ogni componente è fondamentale per la distribuzione delle applicazioni nel cloud in modo più rapido e con maggiore flessibilità.

![Il modello nativo del cloud non è trattato in questa guida](./media/image1-7.png)

**Figura 1-7.** Il modello nativo del cloud non è trattato in questa guida

L'obiettivo di questa guida è specifico. Viene illustrato il percorso da seguire per trasferire in modalità lift-and-shift le applicazioni .NET esistenti senza riprogettarle né modificare il codice. Infine, viene illustrato come rendere l'applicazione ottimizzata per il cloud.

Questa guida non mostra come creare applicazioni native del cloud, ad esempio come passare ad architetture di microservizi. Per riprogettare le applicazioni o per creare applicazioni nuovissime basate su microservizi, vedere l'e-book [.NET microservices: architettura per le applicazioni .NET in contenitori](https://aka.ms/microservicesebook).

### <a name="additional-resources"></a>Risorse aggiuntive

- **Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft** (e-book scaricabile) \
  <https://aka.ms/dockerlifecycleebook>

- **Microservizi .NET: architettura per le applicazioni .NET in contenitori** (e-book scaricabile) \
  <https://aka.ms/microservicesebook>

- **Progettazione di applicazioni Web moderne con ASP.NET Core e Azure** (e-book scaricabile) \
  <https://aka.ms/webappebook>

## <a name="who-should-use-this-guide"></a>Destinatari della guida

Questa guida è destinata agli sviluppatori e ai progettisti di soluzioni che vogliono modernizzare applicazioni Web ASP.NET o servizi WCF esistenti basati su .NET Framework, per ottenere una migliore flessibilità nella distribuzione e nel rilascio delle applicazioni.

Questa guida è utile anche per i responsabili delle decisioni tecniche, ad esempio un progettista aziendale o un responsabile/direttore dello sviluppo che vuole semplicemente una panoramica dei vantaggi che è possibile ottenere usando i contenitori di Windows ed eseguendo la distribuzione nel cloud con Microsoft Azure.

## <a name="how-to-use-this-guide"></a>Come usare questa guida

Questa guida illustra i motivi per cui è consigliabile modernizzare le applicazioni esistenti e i vantaggi specifici offerti dall'uso di contenitori di Windows quando si spostano le app nel cloud. Il contenuto dei primi capitoli di questa guida è destinato ai progettisti e ai responsabili delle decisioni tecniche che vogliono una panoramica generale, senza informazioni dettagliate relative all'implementazione e agli aspetti tecnici.

L'ultimo capitolo di questa guida presenta diverse procedure dettagliate relative a scenari di distribuzione specifici. Nella guida vengono presentate le versioni abbreviate delle procedure dettagliate, per riepilogare gli scenari ed evidenziarne i vantaggi. Le procedure dettagliate complete analizzano in dettaglio le fasi di configurazione e implementazione e sono pubblicate come set di [post wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki) nello stesso [repository GitHub](https://github.com/dotnet-architecture/eShopModernizing) pubblico in cui si trovano le app di esempio correlate (illustrate nella sezione successiva). L'ultimo capitolo e le procedure wiki dettagliate in GitHub sono di particolare interesse per gli sviluppatori e i progettisti che vogliono concentrarsi sui dettagli dell'implementazione.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>App di esempio per la modernizzazione delle app legacy: eShopModernizing

Il repository [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) in GitHub offre due applicazioni di esempio che simulano le applicazioni Web monolitiche legacy. Un'app Web viene sviluppata usando ASP.NET MVC. La seconda app Web viene sviluppata usando ASP.NET Web Forms e la terza app è un'app a più livelli con un'app desktop client WinForms che utilizza un back-end del servizio WCF. Tutte queste app sono basate su .NET Framework tradizionale. Le app di esempio non usano .NET Core o ASP.NET Core in quanto devono rappresentare applicazioni .NET Framework esistenti/legacy da modernizzare.

Queste app di esempio hanno una seconda versione, con codice modernizzato, e sono piuttosto semplici. La differenza più importante tra le versioni delle app è che le seconde versioni usano i contenitori di Windows come opzione di distribuzione. Nelle seconde versioni sono state introdotte anche alcune aggiunte, ad esempio BLOB di archiviazione di Azure per la gestione delle immagini, Azure Active Directory per la gestione della sicurezza e Azure Application Insights per il monitoraggio e il controllo delle applicazioni.

## <a name="send-your-feedback"></a>Invia commenti e suggerimenti

Questa guida è stata scritta per aiutare a comprendere le opzioni disponibili per migliorare e modernizzare le applicazioni Web .NET esistenti. La guida e le applicazioni di esempio correlate sono in continua evoluzione. I commenti degli utenti sono molto apprezzati! È possibile inviare eventuali commenti su come rendere la guida ancora più utile all'indirizzo: [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
>[Successivo](lift-and-shift-existing-apps-azure-iaas.md) <!-- Next Chapter -->
