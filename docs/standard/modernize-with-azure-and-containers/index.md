---
title: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows
description: "Informazioni su come trasferire in modalità lift-and-shift le applicazioni esistenti nei contenitori e nel cloud Azure"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5e1a04a0d8ed151337e00c8147756644dfc9075a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-v10"></a>Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows (v1.0)  

![Immagine di copertina](./media/cover.png)

PUBBLICATO DA  
Microsoft Press e Microsoft DevDiv  
Divisioni di Microsoft Corporation  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2017 Microsoft Corporation  

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro è disponibile gratuitamente in formato di libro elettronico (e-book) attraverso diversi canali Microsoft, ad esempio <http://dot.net/architecture>

Per domande relative a questo libro, inviare un messaggio di posta elettronica a [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.

Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi. Nessuna associazione o connessione reale è intenzionale o può essere presupposta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo http://www.microsoft.com sono marchi delle società del gruppo Microsoft. Tutti gli altri marchi appartengono ai rispettivi proprietari.

Autore:
> **Cesar de la Torre**, Sr. PM, team di prodotto .NET, Microsoft Corp.

Collaboratori e revisori:
> **Scott Hunter**, Partner Director PM, team di .NET, Microsoft  
> **Paul Yuknewicz**, Principal PM Manager, team di Visual Studio Tools, Microsoft  
> **Lisa Guthrie**, Sr. PM, team di Visual Studio Tools, Microsoft  
> **Ankit Asthana**, Principal PM Manager, team di .NET, Microsoft  
> **Unai Zorrilla**, sviluppatore capo, Plain Concepts  
> **Javier Valero**, Chief Operating Officer di Grupo Solutio  

## <a name="introduction"></a>Introduzione

Quando si decide di modernizzare le applicazioni Web e spostarle nel cloud, non è necessario riprogettarle completamente. La riprogettazione di un'applicazione tramite un approccio avanzato come quello dei microservizi non è sempre un'opzione possibile, a causa delle limitazioni di tempo e costi. A seconda del tipo di applicazione, la riprogettazione di un'app potrebbe anche non essere necessaria. Per ottimizzare l'efficacia della strategia di migrazione cloud dell'organizzazione dal punto di vista economico, è importante considerare le esigenze dell'azienda e i requisiti delle app. È necessario determinare:

-   Quali app richiedono una trasformazione o una riprogettazione.

-   Quali app devono essere modernizzate solo parzialmente.

-   Quali app è possibile trasferire in modalità lift-and-shift direttamente nel cloud.

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida è incentrata principalmente su scenari di trasferimento in modalità lift-and-shift e sulla modernizzazione iniziale delle applicazioni Web Microsoft .NET Framework o orientate ai servizi esistenti. Il trasferimento in modalità lift-and-shift è l'azione di spostamento di un carico di lavoro in un ambiente più recente o più moderno senza modificare il codice e l'architettura di base dell'applicazione.

Questa guida descrive come spostare le applicazioni server .NET Framework esistenti direttamente nel cloud modernizzando aree specifiche senza riprogettare l'intera applicazione o riscriverne il codice.

La guida illustra anche i vantaggi dello spostamento delle app nel cloud e della modernizzazione parziale delle app usando un set specifico di nuovi approcci e tecnologie, ad esempio i contenitori di Windows e gli agenti di orchestrazione in Azure.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Percorso di spostamento nel cloud delle applicazioni .NET esistenti

Le organizzazioni scelgono in genere di passare al cloud per ottenere flessibilità e velocità per le applicazioni. Nel cloud è possibile configurare migliaia di server (macchine virtuali) in minuti e non in settimane, che è il tempo in genere necessario per configurare i server locali.

Non c'è un'unica strategia adatta per tutti gli scenari di migrazione delle applicazioni nel cloud. La strategia di migrazione adatta dipende dalle esigenze e dalle priorità dell'organizzazione, oltre che dal tipo di applicazioni di cui si esegue la migrazione. Non tutte le applicazioni giustificano l'investimento per il passaggio a un modello di piattaforma distribuita come servizio ([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) o lo sviluppo di un modello applicativo [nativo del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). In molti casi è possibile adottare un approccio graduale o incrementale per l'investimento nello spostamento degli asset nel cloud, in base alle esigenze aziendali.

Per le applicazioni moderne che offrono il miglior valore e la maggiore flessibilità a lungo termine per l'organizzazione, può essere vantaggioso investire in architetture dell'applicazione *ottimizzate per il cloud* e *native del cloud*. Per ottenere vantaggi significativi dalle applicazioni esistenti o dagli asset legacy è tuttavia importante risparmiare più tempo e denaro possibile per il passaggio al cloud, evitando di riprogettare l'applicazione o modificare il codice.

La figura 1-1 illustra i percorsi che è possibile seguire quando si spostano applicazioni .NET esistenti nel cloud in fasi incrementali.

 ![Percorsi di modernizzazione per servizi e applicazioni .NET esistenti](./media/image1-1.png)

> **Figura 1-1**. Percorsi di modernizzazione per servizi e applicazioni .NET esistenti

Ogni approccio alla migrazione presenta diversi vantaggi e motivi per sceglierlo. Per la migrazione di app nel cloud è possibile scegliere un approccio unico oppure scegliere determinati componenti da più approcci. Le singole applicazioni non sono limitate a un singolo approccio o stato di maturità. Ad esempio, un approccio ibrido comune prevede determinati componenti in locale e altri nel cloud.

Ai primi due livelli di migrazione, è possibile semplicemente trasferire le applicazioni in modalità lift-and-shift:

**Livello 1: Pronto per l'infrastruttura cloud**: con questo approccio di migrazione, le applicazioni locali correnti vengono semplicemente riallocate o spostate in una piattaforma di infrastruttura distribuita come servizio ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)). Le app hanno quasi la stessa composizione di prima, ma vengono ora distribuite in macchine virtuali nel cloud.

**Livello 2: Pronto per lo sviluppo DevOps cloud**: a questo livello, dopo un trasferimento iniziale in modalità lift-and-shift, sempre senza riprogettare o modificare il codice, è possibile ottenere vantaggi ancora maggiori dall'esecuzione dell'app nel cloud. È possibile migliorare la flessibilità delle applicazioni per distribuirle più velocemente ridefinendo i processi delle operazioni di sviluppo aziendale (DevOps). A tale scopo, è possibile usare tecnologie come i contenitori di Windows, basati sul motore Docker. I contenitori rimuovono i conflitti causati dalle dipendenze dell'applicazione quando si esegue la distribuzione in più fasi. I contenitori usano inoltre servizi cloud gestiti aggiuntivi correlati a pipeline di integrazione continua e distribuzione continua (CI/CD), dati e monitoraggio.

Il terzo livello di maturità rappresenta l'obiettivo finale nel cloud, ma è facoltativo per numerose app ed esula dall'ambito di questa guida:

**Livello 3: Ottimizzato per il cloud**: in genere, questo approccio alla migrazione è determinato dalle esigenze aziendali e mira a modernizzare le applicazioni cruciali. A questo livello si usano servizi PaaS per spostare le app in piattaforme di elaborazione PaaS. Si implementa un'architettura di applicazioni e microservizi [nativa del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) per consentire l'evoluzione delle applicazioni con flessibilità a lungo termine e per raggiungere nuovi livelli di scalabilità. Questo tipo di modernizzazione richiede in genere una progettazione specifica per il cloud. Spesso è necessario scrivere nuovo codice, in particolare quando si passa a modelli basati su microservizi e applicazioni nativi del cloud. Questo approccio può consentire di ottenere vantaggi che sono difficili da ottenere in un ambiente applicativo monolitico e locale.

La tabella 1-1 descrive i vantaggi principali di ogni approccio alla migrazione o alla modernizzazione e i motivi per scegliere tale approccio.

> | **Pronto per l'infrastruttura cloud** <br /> *Lift-and-shift* | **Pronto per lo sviluppo DevOps cloud** <br /> *Lift-and-shift* | **Ottimizzato per il cloud** *Modernizzazione/refactoring/riscrittura* |
> |---|---|---|
> | **Destinazione di elaborazione dell'applicazione** |
> | Applicazioni distribuite in macchine virtuali in Azure | App monolitiche in contenitori o app a più livelli distribuite in macchine virtuali, Azure Service Fabric o servizio contenitore di Azure (ovvero Kubernetes) | Microservizi in contenitori o normali applicazioni basate su PaaS in Servizio app di Azure, Azure Service Fabric o servizio contenitore di Azure (ovvero Kubernetes) |
> | **Destinazione dei dati** |
> | SQL o qualsiasi database relazionale in una macchina virtuale | Istanza gestita di database SQL di Azure | Database SQL di Azure, Azure Cosmos DB o altri database NoSQL |
> | **Vantaggi**|
> | <li>Nessuna necessità di riprogettazione o nuovo codice <li> Lavoro minimo per una migrazione rapida <li> Minimo comune denominatore supportato in Azure <li> Garanzie di disponibilità di base <li> Dopo lo spostamento nel cloud, è più semplice aumentare ancora di più il livello di modernizzazione | <li>Nessuna necessità di riprogettazione o nuovo codice <li> I contenitori richiedono un minimo di lavoro in più rispetto alle macchine virtuali <li> Distribuzione migliorata e flessibilità DevOps per il rilascio grazie ai contenitori <li> Densità maggiore e costi di distribuzione minori <li> Portabilità di app e dipendenze <li> Disponibilità elevata e orchestrazione grazie al servizio contenitore di Azure (o Kubernetes) e ad Azure Service Fabric <li> Applicazione di patch a nodi/macchine virtuali in Service Fabric <li> Flessibilità delle destinazioni host: macchine virtuali o set di scalabilità di macchine virtuali di Azure, servizio contenitore di Azure (o Kubernetes), Service Fabric e opzioni future basate su contenitori | <li>Progettazione per il cloud, refactoring, nuovo codice necessario <li> Approcci nativi del cloud basati su microservizi <li> Nuove app Web, monolitiche, a più livelli, resilienti per il cloud e ottimizzate per il cloud <li> Servizi completamente gestiti <li> Applicazione di patch automatica <li> Ottimizzazione per la scalabilità <li> Ottimizzazione per la flessibilità autonoma in base al sottosistema <li> Approccio basato su distribuzione e DevOps <li> Processi DevOps avanzati, come slot e strategie di distribuzione <li> Destinazioni Paas e degli agenti di orchestrazione: Servizio app di Azure, servizio contenitore di Azure (o Kubernetes), Azure Service Fabric e soluzioni PaaS future basate su contenitori |
> | **Sfide** |
> | <li> Valore cloud inferiore, all'infuori del cambiamento nelle spese operative e della chiusura di data center <li> Pochi elementi gestiti: nessuna applicazione di patch a sistema operativo o middleware, eventuali soluzioni di infrastruttura, come Terraform, Spinnaker o Puppet | <li> L'uso di contenitori è un passaggio aggiuntivo della curva di apprendimento in scenari non modificabili | <li> Potrebbe essere necessario un lavoro significativo di refactoring o riscrittura del codice (tempo e budget maggiori) |
>> **Tabella 1-1.** Vantaggi e sfide dei percorsi di modernizzazione per servizi e applicazioni .NET esistenti

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Principali tecnologie e architetture in base al livello di maturità

La prima versione delle applicazioni .NET Framework è stata .NET Framework 1.0, rilasciata verso la fine del 2001. Le aziende sono quindi passate a versioni più recenti (ad esempio 2.0, 3.5 e .NET 4.x). La maggior parte di queste applicazioni veniva eseguita in Windows Server e Internet Information Server (IIS) e usava un database relazionale, ad esempio SQL Server, Oracle, MySQL o un'altra soluzione RDBMS.

La maggior parte delle applicazioni .NET oggi si basa su .NET Framework 4. x o anche .NET Framework 3.5, e usa framework Web come ASP.NET MVC, Web Form ASP.NET, API Web ASP.NET, Windows Communication Foundation (WCF), ASP.NET SignalR e Pagine Web ASP.NET. Queste radicate tecnologie .NET Framework dipendono da Windows. Questa dipendenza è importante da considerare se si esegue semplicemente la migrazione di app legacy e si vuole apportare modifiche minime all'infrastruttura dell'applicazione.

La figura 1-2 mostra le tecnologie e gli stili di architettura principali usati per ognuno dei tre livelli di maturità cloud:

![Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti](./media/image1-2.png)

> **Figura 1-2.** Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti

La figura 1-2 evidenzia gli scenari più comuni, ma per quanto riguarda l'architettura sono possibili numerose varianti ibride e miste. I modelli di maturità si applicano ad esempio non solo alle architetture monolitiche nelle app Web esistenti, ma anche alle varianti orientate ai servizi e a più livelli e ad altri stili dell'architettura.

Ogni livello di maturità nel processo di modernizzazione è associato alle tecnologie e agli approcci principali seguenti:

-   **Pronto per l'infrastruttura cloud** (riallocazione o trasferimento in modalità lift-and-shift di base): come primo passaggio, molte organizzazioni vogliono semplicemente attuare rapidamente una strategia di migrazione nel cloud. In questo caso, le applicazioni vengono semplicemente riallocate. La riallocazione, nella maggior parte dei casi, può essere automatizzata tramite [Azure Migrate](https://aka.ms/azuremigrate), un servizio che fornisce indicazioni, informazioni e meccanismi a supporto della migrazione in Azure tramite strumenti cloud come [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) e [Servizio Migrazione del database di Azure](https://azure.microsoft.com/campaigns/database-migration/). È anche possibile configurare la riallocazione manualmente, in modo da poter apprendere alcuni dettagli dell'infrastruttura per gli asset quando si spostano le app legacy nel cloud. È ad esempio possibile spostare le applicazioni nelle macchine virtuali in Azure con pochissime modifiche, probabilmente apportando solo alcune modifiche minime alla configurazione. La rete, in questo caso, è simile a un ambiente locale, in particolare se si creano reti virtuali in Azure.

-   **Pronto per lo sviluppo DevOps cloud** (modalità lift-and-shift avanzata): questo modello consiste nell'apportare poche ma importanti ottimizzazioni della distribuzione per ottenere alcuni vantaggi significativi dal cloud, senza modificare l'architettura di base dell'applicazione. Il passaggio fondamentale consiste nell'aggiungere il supporto dei [contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) alle applicazioni .NET Framework esistenti. Questo passaggio importante di aggiunta di contenitori non richiede la modifica del codice, quindi il lavoro necessario per il trasferimento in modalità lift-and-shift è piuttosto contenuto. È possibile usare strumenti come [Image2Docker](https://github.com/docker/communitytools-image2docker-win) o Visual Studio, con i relativi strumenti per [Docker](https://www.docker.com/). Visual Studio sceglie automaticamente impostazioni predefinite intelligenti per le applicazioni ASP.NET e le immagini dei contenitori di Windows. Questi strumenti offrono sia un ciclo interno rapido che un percorso veloce per l'uso dei contenitori in Azure. Ne risulta una maggiore flessibilità per la distribuzione in più ambienti. Quando si passa all'ambiente di produzione, è quindi possibile distribuire i contenitori di Windows in agenti di orchestrazione come [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) o il [servizio contenitore di Azure](https://azure.microsoft.com/services/container-service/) (Kubernetes, DC/OS o Swarm). Durante questa fase di modernizzazione iniziale, è anche possibile aggiungere asset dal cloud, ad esempio il monitoraggio con strumenti come [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview), pipeline di integrazione continua/distribuzione continua per i cicli di vita delle app con [Visual Studio Team Services](https://www.visualstudio.com/team-services/) e molti altri servizi per le risorse dati disponibili in Azure. È ad esempio possibile modificare un'app Web monolitica originariamente distribuita in modo tradizionale con [Web Form ASP.NET](https://www.asp.net/web-forms) o [ASP.NET MVC](https://www.asp.net/mvc), distribuendola invece con i contenitori di Windows. Quando si usano i contenitori di Windows, è anche necessario eseguire la migrazione dei dati in un database nell'[Istanza gestita di database SQL di Azure](https://docs.microsoft.com/azure/sql-database/), senza dover modificare l'architettura di base dell'applicazione.

-   **Ottimizzato per il cloud**: come già menzionato, l'obiettivo finale della modernizzazione delle applicazioni nel cloud è quello di basare il sistema su piattaforme PaaS come [Servizio app di Azure](https://azure.microsoft.com/services/app-service/). Le piattaforme PaaS sono incentrate sulle applicazioni Web moderne ed estendono le app con nuovi servizi basati su [elaborazione senza server](https://azure.microsoft.com/overview/serverless-computing/) e piattaforme come [Funzioni di Azure](https://azure.microsoft.com/services/functions/). Il secondo e più avanzato scenario di questo modello di maturità riguarda le architetture di microservizi e le applicazioni [native del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications), che in genere usano agenti di orchestrazione come [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) o il [servizio contenitore di Azure](https://azure.microsoft.com/services/container-service/) (Kubernetes, DC/OS o Swarm). Questi agenti di orchestrazione sono creati appositamente per i microservizi e le applicazioni multicontenitore. Tutti questi approcci (ad esempio microservizi e PaaS) richiedono in genere la scrittura di nuovo codice, personalizzato per piattaforme PaaS specifiche o allineato ad architetture specifiche, ad esempio i microservizi.

La figura 1-3 illustra le tecnologie interne che è possibile usare per ogni livello di maturità:

![Tecnologie interne per ogni livello di maturità della modernizzazione](./media/image1-3.png)

> **Figura 1-3.** Tecnologie interne per ogni livello di maturità della modernizzazione

## <a name="lift-and-shift-scenarios"></a>Scenari di trasferimento in modalità lift-and-shift

Per le migrazioni con trasferimento in modalità lift-and-shift, tenere presente che è possibile scegliere tra diverse varianti per gli scenari dell'applicazione. Se si rialloca solo l'applicazione, lo scenario potrebbe essere simile a quello illustrato nella figura 1-4, dove si usano le macchine virtuali nel cloud solo per l'applicazione e per il server di database.

![Esempio di scenario IaaS puro nel cloud](./media/image1-4.png)

> **Figura 1-4**. Esempio di scenario IaaS puro nel cloud

Procedendo, si potrebbe avere un'applicazione pronta per lo sviluppo DevOps cloud pura che usa elementi solo di quel livello di maturità. Oppure si potrebbe avere un'applicazione con uno stato intermedio, con alcuni elementi pronti per l'infrastruttura cloud e atri pronti per lo sviluppo DevOps cloud (un modello con possibilità di scelta o misto), come nella figura 1-5.

![Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori](./media/image1-5.png)

> **Figura 1-5.** Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori

Come scenario ideale per la migrazione di numerose applicazioni .NET Framework esistenti c'è poi la migrazione a un'applicazione pronta per lo sviluppo DevOps cloud, che consente di ottenere grandi vantaggi con poco lavoro. Questo approccio apre anche la strada all'ottimizzazione per il cloud, come possibile passaggio futuro. La figura 1-6 mostra un esempio.

![Scenario di esempio di app pronte per lo sviluppo DevOps cloud, con contenitori di Windows e servizi gestiti](./media/image1-6.png)

> **Figura 1-6.** Scenario di esempio di app pronte per lo sviluppo DevOps cloud, con contenitori di Windows e servizi gestiti

Procedendo ulteriormente, è possibile estendere l'applicazione pronta per lo sviluppo DevOps cloud aggiungendo alcuni microservizi per scenari specifici. In questo modo si passerebbe parzialmente al livello nativo del cloud nel modello ottimizzato per il cloud, che esula dall'ambito della presente guida.


## <a name="what-this-guide-does-not-cover"></a>Argomenti non trattati dalla guida

Questa guida descrive un sottoinsieme specifico di scenari di esempio, come illustrato nella figura 1-7. La guida è incentrata solo su scenari di trasferimento in modalità lift-and-shift e, in definitiva, sul modello pronto per lo sviluppo DevOps cloud. Ne modello pronto per lo sviluppo DevOps cloud un'applicazione .NET Framework viene modernizzata usando i contenitori di Windows e componenti aggiuntivi come il monitoraggio e le pipeline di integrazione continua e distribuzione continua. Ogni componente è fondamentale per la distribuzione delle applicazioni nel cloud in modo più rapido e con maggiore flessibilità.

![Trasferimento in modalità lift-and-shift e modernizzazione iniziale per il passaggio ad applicazioni pronte per lo sviluppo DevOps cloud](./media/image1-7.png)

> **Figura 1-7.** Trasferimento in modalità lift-and-shift e modernizzazione iniziale per il passaggio ad applicazioni pronte per lo sviluppo DevOps cloud

L'obiettivo di questa guida è specifico. Viene illustrato il percorso da seguire per trasferire in modalità lift-and-shift le applicazioni .NET esistenti senza riprogettarle né modificare il codice. In definitiva, viene illustrato come rendere un'applicazione pronta per lo sviluppo DevOps cloud.

Questa guida non mostra come lavorare con le applicazioni native del cloud, ad esempio come passare ad architetture di microservizi. Per riprogettare le applicazioni o per creare applicazioni completamente nuove basate su microservizi, vedere l'e-book [.NET Microservices: Architecture for containerized .NET applications](https://aka.ms/microservicesebook) (Microservizi .NET: architettura per applicazioni .NET in contenitori).

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft** (e-book scaricabile): [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

-   **.NET Microservices: Architecture for containerized .NET applications** (Microservizi .NET: architettura per applicazioni .NET in contenitori) (e-book scaricabile): [*https://aka.ms/microservicesebook*](https://aka.ms/microservicesebook)

-   **Architecting modern web applications with ASP.NET Core and Azure** (Progettazione di applicazioni Web moderne con ASP.NET Core e Azure) (e-book scaricabile): [*https://aka.ms/webappebook*](https://aka.ms/webappebook)

## <a name="who-should-use-this-guide"></a>Destinatari della guida

Questa guida è destinata agli sviluppatori e ai progettisti di soluzioni che vogliono modernizzare le applicazioni ASP.NET esistenti basate su .NET Framework, per ottenere una migliore flessibilità nella distribuzione e nel rilascio delle applicazioni.

Questa guida è utile anche per i responsabili delle decisioni tecniche, ad esempio un progettista aziendale o un responsabile/direttore dello sviluppo che vuole semplicemente una panoramica dei vantaggi che è possibile ottenere usando i contenitori di Windows ed eseguendo la distribuzione nel cloud con Microsoft Azure.

## <a name="how-to-use-this-guide"></a>Come usare questa guida

Questa guida illustra i motivi per cui è consigliabile modernizzare le applicazioni esistenti e i vantaggi specifici offerti dall'uso di contenitori di Windows quando si spostano le app nel cloud. Il contenuto dei primi capitoli di questa guida è destinato ai progettisti e ai responsabili delle decisioni tecniche che vogliono una panoramica generale, senza informazioni dettagliate relative all'implementazione e agli aspetti tecnici.

L'ultimo capitolo di questa guida presenta diverse procedure dettagliate relative a scenari di distribuzione specifici. Nella guida vengono presentate le versioni abbreviate delle procedure dettagliate, per riepilogare gli scenari ed evidenziarne i vantaggi. Le procedure dettagliate complete analizzano in dettaglio le fasi di configurazione e implementazione e sono pubblicate come set di [post wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki) nello stesso [repository GitHub](https://github.com/dotnet-architecture/eShopModernizing) pubblico in cui si trovano le app di esempio correlate (illustrate nella sezione successiva). L'ultimo capitolo e le procedure wiki dettagliate in GitHub sono di particolare interesse per gli sviluppatori e i progettisti che vogliono concentrarsi sui dettagli dell'implementazione.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>App di esempio per la modernizzazione delle app legacy: eShopModernizing

Il repository [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) in GitHub offre due applicazioni di esempio che simulano le applicazioni Web monolitiche legacy. Un'app Web è sviluppata con ASP.NET MVC, mentre la seconda è sviluppata con Web Form ASP.NET. Entrambe le app Web sono basate su .NET Framework tradizionale. Le app di esempio non usano .NET Core o ASP.NET Core in quanto devono rappresentare applicazioni .NET Framework esistenti/legacy da modernizzare.

Entrambe le app di esempio hanno una seconda versione, con codice modernizzato, e sono piuttosto semplici. La differenza più importante tra le versioni delle app è che le seconde versioni usano i contenitori di Windows come opzione di distribuzione. Nelle seconde versioni sono state introdotte anche alcune aggiunte, ad esempio BLOB di archiviazione di Azure per la gestione delle immagini, Azure Active Directory per la gestione della sicurezza e Azure Application Insights per il monitoraggio e il controllo delle applicazioni.

## <a name="send-us-your-feedback"></a>Inviateci i vostri commenti!

Questa guida è stata scritta per aiutare a comprendere le opzioni per migliorare e modernizzare le applicazioni Web .NET esistenti. La guida e le applicazioni di esempio correlate sono in continua evoluzione. Invitiamo gli utenti a inviare il proprio feedback. È possibile inviare eventuali commenti su come rendere la guida ancora più utile all'indirizzo: [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
[avanti](lift-and-shift-existing-apps-azure-iaas.md)
