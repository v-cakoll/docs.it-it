---
title: Modernizzare .NET applicazioni con Azure Cloud esistente e i contenitori di Windows (2 ° edizione)
description: In grado di accuratezza e tenere premuto MAIUSC e modernizzare le applicazioni esistenti al cloud di Azure e i contenitori con questo e-book.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 4/28/2018
ms.openlocfilehash: 3fcfdca68e05494785148cbbe149cdc2f812c577
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956383"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>Modernizzare le applicazioni .NET esistenti con cloud di Azure e i contenitori di Windows (2 ° edizione)

![Immagine di copertina](./media/cover.png)

PUBBLICATO DA  
Microsoft Press e Microsoft DevDiv  
Divisioni di Microsoft Corporation  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © Microsoft Corporation 2018  

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questa guida è disponibile gratuitamente sotto forma di un libro elettronico (e-book) disponibile tramite più canali presso Microsoft, ad esempio http://dot.net/architecture.

Per domande relative a questo libro, inviare un messaggio di posta elettronica a [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. Opinioni, visualizzazioni e informazioni espresse nel presente documento, inclusi URL e altri riferimenti a siti Web, soggette a modifiche senza preavviso.

Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi. Nessuna associazione o connessione reale è intenzionale o può essere presupposta.

Microsoft e i marchi elencati in http://www.microsoft.com nella pagina Web "Marchi" sono marchi delle società del gruppo Microsoft. Tutti gli altri marchi appartengono ai rispettivi proprietari.

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

Quando si decide di modernizzare servizi o le applicazioni web e li sposta nel cloud, non necessariamente dovranno completamente ridefinizione dell'architettura delle applicazioni. Rielaborazione di un'applicazione utilizzando un approccio avanzato, ad esempio microservizi non è sempre un'opzione a causa di restrizioni di tempo e costi. A seconda del tipo di applicazione, un'app di rielaborazione inoltre potrebbero non essere necessarie. Per ottimizzare l'efficacia della strategia di migrazione cloud dell'organizzazione dal punto di vista economico, è importante considerare le esigenze dell'azienda e i requisiti delle app. È necessario determinare:

- App che richiedono una trasformazione o rielaborazione.

- Quali app devono essere modernizzate solo parzialmente.

- Quali app è possibile trasferire in modalità lift-and-shift direttamente nel cloud.

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida è incentrata principalmente sul moderna iniziale del web di Microsoft .NET Framework esistenti o le applicazioni orientate ai servizi, vale a dire l'azione di spostamento di un carico di lavoro in un ambiente più recente o più moderno senza modificare in modo significativo il codice dell'applicazione e architettura di base. 

Questa guida illustra inoltre i vantaggi di lo spostamento delle app nel cloud e parzialmente modernizzare le app usando un set specifico di nuove tecnologie e gli approcci, ad esempio i contenitori di Windows e le piattaforme di calcolo correlate in Azure che supportano i contenitori di Windows.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Percorso di spostamento nel cloud delle applicazioni .NET esistenti

Le organizzazioni scelgono in genere di passare al cloud per ottenere flessibilità e velocità per le applicazioni. Nel cloud è possibile configurare migliaia di server (macchine virtuali) in minuti e non in settimane, che è il tempo in genere necessario per configurare i server locali.

Non c'è un'unica strategia adatta per tutti gli scenari di migrazione delle applicazioni nel cloud. La strategia di migrazione adatta dipende dalle esigenze e dalle priorità dell'organizzazione, oltre che dal tipo di applicazioni di cui si esegue la migrazione. Non tutte le applicazioni giustificano l'investimento per il passaggio a un modello di piattaforma distribuita come servizio ([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) o lo sviluppo di un modello applicativo [nativo del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). In molti casi è possibile adottare un approccio graduale o incrementale per l'investimento nello spostamento degli asset nel cloud, in base alle esigenze aziendali.

Per le applicazioni moderne con una maggiore flessibilità per migliore a lungo termine e il valore per l'organizzazione, è possibile trarre vantaggio dall'investimento in *cloud nativo* architetture di applicazioni. Tuttavia, per le applicazioni che sono esistenti o asset legacy, la chiave è investire minimo tempo e denaro (nessuna modifica codice o rielaborazione) durante lo spostamento nel cloud, per ottenere vantaggi significativi.

La figura 1-1 illustra i percorsi che è possibile seguire quando si spostano applicazioni .NET esistenti nel cloud in fasi incrementali.

 ![Percorsi di modernizzazione per servizi e applicazioni .NET esistenti](./media/image1-1.png)

> **Figura 1-1**. Percorsi di modernizzazione per servizi e applicazioni .NET esistenti

Ogni approccio alla migrazione presenta diversi vantaggi e motivi per sceglierlo. Per la migrazione di app nel cloud è possibile scegliere un approccio unico oppure scegliere determinati componenti da più approcci. Le singole applicazioni non sono limitate a un singolo approccio o stato di maturità. Ad esempio, un approccio ibrido comune prevede determinati componenti in locale e altri nel cloud.

La definizione e una breve spiegazione di ogni livello di maturità dell'applicazione sono i seguenti:

**Livello 1: Infrastruttura Cloud-Ready** applicazioni: con questo approccio di migrazione, sufficiente eseguire la migrazione o riallocare le applicazioni locali correnti per un'infrastruttura come servizio ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)) della piattaforma. Le app hanno quasi la stessa composizione di prima, ma vengono ora distribuite in macchine virtuali nel cloud.
Questo tipo semplice di migrazione è in genere noto nel settore come "Sollevare e spostare".

**Livello 2: Cloud ottimizzata** applicazioni: A questo livello e ancora senza rielaborazione o la modifica di codice significativo, è possibile ottenere vantaggi aggiuntivi di eseguire l'app nel cloud con moderne tecnologie contenitori e aggiuntivi servizi cloud gestiti. È possibile migliorare la flessibilità delle applicazioni per distribuirle più velocemente ridefinendo i processi delle operazioni di sviluppo aziendale (DevOps). Eseguire questa operazione tramite tecnologie quali i contenitori di Windows, che si basa sul motore Docker. I contenitori di rimuovere le discrepanze causata da dipendenze dell'applicazione quando si distribuisce in più fasi. In questo modello di scadenza, è possibile distribuire i contenitori in IaaS o PaaS durante l'utilizzo aggiuntive dei servizi gestiti da cloud correlati ai database, nella cache come un servizio, il monitoraggio e la distribuzione integrazione continua/continua (CI/CD) pipeline.

Il terzo livello di maturità rappresenta l'obiettivo finale nel cloud, ma è facoltativo per numerose app ed esula dall'ambito di questa guida:

**Livello 3: Cloud nativo** applicazioni: questo approccio di migrazione in genere è dovuto a esigenze aziendali e le destinazioni modernizzazione le applicazioni mission-critical. A questo livello si usano servizi PaaS per spostare le app in piattaforme di elaborazione PaaS. Si implementa un'architettura di applicazioni e microservizi [nativa del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) per consentire l'evoluzione delle applicazioni con flessibilità a lungo termine e per raggiungere nuovi livelli di scalabilità. Questo tipo di modernizzazione richiede in genere una progettazione specifica per il cloud. Spesso è necessario scrivere nuovo codice, in particolare quando si passa a modelli basati su microservizi e applicazioni nativi del cloud. Questo approccio può consentire di ottenere vantaggi che sono difficili da ottenere in un ambiente applicativo monolitico e locale.

La tabella 1-1 descrive i vantaggi principali di ogni approccio alla migrazione o alla modernizzazione e i motivi per scegliere tale approccio.

| **Pronto per l'infrastruttura cloud** <br /> *Lift-and-shift* | **Ottimizzato per il cloud** <br /> *Modernizzare* | **Cloud-nativo** <br /> *Modernizzare, ridefinizione dell'architettura e riscrivere* |
|---|---|---|
| **Destinazione di elaborazione dell'applicazione** |
| Applicazioni distribuite in macchine virtuali in Azure | Monolitico o le app a più livelli distribuite al servizio App di Azure, Azure contenitore istanza ACI (), le macchine virtuali con i contenitori, Azure Service Fabric o AKS (servizio Kubernetes di Azure) | Nei contenitori microservizi in Azure Kubernetes servizio (AKS), Service Fabric e/o senza server microservizi basate sulle funzioni di Azure. |
| **Destinazione dei dati** |
| SQL o qualsiasi database relazionale in una macchina virtuale | Istanza gestita del Database SQL Azure o un altro database gestiti nel cloud. | Database con granularità multate per microservizio, in base a Database SQL di Azure, Azure Cosmos DB o un altro database gestiti nel cloud |
| **Vantaggi**|
| <li>Nessun codice rielaborazione, non nuovo <li> Lavoro minimo per una migrazione rapida <li> Minimo comune denominatore supportato in Azure <li> Garanzie di disponibilità di base <li> Dopo lo spostamento nel cloud, è più semplice aumentare ancora di più il livello di modernizzazione | <li> Nessun rielaborazione <li> Modifiche di codice/configurazione minima <li> Distribuzione migliorata e flessibilità DevOps per il rilascio grazie ai contenitori <li> Densità maggiore e costi di distribuzione minori <li> Portabilità di app e dipendenze <li> Flessibilità di destinazioni di host: PaaS approcci o IaaS | <li> Architetto per il cloud, si ottengono vantaggi migliori dal cloud, ma è necessario nuovo codice <li> Approcci nativi del cloud basati su microservizi <li> Applicazioni moderne mission-critical, cloud resilienti hyper scalabile <li> Servizi completamente gestiti <li> Ottimizzazione per la scalabilità <li> Ottimizzazione per la flessibilità autonoma in base al sottosistema <li> Approccio basato su distribuzione e DevOps |
| **Sfide** |
| <li> Valore cloud inferiore, all'infuori del cambiamento nelle spese operative e della chiusura di data center <li> Poco gestito: nessun sistema operativo o l'applicazione di patch middleware; potrebbe utilizzare soluzioni di infrastruttura, ad esempio Terraform, Spinnaker o Puppet | <li> Containerizing è un passaggio aggiuntivo della curva di apprendimento per gli sviluppatori e gli operatori IT <li> DevOps e CI/CD pipeline è in genere 'necessaria' per questo approccio. Se non è attualmente presente nelle impostazioni cultura dell'organizzazione, potrebbe essere un'ulteriore sfida| <li> Richiede la rielaborazione per App native di cloud e alle architetture microservizio e in genere richiede codice significativo refactoring o riscrivendo quando modernizzazione (un aumento dei tempi e budget) <li> DevOps e CI/CD pipeline è in genere 'necessaria' per questo approccio. Se non è attualmente presente nelle impostazioni cultura dell'organizzazione, potrebbe essere un'ulteriore sfida|
> **Tabella 1-1.** Vantaggi e sfide dei percorsi di modernizzazione per servizi e applicazioni .NET esistenti

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Principali tecnologie e architetture in base al livello di maturità

La prima versione delle applicazioni .NET Framework è stata .NET Framework 1.0, rilasciata verso la fine del 2001. Le aziende sono quindi passate a versioni più recenti (ad esempio 2.0, 3.5 e .NET 4.x). La maggior parte delle applicazioni è stato eseguito in Windows Server e Internet Information Server (IIS) e utilizzato un database relazionale, ad esempio SQL Server, Oracle, MySQL o qualsiasi altro sistema RDBMS.

La maggior parte delle applicazioni .NET oggi si basa su .NET Framework 4. x o anche .NET Framework 3.5, e usa framework Web come ASP.NET MVC, Web Form ASP.NET, API Web ASP.NET, Windows Communication Foundation (WCF), ASP.NET SignalR e Pagine Web ASP.NET. Queste radicate tecnologie .NET Framework dipendono da Windows. Questa dipendenza è importante da considerare se si esegue semplicemente la migrazione di app legacy e si vuole apportare modifiche minime all'infrastruttura dell'applicazione.

La figura 1-2 mostra le tecnologie e gli stili di architettura principali usati per ognuno dei tre livelli di maturità cloud:

![Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti](./media/image1-2.png)

> **Figura 1-2.** Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti

La figura 1-2 evidenzia gli scenari più comuni, ma per quanto riguarda l'architettura sono possibili numerose varianti ibride e miste. I modelli di maturità si applicano ad esempio non solo alle architetture monolitiche nelle app Web esistenti, ma anche alle varianti orientate ai servizi e a più livelli e ad altri stili dell'architettura. Il superiore stato attivo o percentuale sul tipo di architettura di uno o un altro e le tecnologie correlate determina il livello di maturità complessiva delle applicazioni.

Ogni livello di maturità nel processo di modernizzazione è associato alle tecnologie e agli approcci principali seguenti:

- **Pronto per infrastruttura di cloud** (rehost o basic sollevare e spostare): come primo passaggio, molte organizzazioni devono solo eseguire rapidamente una strategia di migrazione cloud. In questo caso, le applicazioni vengono riallocate. La riallocazione, nella maggior parte dei casi, può essere automatizzata tramite [Azure Migrate](https://aka.ms/azuremigrate), un servizio che fornisce indicazioni, informazioni e meccanismi a supporto della migrazione in Azure tramite strumenti cloud come [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) e [Servizio Migrazione del database di Azure](https://azure.microsoft.com/campaigns/database-migration/). È anche possibile configurare la riallocazione manualmente, in modo da poter apprendere alcuni dettagli dell'infrastruttura per gli asset quando si spostano le app legacy nel cloud. Ad esempio, è possibile spostare le applicazioni per le macchine virtuali di Azure con poche modifiche probabilmente con solo le modifiche alla configurazione. La rete, in questo caso, è simile a un ambiente locale, in particolare se si creano reti virtuali in Azure.

- **Ottimizzato per il cloud** (servizi gestiti e i contenitori di Windows): questo modello consiste nel rendere alcune ottimizzazioni distribuzione importante per ottenere alcuni vantaggi significativi dal cloud, senza modificare l'architettura dei componenti di base dell'applicazione. Il passaggio fondamentale consiste nell'aggiungere il supporto dei [contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) alle applicazioni .NET Framework esistenti. Questo passaggio importante (la containerizzazione) non richiede alcuna modifica al codice, pertanto l'impegno di accuratezza e MAIUSC complessivo è chiaro. È possibile usare strumenti come [Image2Docker](https://github.com/docker/communitytools-image2docker-win) o Visual Studio, con i relativi strumenti per [Docker](https://www.docker.com/). Visual Studio sceglie automaticamente impostazioni predefinite intelligenti per le applicazioni ASP.NET e le immagini dei contenitori di Windows. Questi strumenti offrono sia un ciclo interno rapido che un percorso veloce per l'uso dei contenitori in Azure. Ne risulta una maggiore flessibilità per la distribuzione in più ambienti. Quindi, lo spostamento in produzione, è possibile distribuire i contenitori di Windows per [App Web di Azure per i contenitori](https://azure.microsoft.com/en-us/services/app-service/containers/), [Azure contenitore istanze ACI () e macchine virtuali di Azure con Windows Server 2016 e i contenitori se si preferisce un approccio IaaS. Per le applicazioni multi-contenitore leggermente più complesse, in orchestrators, ad esempio [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) oppure [servizio Kubernetes (AKS/ACS) di Azure](https://azure.microsoft.com/en-us/services/container-service/). Durante questa fase di modernizzazione iniziale, è anche possibile aggiungere asset dal cloud, ad esempio il monitoraggio con strumenti come [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview), pipeline di integrazione continua/distribuzione continua per i cicli di vita delle app con [Visual Studio Team Services](https://www.visualstudio.com/team-services/) e molti altri servizi per le risorse dati disponibili in Azure. È ad esempio possibile modificare un'app Web monolitica originariamente distribuita in modo tradizionale con [Web Form ASP.NET](https://www.asp.net/web-forms) o [ASP.NET MVC](https://www.asp.net/mvc), distribuendola invece con i contenitori di Windows. Quando si usano i contenitori di Windows, è anche necessario eseguire la migrazione dei dati in un database nell'[Istanza gestita di database SQL di Azure](https://docs.microsoft.com/azure/sql-database/), senza dover modificare l'architettura di base dell'applicazione.

- **Cloud-nativo**: forma introdotta, è necessario considerare architettura [cloud nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) le applicazioni quando si dispone di applicazioni di grandi e complesse con più team di sviluppo indipendente lavorando microservizi diversi che possono essere sviluppati e distribuiti in modo autonomo. Inoltre, a causa di scalabilità granularized e indipendenti per ogni microservizio. Questi approcci architetturali faccia molto importante sfide e complessità, ma possono essere notevolmente semplificati tramite cloud PaaS e come orchestrators [Azure Kubernetes servizio (AKS/ACS)](https://azure.microsoft.com/en-us/services/container-service/) (gestito Kubernetes), [servizio Azure Infrastruttura, e [funzioni Azure](https://azure.microsoft.com/services/functions/) per un approccio senza server. Tutti questi approcci (ad esempio microservizi e senza server) richiedono in genere è possibile progettare per il cloud e scrivere il nuovo codice, ovvero codice in cui è stato adattato a piattaforme PaaS specifiche o codice che viene allineato con architetture specifiche, ad esempio microservizi.

La figura 1-3 illustra le tecnologie interne che è possibile usare per ogni livello di maturità:

![Tecnologie interne per ogni livello di maturità della modernizzazione](./media/image1-3.png)

> **Figura 1-3.** Tecnologie interne per ogni livello di maturità della modernizzazione

## <a name="lift-and-shift-scenario"></a>Spostare scenario

Per le migrazioni con trasferimento in modalità lift-and-shift, tenere presente che è possibile scegliere tra diverse varianti per gli scenari dell'applicazione. Se si rialloca solo l'applicazione, lo scenario potrebbe essere simile a quello illustrato nella figura 1-4, dove si usano le macchine virtuali nel cloud solo per l'applicazione e per il server di database.

![Esempio di scenario IaaS puro nel cloud](./media/image1-4.png)

> **Figura 1-4**. Esempio di scenario IaaS puro nel cloud

## <a name="modernization-scenarios"></a>Scenari di modernizzazione

Per gli scenari modernizzazione, potrebbe essere necessario un'applicazione pura ottimizzato su Cloud che utilizza gli elementi solo da tale livello di maturità. Oppure, è possibile un'applicazione stato intermedio con alcuni elementi dell'infrastruttura di Cloud computing e altri elementi da ottimizzato su Cloud (un "scegliere" o un modello misto), come nella figura 1 a 5.

![Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori](./media/image1-5.png)

> **Figura 1-5.** Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori

Successivamente, come lo scenario ideale per molte applicazioni .NET Framework esistente eseguire la migrazione, è possibile eseguire la migrazione a un'applicazione ottimizzato su Cloud, per ottenere notevoli vantaggi da impegno minimo. Questo approccio imposta inoltre per codice nativo Cloud come una possibile evoluzione future. La figura 1-6 mostra un esempio.

![Scenario di ottimizzato su Cloud app di esempio, con i contenitori di Windows e dei servizi gestiti](./media/image1-6.png)

> **Figura 1-6.** Scenario di ottimizzato su Cloud app di esempio, con i contenitori di Windows e dei servizi gestiti

Continua anche, è possibile estendere l'applicazione esistente ottimizzato su Cloud mediante l'aggiunta di alcune microservizi per scenari specifici. Ciò sposterebbe è parzialmente al livello del modello di Cloud nativo che non è l'obiettivo principale della presenta Guida.


## <a name="what-this-guide-does-not-cover"></a>Argomenti non trattati dalla guida

Questa guida descrive un sottoinsieme specifico di scenari di esempio, come illustrato nella figura 1-7. Questa guida è incentrato solo sugli scenari di accuratezza e MAIUSC e infine sul modello ottimizzato su Cloud. Nel modello ottimizzato su Cloud, un'applicazione .NET Framework è modernizzata usando i contenitori di Windows, nonché i componenti aggiuntivi, ad esempio il monitoraggio e CI/CD pipeline. Ogni componente è fondamentale per la distribuzione delle applicazioni nel cloud in modo più rapido e con maggiore flessibilità.

![Cloud nativo non viene descritta in questa Guida](./media/image1-7.png)

> **Figura 1-7.** Cloud nativo non viene descritta in questa Guida

L'obiettivo di questa guida è specifico. Mostra il percorso che è possibile intraprendere per ottenere un'accuratezza e spostamento di applicazioni .NET esistenti, senza rielaborazione e senza apportare modifiche al codice. Infine, viene illustrato come rendere l'applicazione ottimizzato su Cloud.

Questa Guida non mostra come creare applicazioni Cloud nativo, ad esempio imparando a evolvere a un'architettura di microservizi. Per ridefinizione dell'architettura delle applicazioni o per creare applicazioni completamente nuova, che si basano microservizi, vedere l'e-book [Microservizi .NET: architettura per le applicazioni .NET nei contenitori](https://aka.ms/microservicesebook).

### <a name="additional-resources"></a>Risorse aggiuntive

- **Contenitore Docker del ciclo di vita dell'applicazione con strumenti e piattaforma Microsoft** (scaricabili e-book): [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

- **Microservizi .NET: Architettura per le applicazioni .NET nei contenitori** (scaricabili e-book): [*https://aka.ms/microservicesebook*](https://aka.ms/microservicesebook)

- **Architettura di moderne applicazioni web con ASP.NET Core e Azure** (scaricabili e-book): [*https://aka.ms/webappebook*](https://aka.ms/webappebook)

## <a name="who-should-use-this-guide"></a>Destinatari della guida

Questa guida è stata scritta per gli sviluppatori e architetti di soluzioni che desiderano modernizzare le applicazioni web ASP.NET esistenti o i servizi WCF basati su .NET Framework, per una migliore agilità di spedizione e il rilascio di applicazioni.

Questa guida è utile anche per i responsabili delle decisioni tecniche, ad esempio un progettista aziendale o un responsabile/direttore dello sviluppo che vuole semplicemente una panoramica dei vantaggi che è possibile ottenere usando i contenitori di Windows ed eseguendo la distribuzione nel cloud con Microsoft Azure.

## <a name="how-to-use-this-guide"></a>Come usare questa guida

Questa guida illustra i motivi per cui è consigliabile modernizzare le applicazioni esistenti e i vantaggi specifici offerti dall'uso di contenitori di Windows quando si spostano le app nel cloud. Il contenuto dei primi capitoli di questa guida è destinato ai progettisti e ai responsabili delle decisioni tecniche che vogliono una panoramica generale, senza informazioni dettagliate relative all'implementazione e agli aspetti tecnici.

L'ultimo capitolo di questa guida presenta diverse procedure dettagliate relative a scenari di distribuzione specifici. Questa guida fornisce le procedure dettagliate, le versioni più breve per riepilogare gli scenari ed evidenziare i vantaggi in termini. Le procedure dettagliate complete analizzano in dettaglio le fasi di configurazione e implementazione e sono pubblicate come set di [post wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki) nello stesso [repository GitHub](https://github.com/dotnet-architecture/eShopModernizing) pubblico in cui si trovano le app di esempio correlate (illustrate nella sezione successiva). L'ultimo capitolo e le procedure wiki dettagliate in GitHub sono di particolare interesse per gli sviluppatori e i progettisti che vogliono concentrarsi sui dettagli dell'implementazione.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>App di esempio per la modernizzazione delle app legacy: eShopModernizing

Il repository [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) in GitHub offre due applicazioni di esempio che simulano le applicazioni Web monolitiche legacy. Viene sviluppata un'app web utilizzando ASP.NET MVC; l'app web secondo viene sviluppato da mediante Web Forms ASP.NET e il terzo app è un'applicazione a più livelli con un'applicazione desktop di client Windows Form utilizzano un servizio WCF back-end. Tutte queste App sono basate su .NET Framework tradizionale. Le app di esempio non usano .NET Core o ASP.NET Core in quanto devono rappresentare applicazioni .NET Framework esistenti/legacy da modernizzare.

Queste app di esempio dispongono di una versione secondo, con moderno e codice, e che sono piuttosto semplici. La differenza più importante tra le versioni delle app è che le seconde versioni usano i contenitori di Windows come opzione di distribuzione. Nelle seconde versioni sono state introdotte anche alcune aggiunte, ad esempio BLOB di archiviazione di Azure per la gestione delle immagini, Azure Active Directory per la gestione della sicurezza e Azure Application Insights per il monitoraggio e il controllo delle applicazioni.

## <a name="send-your-feedback"></a>Inviare commenti e suggerimenti

Questa guida è stata scritta per comprendere le opzioni per migliorare e modernizzare le applicazioni web .NET esistenti. La guida e le applicazioni di esempio correlate sono in continua evoluzione. Commenti e suggerimenti sono benvenuto! È possibile inviare eventuali commenti su come rendere la guida ancora più utile all'indirizzo: [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
[avanti](lift-and-shift-existing-apps-azure-iaas.md)
