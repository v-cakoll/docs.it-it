---
title: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows (2a edizione)
description: Questo e-book consente di acquisire e spostare e modernizzare le applicazioni esistenti nel cloud e nei contenitori di Azure.
ms.date: 04/28/2018
ms.openlocfilehash: ab2b58441af7aed6a8cd868751339b555a345565
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "70222852"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows (2a edizione)

![Immagine di copertina della Guida alla modernizzazione delle applicazioni .NET.](./media/index/web-application-guide-cover-image.png)

PUBBLICATO DA  
Microsoft Press e Microsoft DevDiv  
Divisioni di Microsoft Corporation  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2018 Microsoft Corporation  

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro è disponibile gratuitamente sotto forma di libro elettronico (e-book) disponibile attraverso più canali in Microsoft, ad esempio <https://dot.net/architecture>.

Per domande relative a questo libro, inviare un messaggio di posta elettronica a [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. Le opinioni, le opinioni e le informazioni espresse nel presente documento, inclusi URL e altri riferimenti a siti Web Internet, possono cambiare senza preavviso.

Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi. Nessuna associazione o connessione reale è intenzionale o può essere presupposta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft. Tutti gli altri marchi appartengono ai rispettivi proprietari.

Autore:
> **Cesar de la Torre**, Sr. pm, team di prodotto .NET, Microsoft Corp.

Collaboratori e revisori:
> **Scott Hunter**, Partner Director PM, team di .NET, Microsoft  
> **Paul Yuknewicz**, Principal PM Manager, team di Visual Studio Tools, Microsoft  
> **Lisa Guthrie**, Sr. PM, strumenti di Visual Studio Team, Microsoft  
> **Ankit Asthana**, Principal PM Manager, team di .NET, Microsoft  
> **Unai Zorrilla**, sviluppatore capo, Plain Concepts  
> **Javier Valero**, Chief Operating Officer di Grupo Solutio  

## <a name="introduction"></a>Introduzione

Quando si decide di modernizzare le applicazioni o i servizi Web e di spostarli nel cloud, non è necessariamente necessario riprogettare completamente le app. La riprogettazione di un'applicazione con un approccio avanzato come i microservizi non è sempre un'opzione a causa dei vincoli di costo e tempo. A seconda del tipo di applicazione, potrebbe anche non essere necessario riprogettare un'app. Per ottimizzare l'efficacia della strategia di migrazione cloud dell'organizzazione dal punto di vista economico, è importante considerare le esigenze dell'azienda e i requisiti delle app. È necessario determinare:

- Quali app richiedono una trasformazione o una riprogettazione.

- Quali app devono essere modernizzate solo parzialmente.

- Quali app è possibile trasferire in modalità lift-and-shift direttamente nel cloud.

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida è incentrata principalmente sulla modernizzazione iniziale di applicazioni esistenti di Microsoft .NET Framework Web o orientate ai servizi, ovvero sull'azione di spostare un carico di lavoro in un ambiente più recente o più moderno senza modificare significativamente il codice dell'applicazione. e l'architettura di base. 

Questa guida evidenzia inoltre i vantaggi derivanti dallo spostamento delle app nel cloud e dalla modernizzazione parziale delle app usando un set specifico di nuove tecnologie e approcci, come i contenitori Windows e le piattaforme di calcolo correlate in Azure che supportano i contenitori di Windows.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Percorso di spostamento nel cloud delle applicazioni .NET esistenti

Le organizzazioni scelgono in genere di passare al cloud per ottenere flessibilità e velocità per le applicazioni. Nel cloud è possibile configurare migliaia di server (macchine virtuali) in minuti e non in settimane, che è il tempo in genere necessario per configurare i server locali.

Non c'è un'unica strategia adatta per tutti gli scenari di migrazione delle applicazioni nel cloud. La strategia di migrazione adatta dipende dalle esigenze e dalle priorità dell'organizzazione, oltre che dal tipo di applicazioni di cui si esegue la migrazione. Non tutte le applicazioni giustificano l'investimento per il passaggio a un modello di piattaforma distribuita come servizio ([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) o lo sviluppo di un modello applicativo [nativo del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). In molti casi è possibile adottare un approccio graduale o incrementale per l'investimento nello spostamento degli asset nel cloud, in base alle esigenze aziendali.

Per le applicazioni moderne con l'agilità e il valore migliori a lungo termine per l'organizzazione, è possibile trarre vantaggio dall'investimento in architetture di applicazioni *native del cloud* . Tuttavia, per le applicazioni che sono asset esistenti o legacy, la chiave consiste nel dedicare tempo e denaro minimo (nessuna riprogettazione o modifica del codice), spostando nel cloud, per realizzare vantaggi significativi.

La figura 1-1 illustra i percorsi che è possibile seguire quando si spostano applicazioni .NET esistenti nel cloud in fasi incrementali.

 ![Percorsi di modernizzazione per servizi e applicazioni .NET esistenti](./media/image1-1.png)

> **Figura 1-1**. Percorsi di modernizzazione per servizi e applicazioni .NET esistenti

Ogni approccio alla migrazione presenta diversi vantaggi e motivi per sceglierlo. Per la migrazione di app nel cloud è possibile scegliere un approccio unico oppure scegliere determinati componenti da più approcci. Le singole applicazioni non sono limitate a un singolo approccio o stato di maturità. Ad esempio, un approccio ibrido comune prevede determinati componenti in locale e altri nel cloud.

La definizione e la breve spiegazione per ogni livello di maturità dell'applicazione sono le seguenti:

**Livello 1: Applicazioni predisposte** per l'infrastruttura cloud: In questo approccio di migrazione è sufficiente migrare o riospitare le applicazioni locali correnti in una piattaforma di infrastruttura distribuita come servizio ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)). Le app hanno quasi la stessa composizione di prima, ma vengono ora distribuite in macchine virtuali nel cloud.
Questo semplice tipo di migrazione è in genere noto nel settore come "Lift & Shift".

**Livello 2: Applicazioni ottimizzate** per il cloud: A questo livello, sempre senza riprogettare o modificare codice significativo, è possibile ottenere vantaggi aggiuntivi dall'esecuzione dell'app nel cloud con tecnologie moderne come contenitori e servizi aggiuntivi gestiti dal cloud. È possibile migliorare la flessibilità delle applicazioni per distribuirle più velocemente ridefinendo i processi delle operazioni di sviluppo aziendale (DevOps). A tale scopo, è possibile usare tecnologie come i contenitori di Windows, basate sul motore docker. I contenitori rimuovono l'attrito causato dalle dipendenze dell'applicazione quando si esegue la distribuzione in più fasi. In questo modello di maturità è possibile distribuire contenitori in IaaS o PaaS usando servizi aggiuntivi gestiti dal cloud correlati a database, cache come servizio, monitoraggio e pipeline di integrazione continua/distribuzione continua (CI/CD).

Il terzo livello di maturità rappresenta l'obiettivo finale nel cloud, ma è facoltativo per numerose app ed esula dall'ambito di questa guida:

**Livello 3: Applicazioni native** del cloud: Questo approccio di migrazione è in genere determinato dalle esigenze aziendali e mira alla modernizzazione delle applicazioni cruciali. A questo livello si usano servizi PaaS per spostare le app in piattaforme di elaborazione PaaS. Si implementa un'architettura di applicazioni e microservizi [nativa del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) per consentire l'evoluzione delle applicazioni con flessibilità a lungo termine e per raggiungere nuovi livelli di scalabilità. Questo tipo di modernizzazione richiede in genere una progettazione specifica per il cloud. Spesso è necessario scrivere nuovo codice, in particolare quando si passa a modelli basati su microservizi e applicazioni nativi del cloud. Questo approccio può consentire di ottenere vantaggi che sono difficili da ottenere in un ambiente applicativo monolitico e locale.

La tabella 1-1 descrive i vantaggi principali di ogni approccio alla migrazione o alla modernizzazione e i motivi per scegliere tale approccio.

| **Pronto per l'infrastruttura cloud** <br /> *Lift-and-shift* | **Ottimizzato per il cloud** <br /> *Modernizzare* | **Nativo del cloud** <br /> *Modernizzare, riprogettare e riscrivere* |
|---|---|---|
| **Destinazione di elaborazione dell'applicazione** |
| Applicazioni distribuite in macchine virtuali in Azure | App monolitiche o a più livelli distribuite nel servizio app Azure, istanza di contenitore di Azure, VM con contenitori o AKS (servizio Azure Kubernetes) | Microservizi in contenitori in Azure Kubernetes Service (AKS) e/o microservizi senza server basati su funzioni di Azure. |
| **Destinazione dei dati** |
| SQL o qualsiasi database relazionale in una macchina virtuale | Istanza gestita di database SQL di Azure o un altro database gestito nel cloud. | Database con granularità fine per microservizio, basati sul database SQL di Azure, Azure Cosmos DB o un altro database gestito nel cloud |
| **Vantaggi**|
| <li>Nessuna riprogettazione, nessun nuovo codice <li> Lavoro minimo per una migrazione rapida <li> Minimo comune denominatore supportato in Azure <li> Garanzie di disponibilità di base <li> Dopo lo spostamento nel cloud, è più semplice aumentare ancora di più il livello di modernizzazione | <li> Nessuna ridefinizione dell'architettura <li> Modifiche minime al codice/configurazione <li> Distribuzione migliorata e flessibilità DevOps per il rilascio grazie ai contenitori <li> Densità maggiore e costi di distribuzione minori <li> Portabilità di app e dipendenze <li> Flessibilità delle destinazioni host: Approcci PaaS o IaaS | <li> Architetto per il cloud, si ottengono i migliori vantaggi dal cloud, ma è necessario un nuovo codice <li> Approcci nativi del cloud basati su microservizi <li> Applicazioni mission-critical moderne, iperscalabile con resilienza del cloud <li> Servizi completamente gestiti <li> Ottimizzazione per la scalabilità <li> Ottimizzazione per la flessibilità autonoma in base al sottosistema <li> Approccio basato su distribuzione e DevOps |
| **Sfide** |
| <li> Valore cloud inferiore, all'infuori del cambiamento nelle spese operative e della chiusura di data center <li> Gestione minima: Nessuna applicazione di patch del sistema operativo o del middleware; potrebbe usare soluzioni di infrastruttura, ad esempio bonifica, Spinnaker o Puppet | <li> Inserimento è un passaggio aggiuntivo nella curva di apprendimento per gli sviluppatori e le operazioni IT <li> Le pipeline DevOps e CI/CD sono in genere ' a must ' per questo approccio. Se non è attualmente presente nelle impostazioni cultura dell'organizzazione, potrebbe trattarsi di una sfida aggiuntiva| <li> Richiede la riarchitettura per le app cloud native e le architetture di microservizi e in genere richiede il refactoring o la riscrittura di codice significativo durante la modernizzazione (aumento del tempo e del budget)|
> **Tabella 1-1.** Vantaggi e sfide dei percorsi di modernizzazione per servizi e applicazioni .NET esistenti

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Principali tecnologie e architetture in base al livello di maturità

La prima versione delle applicazioni .NET Framework è stata .NET Framework 1.0, rilasciata verso la fine del 2001. Le aziende sono quindi passate a versioni più recenti (ad esempio 2.0, 3.5 e .NET 4.x). La maggior parte di queste applicazioni è stata eseguita in Windows Server e Internet Information Server (IIS) ed è stato usato un database relazionale, ad esempio SQL Server, Oracle, MySQL o qualsiasi altro RDBMS.

La maggior parte delle applicazioni .NET oggi si basa su .NET Framework 4. x o anche .NET Framework 3.5, e usa framework Web come ASP.NET MVC, Web Form ASP.NET, API Web ASP.NET, Windows Communication Foundation (WCF), ASP.NET SignalR e Pagine Web ASP.NET. Queste radicate tecnologie .NET Framework dipendono da Windows. Questa dipendenza è importante da considerare se si esegue semplicemente la migrazione di app legacy e si vuole apportare modifiche minime all'infrastruttura dell'applicazione.

La figura 1-2 mostra le tecnologie e gli stili di architettura principali usati per ognuno dei tre livelli di maturità cloud:

![Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti](./media/image1-2.png)

> **Figura 1-2.** Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti

La figura 1-2 evidenzia gli scenari più comuni, ma per quanto riguarda l'architettura sono possibili numerose varianti ibride e miste. I modelli di maturità si applicano ad esempio non solo alle architetture monolitiche nelle app Web esistenti, ma anche alle varianti orientate ai servizi e a più livelli e ad altri stili dell'architettura. Lo stato attivo o la percentuale più elevato per uno o un altro tipo di architettura e le tecnologie correlate determinano il livello di maturità generale delle applicazioni.

Ogni livello di maturità nel processo di modernizzazione è associato alle tecnologie e agli approcci principali seguenti:

- **Pronto per l'infrastruttura cloud** (rehost o lift di base & Shift): Come primo passaggio, molte organizzazioni vogliono solo eseguire rapidamente una strategia di migrazione cloud. In questo caso, le applicazioni vengono riallocate. La riallocazione, nella maggior parte dei casi, può essere automatizzata tramite [Azure Migrate](https://aka.ms/azuremigrate), un servizio che fornisce indicazioni, informazioni e meccanismi a supporto della migrazione in Azure tramite strumenti cloud come [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) e [Servizio Migrazione del database di Azure](https://azure.microsoft.com/campaigns/database-migration/). È anche possibile configurare la riallocazione manualmente, in modo da poter apprendere alcuni dettagli dell'infrastruttura per gli asset quando si spostano le app legacy nel cloud. Ad esempio, è possibile spostare le applicazioni in macchine virtuali in Azure con una piccola modifica, probabilmente con modifiche minime alla configurazione. La rete, in questo caso, è simile a un ambiente locale, in particolare se si creano reti virtuali in Azure.

- Ottimizzato per il **cloud** (Servizi gestiti e contenitori di Windows): Questo modello sta per apportare alcune importanti ottimizzazioni di distribuzione per ottenere vantaggi significativi dal cloud, senza modificare l'architettura di base dell'applicazione. Il passaggio fondamentale consiste nell'aggiungere il supporto dei [contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) alle applicazioni .NET Framework esistenti. Questo passaggio importante (contenitori) non richiede il tocco del codice, quindi il lavoro di Lift-and-Shift complessivo è chiaro. È possibile usare strumenti come [Image2Docker](https://github.com/docker/communitytools-image2docker-win) o Visual Studio, con i relativi strumenti per [Docker](https://www.docker.com/). Visual Studio sceglie automaticamente impostazioni predefinite intelligenti per le applicazioni ASP.NET e le immagini dei contenitori di Windows. Questi strumenti offrono sia un ciclo interno rapido che un percorso veloce per l'uso dei contenitori in Azure. Ne risulta una maggiore flessibilità per la distribuzione in più ambienti. Passando quindi alla produzione, è possibile distribuire i contenitori di Windows in [app Web per contenitori di Azure](https://azure.microsoft.com/services/app-service/containers/), istanze di contenitore di [Azure (ACI)](https://azure.microsoft.com/services/container-instances/)e VM di azure con Windows Server 2016 e contenitori se si preferisce un approccio IaaS. Per applicazioni multicontenitore più complesse, provare a usare gli agenti di orchestrazione come [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/). 

Durante questa fase di modernizzazione iniziale, è anche possibile aggiungere asset dal cloud, ad esempio il monitoraggio con strumenti come [applicazione Azure Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview); Pipeline CI/CD per i cicli di vita delle app con [Azure DevOps Services](https://azure.microsoft.com/services/devops/); e molti altri servizi di risorse di dati disponibili in Azure. È ad esempio possibile modificare un'app Web monolitica originariamente distribuita in modo tradizionale con [Web Form ASP.NET](https://www.asp.net/web-forms) o [ASP.NET MVC](https://www.asp.net/mvc), distribuendola invece con i contenitori di Windows. Quando si usano i contenitori di Windows, è anche necessario eseguire la migrazione dei dati in un database nell'[Istanza gestita di database SQL di Azure](https://docs.microsoft.com/azure/sql-database/), senza dover modificare l'architettura di base dell'applicazione.

- **Nativo del cloud**: Come introdotto, è opportuno considerare l'architettura di applicazioni [native del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) quando si è destinati a applicazioni di grandi dimensioni e complesse con più team di sviluppo indipendenti che lavorano su microservizi diversi che possono essere sviluppati e distribuiti. autonomamente. Inoltre, a causa del ridimensionamento e della scalabilità indipendenti per microservizi. Questi approcci architettonici affrontano difficoltà e complessità molto importanti, ma possono essere notevolmente semplificati tramite PaaS cloud e agenti di orchestrazione come [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/) (Managed Kubernetes) e [funzioni di Azure](https://azure.microsoft.com/services/functions/) per un approccio senza server. Tutti questi approcci, come i microservizi e senza server, richiedono in genere l'architettura per il cloud e la scrittura di nuovo codice, ovvero codice adattato a piattaforme PaaS specifiche o codice allineato a architetture specifiche, ad esempio i microservizi.

La figura 1-3 illustra le tecnologie interne che è possibile usare per ogni livello di maturità:

![Tecnologie interne per ogni livello di maturità della modernizzazione](./media/image1-3.png)

> **Figura 1-3.** Tecnologie interne per ogni livello di maturità della modernizzazione

## <a name="lift-and-shift-scenario"></a>Scenario di Lift-and-Shift

Per le migrazioni con trasferimento in modalità lift-and-shift, tenere presente che è possibile scegliere tra diverse varianti per gli scenari dell'applicazione. Se si rialloca solo l'applicazione, lo scenario potrebbe essere simile a quello illustrato nella figura 1-4, dove si usano le macchine virtuali nel cloud solo per l'applicazione e per il server di database.

![Esempio di scenario IaaS puro nel cloud](./media/image1-4.png)

> **Figura 1-4**. Esempio di scenario IaaS puro nel cloud

## <a name="modernization-scenarios"></a>Scenari di modernizzazione

Per gli scenari di modernizzazione, potrebbe essere presente un'applicazione ottimizzata per il cloud che usa elementi solo da tale livello di maturità. In alternativa, è possibile che si disponga di un'applicazione a stato intermedio con alcuni elementi dell'infrastruttura cloud pronto e altri elementi da ottimizzato per il cloud (un "pick and choose" o un modello misto), come illustrato nella figura 1-5.

![Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori](./media/image1-5.png)

> **Figura 1-5.** Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori

Quindi, come scenario ideale per la migrazione di molte applicazioni .NET Framework esistenti, è possibile eseguire la migrazione a un'applicazione ottimizzata per il cloud, per ottenere vantaggi significativi da un po' di lavoro. Questo approccio consente inoltre di configurare il cloud nativo come possibile evoluzione futura. La figura 1-6 mostra un esempio.

![Scenario di esempio di app ottimizzate per il cloud, con i contenitori di Windows e i servizi gestiti](./media/image1-6.png)

> **Figura 1-6.** Scenario di esempio di app ottimizzate per il cloud, con i contenitori di Windows e i servizi gestiti

Ancora più avanti, è possibile estendere l'applicazione esistente ottimizzata per il cloud aggiungendo alcuni microservizi per scenari specifici. In questo modo si passa parzialmente al livello del modello nativo del cloud, che non è l'obiettivo principale dell'attuale materiale sussidiario.

## <a name="what-this-guide-does-not-cover"></a>Argomenti non trattati dalla guida

Questa guida descrive un sottoinsieme specifico di scenari di esempio, come illustrato nella figura 1-7. Questa guida è incentrata solo sugli scenari di Lift-and-Shift e, infine, sul modello ottimizzato per il cloud. Nel modello ottimizzato per il cloud, un'applicazione .NET Framework viene modernizzata usando i contenitori di Windows, oltre a componenti aggiuntivi come il monitoraggio e le pipeline di integrazione continua/recapito continuo. Ogni componente è fondamentale per la distribuzione delle applicazioni nel cloud in modo più rapido e con maggiore flessibilità.

![Il cloud nativo non è trattato in questa guida](./media/image1-7.png)

> **Figura 1-7.** Il cloud nativo non è trattato in questa guida

L'obiettivo di questa guida è specifico. Mostra il percorso che è possibile intraprendere per ottenere un lift-and-Shift delle applicazioni .NET esistenti, senza riprogettare e senza modifiche al codice. Infine, viene illustrato come rendere l'applicazione ottimizzata per il cloud.

Questa guida non illustra come creare applicazioni native del cloud, ad esempio come evolversi in un'architettura di microservizi. Per riprogettare le applicazioni o per creare applicazioni nuovissime basate su microservizi, vedere l'e-book [.NET microservices: Architettura per le applicazioni](https://aka.ms/microservicesebook).NET in contenitori.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft** (e-book scaricabile) \
  <https://aka.ms/dockerlifecycleebook>

- **Microservizi .NET.: Architettura per le applicazioni** .NET in contenitori (e-book scaricabile) \
  <https://aka.ms/microservicesebook>

- **Architettura di applicazioni Web moderne con ASP.NET Core e Azure** (e-book scaricabile) \
  <https://aka.ms/webappebook>

## <a name="who-should-use-this-guide"></a>Destinatari della guida

Questa guida è stata scritta per sviluppatori e architetti di soluzioni che vogliono modernizzare le applicazioni Web ASP.NET esistenti o i servizi WCF basati sulla .NET Framework, per una maggiore flessibilità nella distribuzione e nel rilascio delle applicazioni.

Questa guida è utile anche per i responsabili delle decisioni tecniche, ad esempio un progettista aziendale o un responsabile/direttore dello sviluppo che vuole semplicemente una panoramica dei vantaggi che è possibile ottenere usando i contenitori di Windows ed eseguendo la distribuzione nel cloud con Microsoft Azure.

## <a name="how-to-use-this-guide"></a>Come usare questa guida

Questa guida illustra i motivi per cui è consigliabile modernizzare le applicazioni esistenti e i vantaggi specifici offerti dall'uso di contenitori di Windows quando si spostano le app nel cloud. Il contenuto dei primi capitoli di questa guida è destinato ai progettisti e ai responsabili delle decisioni tecniche che vogliono una panoramica generale, senza informazioni dettagliate relative all'implementazione e agli aspetti tecnici.

L'ultimo capitolo di questa guida presenta diverse procedure dettagliate relative a scenari di distribuzione specifici. Questa guida offre versioni più brevi delle procedure dettagliate per riepilogare gli scenari ed evidenziare i relativi vantaggi. Le procedure dettagliate complete analizzano in dettaglio le fasi di configurazione e implementazione e sono pubblicate come set di [post wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki) nello stesso [repository GitHub](https://github.com/dotnet-architecture/eShopModernizing) pubblico in cui si trovano le app di esempio correlate (illustrate nella sezione successiva). L'ultimo capitolo e le procedure wiki dettagliate in GitHub sono di particolare interesse per gli sviluppatori e i progettisti che vogliono concentrarsi sui dettagli dell'implementazione.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>App di esempio per la modernizzazione delle app legacy: eShopModernizing

Il repository [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) in GitHub offre due applicazioni di esempio che simulano le applicazioni Web monolitiche legacy. Un'app Web viene sviluppata usando ASP.NET MVC; la seconda app Web viene sviluppata usando Web Form ASP.NET e la terza app è un'app a più livelli con un'app desktop client WinForms che usa un back-end del servizio WCF. Tutte queste app sono basate sulla .NET Framework tradizionale. Le app di esempio non usano .NET Core o ASP.NET Core in quanto devono rappresentare applicazioni .NET Framework esistenti/legacy da modernizzare.

Queste app di esempio hanno una seconda versione, con codice modernizzato, che sono piuttosto semplici. La differenza più importante tra le versioni delle app è che le seconde versioni usano i contenitori di Windows come opzione di distribuzione. Nelle seconde versioni sono state introdotte anche alcune aggiunte, ad esempio BLOB di archiviazione di Azure per la gestione delle immagini, Azure Active Directory per la gestione della sicurezza e Azure Application Insights per il monitoraggio e il controllo delle applicazioni.

## <a name="send-your-feedback"></a>Invia commenti e suggerimenti

Questa guida è stata scritta per aiutare a comprendere le opzioni per migliorare e modernizzare le applicazioni Web .NET esistenti. La guida e le applicazioni di esempio correlate sono in continua evoluzione. I commenti e suggerimenti sono benvenuti. È possibile inviare eventuali commenti su come rendere la guida ancora più utile all'indirizzo: [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
>[avanti](lift-and-shift-existing-apps-azure-iaas.md) <!-- Next Chapter -->
