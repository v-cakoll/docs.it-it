---
title: Modernizza .NET le applicazioni con Azure Cloud esistente e i contenitori di Windows (2nd edition)
description: Scopri come lift and -shift e modernizzare le applicazioni esistenti per il cloud di Azure e contenitori con questo e-book.
ms.date: 04/28/2018
ms.openlocfilehash: 4e632fcfbb8904a9def3fdad992286055c5df4f0
ms.sourcegitcommit: 6472349821dbe202d01182bc2cfe9d7176eaaa6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2019
ms.locfileid: "67870591"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>Modernizzare le applicazioni .NET esistenti con cloud di Azure e i contenitori di Windows (2nd edition)

![Immagine copertina della Guida .NET modernizzare le applicazioni.](./media/index/web-application-guide-cover-image.png)

PUBBLICATO DA  
Microsoft Press e Microsoft DevDiv  
Divisioni di Microsoft Corporation  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2018 Microsoft Corporation  

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro è disponibile gratuitamente sotto forma di libro elettronico (e-book) attraverso diversi canali Microsoft, ad esempio <https://dot.net/architecture>.

Per domande relative a questo libro, inviare un messaggio di posta elettronica a [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. Le viste, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web Internet, può cambiare senza preavviso.

Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi. Nessuna associazione o connessione reale è intenzionale o può essere presupposta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft. Tutti gli altri marchi appartengono ai rispettivi proprietari.

Autore:
> **Cesar de la Torre**, Senior PM, .NET Product Team, Microsoft Corp.

Collaboratori e revisori:
> **Scott Hunter**, Partner Director PM, team di .NET, Microsoft  
> **Paul Yuknewicz**, Principal PM Manager, team di Visual Studio Tools, Microsoft  
> **Lisa Guthrie**, Senior PM, team di Visual Studio Tools, Microsoft  
> **Ankit Asthana**, Principal PM Manager, team di .NET, Microsoft  
> **Unai Zorrilla**, sviluppatore capo, Plain Concepts  
> **Javier Valero**, Chief Operating Officer di Grupo Solutio  

## <a name="introduction"></a>Introduzione

Quando si decide di modernizzare le applicazioni web o i servizi e spostarli nel cloud, non necessariamente completamente ridefinizione dell'architettura delle app. Se riprogetti un'applicazione usando un approccio avanzato come quello dei microservizi non è sempre un'opzione a causa di limitazioni di tempo e costi. A seconda del tipo di applicazione, un'app di rielaborazione anche potrebbe non essere necessaria. Per ottimizzare l'efficacia della strategia di migrazione cloud dell'organizzazione dal punto di vista economico, è importante considerare le esigenze dell'azienda e i requisiti delle app. È necessario determinare:

- Quali App richiedono una trasformazione o rielaborazione.

- Quali app devono essere modernizzate solo parzialmente.

- Quali app è possibile trasferire in modalità lift-and-shift direttamente nel cloud.

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida è incentrata principalmente in modernizzazione iniziale delle web di Microsoft .NET Framework esistenti o le applicazioni orientate ai servizi, vale a dire l'azione di spostamento di un carico di lavoro in un ambiente più recente o più moderno senza alterare in modo significativo il codice dell'applicazione e architettura di base. 

Questa guida illustra anche i vantaggi di spostamento delle App cloud e modernizzazione parziale delle App usando un set specifico di nuovi approcci e tecnologie, quali i contenitori Windows e piattaforme di calcolo correlate in Azure che supportano i contenitori di Windows.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Percorso di spostamento nel cloud delle applicazioni .NET esistenti

Le organizzazioni scelgono in genere di passare al cloud per ottenere flessibilità e velocità per le applicazioni. Nel cloud è possibile configurare migliaia di server (macchine virtuali) in minuti e non in settimane, che è il tempo in genere necessario per configurare i server locali.

Non c'è un'unica strategia adatta per tutti gli scenari di migrazione delle applicazioni nel cloud. La strategia di migrazione adatta dipende dalle esigenze e dalle priorità dell'organizzazione, oltre che dal tipo di applicazioni di cui si esegue la migrazione. Non tutte le applicazioni giustificano l'investimento per il passaggio a un modello di piattaforma distribuita come servizio ([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) o lo sviluppo di un modello applicativo [nativo del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). In molti casi è possibile adottare un approccio graduale o incrementale per l'investimento nello spostamento degli asset nel cloud, in base alle esigenze aziendali.

Per le applicazioni moderne con flessibilità a lungo termine migliore e il valore per l'organizzazione, è possibile trarre vantaggio dall'investimento in *nativa del cloud* architetture di applicazioni. Tuttavia, per le applicazioni esistenti o dagli asset legacy, la chiave è di dedicare tempo e denaro (nessuna modifica codice o rielaborazione) durante lo spostamento nel cloud, per ottenere vantaggi significativi.

La figura 1-1 illustra i percorsi che è possibile seguire quando si spostano applicazioni .NET esistenti nel cloud in fasi incrementali.

 ![Percorsi di modernizzazione per servizi e applicazioni .NET esistenti](./media/image1-1.png)

> **Figura 1-1**. Percorsi di modernizzazione per servizi e applicazioni .NET esistenti

Ogni approccio alla migrazione presenta diversi vantaggi e motivi per sceglierlo. Per la migrazione di app nel cloud è possibile scegliere un approccio unico oppure scegliere determinati componenti da più approcci. Le singole applicazioni non sono limitate a un singolo approccio o stato di maturità. Ad esempio, un approccio ibrido comune prevede determinati componenti in locale e altri nel cloud.

La definizione e una breve spiegazione di ogni livello di maturità dell'applicazione sono i seguenti:

**Livello 1: Pronto per l'infrastruttura cloud** applicazioni: Questo approccio di migrazione, semplicemente la migrazione o riallocare le applicazioni locali correnti per un'infrastruttura distribuita come servizio ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)) della piattaforma. Le app hanno quasi la stessa composizione di prima, ma vengono ora distribuite in macchine virtuali nel cloud.
Questo tipo semplice di migrazione è in genere noto nel settore come "Lift- and -Shift."

**Livello 2: Cloud ottimizzato** applicazioni: A questo livello e ancora senza riarchitettare o modifica significativa al codice, è possibile ottenere ulteriori vantaggi dall'esecuzione dell'app nel cloud con le tecnologie moderne, ad esempio i contenitori e servizi cloud gestiti aggiuntivi. È possibile migliorare la flessibilità delle applicazioni per distribuirle più velocemente ridefinendo i processi delle operazioni di sviluppo aziendale (DevOps). Ottenere questo risultato mediante tecnologie quali i contenitori di Windows, che si basa sul motore Docker. I contenitori rimuovono i conflitti causati dalle dipendenze dell'applicazione quando si distribuisce in più fasi. In questo modello di maturità, è possibile distribuire i contenitori nell'ambiente IaaS o PaaS durante l'utilizzo aggiuntive servizi cloud gestiti correlate ai database, memorizzare nella cache come un servizio, il monitoraggio e distribuzione/integrazione continua (CI/CD) pipeline.

Il terzo livello di maturità rappresenta l'obiettivo finale nel cloud, ma è facoltativo per numerose app ed esula dall'ambito di questa guida:

**Livello 3: Native del cloud** applicazioni: Questo approccio alla migrazione è in genere determinato da esigenze aziendali e mira a modernizzare le applicazioni mission-critical. A questo livello si usano servizi PaaS per spostare le app in piattaforme di elaborazione PaaS. Si implementa un'architettura di applicazioni e microservizi [nativa del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) per consentire l'evoluzione delle applicazioni con flessibilità a lungo termine e per raggiungere nuovi livelli di scalabilità. Questo tipo di modernizzazione richiede in genere una progettazione specifica per il cloud. Spesso è necessario scrivere nuovo codice, in particolare quando si passa a modelli basati su microservizi e applicazioni nativi del cloud. Questo approccio può consentire di ottenere vantaggi che sono difficili da ottenere in un ambiente applicativo monolitico e locale.

La tabella 1-1 descrive i vantaggi principali di ogni approccio alla migrazione o alla modernizzazione e i motivi per scegliere tale approccio.

| **Pronto per l'infrastruttura cloud** <br /> *Lift-and-shift* | **Ottimizzato per il cloud** <br /> *Modernize* | **Cloud-Native** <br /> *Modernizza la ridefinizione dell'architettura e riscrivere* |
|---|---|---|
| **Destinazione di elaborazione dell'applicazione** |
| Applicazioni distribuite in macchine virtuali in Azure | App monolitico o a più livelli distribuite in servizio App di Azure, istanza di contenitore di Azure (ACI), le macchine virtuali con i contenitori o servizio contenitore di AZURE (Azure Kubernetes Service) | Microservizi in contenitori in Azure Kubernetes Service (AKS) e/o microservizi senza server basati sulle funzioni di Azure. |
| **Destinazione dei dati** |
| SQL o qualsiasi database relazionale in una macchina virtuale | Istanza gestita del Database SQL Azure o un altro database gestito nel cloud. | Database multate-livello di dettaglio per ogni microservizio, basati su Database SQL di Azure, Azure Cosmos DB o un altro database gestito nel cloud |
| **Vantaggi**|
| <li>Nessun codice rielaborazione, non nuovo <li> Lavoro minimo per una migrazione rapida <li> Minimo comune denominatore supportato in Azure <li> Garanzie di disponibilità di base <li> Dopo lo spostamento nel cloud, è più semplice aumentare ancora di più il livello di modernizzazione | <li> Nessun rielaborazione <li> Modifiche di codice/configurazione minima <li> Distribuzione migliorata e flessibilità DevOps per il rilascio grazie ai contenitori <li> Densità maggiore e costi di distribuzione minori <li> Portabilità di app e dipendenze <li> Flessibilità delle destinazioni host: Gli approcci di PaaS o IaaS | <li> Architetto per il cloud, si ottengono i vantaggi migliori dal cloud, ma è necessario codice nuovo <li> Approcci nativi del cloud basati su microservizi <li> Le applicazioni cruciali moderne, resilienti per il cloud altamente scalabile <li> Servizi completamente gestiti <li> Ottimizzazione per la scalabilità <li> Ottimizzazione per la flessibilità autonoma in base al sottosistema <li> Approccio basato su distribuzione e DevOps |
| **Sfide** |
| <li> Valore cloud inferiore, all'infuori del cambiamento nelle spese operative e della chiusura di data center <li> Poco viene gestito: Nessun sistema operativo o middleware l'applicazione di patch; potrebbe usare soluzioni di infrastruttura, come Terraform, Spinnaker o Puppet | <li> Uso di contenitori è un passaggio aggiuntivo della curva di apprendimento per gli sviluppatori e gli operatori IT <li> Pipeline di integrazione continua/recapito Continuo e DevOps sono in genere 'necessaria' per questo approccio. Se non attualmente presente nelle impostazioni cultura dell'organizzazione, potrebbe essere un'ulteriore sfida| <li> Richiede la rielaborazione per applicazioni native basate su cloud e le architetture di microservizi e in genere richiede codice significativo di refactoring o riscrittura la modernizzazione (tempo e budget maggiori)|
> **Tabella 1-1.** Vantaggi e sfide dei percorsi di modernizzazione per servizi e applicazioni .NET esistenti

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Principali tecnologie e architetture in base al livello di maturità

La prima versione delle applicazioni .NET Framework è stata .NET Framework 1.0, rilasciata verso la fine del 2001. Le aziende sono quindi passate a versioni più recenti (ad esempio 2.0, 3.5 e .NET 4.x). La maggior parte di queste applicazioni è stato eseguito in Windows Server e Internet Information Server (IIS) e usava un database relazionale, ad esempio SQL Server, Oracle, MySQL o qualsiasi altro sistema RDBMS.

La maggior parte delle applicazioni .NET oggi si basa su .NET Framework 4. x o anche .NET Framework 3.5, e usa framework Web come ASP.NET MVC, Web Form ASP.NET, API Web ASP.NET, Windows Communication Foundation (WCF), ASP.NET SignalR e Pagine Web ASP.NET. Queste radicate tecnologie .NET Framework dipendono da Windows. Questa dipendenza è importante da considerare se si esegue semplicemente la migrazione di app legacy e si vuole apportare modifiche minime all'infrastruttura dell'applicazione.

La figura 1-2 mostra le tecnologie e gli stili di architettura principali usati per ognuno dei tre livelli di maturità cloud:

![Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti](./media/image1-2.png)

> **Figura 1-2.** Tecnologie principali per ogni livello di maturità per la modernizzazione delle applicazioni Web .NET esistenti

La figura 1-2 evidenzia gli scenari più comuni, ma per quanto riguarda l'architettura sono possibili numerose varianti ibride e miste. I modelli di maturità si applicano ad esempio non solo alle architetture monolitiche nelle app Web esistenti, ma anche alle varianti orientate ai servizi e a più livelli e ad altri stili dell'architettura. La messa a fuoco o percentuale sul tipo di architettura di uno o un altro e le tecnologie correlate superiore determina il livello di maturità complessivo delle applicazioni.

Ogni livello di maturità nel processo di modernizzazione è associato alle tecnologie e agli approcci principali seguenti:

- **Pronto per l'infrastruttura cloud** (riallocazione o basic lift- and -shift): Come primo passaggio, molte organizzazioni vogliono semplicemente attuare rapidamente una strategia di migrazione nel cloud. In questo caso, le applicazioni vengono riallocate. La riallocazione, nella maggior parte dei casi, può essere automatizzata tramite [Azure Migrate](https://aka.ms/azuremigrate), un servizio che fornisce indicazioni, informazioni e meccanismi a supporto della migrazione in Azure tramite strumenti cloud come [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) e [Servizio Migrazione del database di Azure](https://azure.microsoft.com/campaigns/database-migration/). È anche possibile configurare la riallocazione manualmente, in modo da poter apprendere alcuni dettagli dell'infrastruttura per gli asset quando si spostano le app legacy nel cloud. Ad esempio, è possibile spostare le applicazioni per le macchine virtuali in Azure con poche modifiche, probabilmente apportando solo modifiche minime alla configurazione. La rete, in questo caso, è simile a un ambiente locale, in particolare se si creano reti virtuali in Azure.

- **Ottimizzato per il cloud** (codice gestito di servizi e contenitori Windows): Questo modello è incentrato sul rendere alcuni importanti ottimizzazioni della distribuzione per ottenere alcuni vantaggi significativi dal cloud, senza modificare l'architettura di base dell'applicazione. Il passaggio fondamentale consiste nell'aggiungere il supporto dei [contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) alle applicazioni .NET Framework esistenti. Questo passaggio importante (contenitori) non è necessario modificare il codice, in modo che la modalità lift- and -shift uno sforzo complessivo è ridotto. È possibile usare strumenti come [Image2Docker](https://github.com/docker/communitytools-image2docker-win) o Visual Studio, con i relativi strumenti per [Docker](https://www.docker.com/). Visual Studio sceglie automaticamente impostazioni predefinite intelligenti per le applicazioni ASP.NET e le immagini dei contenitori di Windows. Questi strumenti offrono sia un ciclo interno rapido che un percorso veloce per l'uso dei contenitori in Azure. Ne risulta una maggiore flessibilità per la distribuzione in più ambienti. Quindi, passare alla produzione, è possibile distribuire i contenitori di Windows per [App Web di Azure per contenitori](https://azure.microsoft.com/services/app-service/containers/), [istanze di contenitore di Azure (ACI)](https://azure.microsoft.com/services/container-instances/), macchine virtuali di Azure con Windows Server 2016 e i contenitori se si preferisce e un approccio IaaS. Per le applicazioni multi-contenitore più complesse, è consigliabile usare gli agenti di orchestrazione, ad esempio [Azure Kubernetes Service (servizio contenitore di AZURE/ACS)](https://azure.microsoft.com/services/container-service/). 

Durante questa fase di modernizzazione iniziale, è anche possibile aggiungere asset dal cloud, ad esempio il monitoraggio con strumenti quali [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview); Per i cicli di vita delle app con le pipeline di integrazione continua/recapito Continuo [servizi di Azure DevOps](https://azure.microsoft.com/services/devops/); e molti altri risorsa servizi dati che sono disponibili in Azure. È ad esempio possibile modificare un'app Web monolitica originariamente distribuita in modo tradizionale con [Web Form ASP.NET](https://www.asp.net/web-forms) o [ASP.NET MVC](https://www.asp.net/mvc), distribuendola invece con i contenitori di Windows. Quando si usano i contenitori di Windows, è anche necessario eseguire la migrazione dei dati in un database nell'[Istanza gestita di database SQL di Azure](https://docs.microsoft.com/azure/sql-database/), senza dover modificare l'architettura di base dell'applicazione.

- **Native del cloud**: Come descritto, è necessario considerare architettura [nativa del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) applicazioni quando si intende usare applicazioni grandi e complesse con più team di sviluppo indipendente lavora su diversi microservizi che possono essere sviluppato e distribuito in modo autonomo. Inoltre, a causa di scalabilità granularized e indipendenti per ogni microservizio. Questi approcci architetturali si trovano molto importante sfide e complessità, ma possono essere notevolmente semplificati tramite cloud PaaS e gli agenti di orchestrazione, ad esempio [Azure Kubernetes Service (servizio contenitore di AZURE/ACS)](https://azure.microsoft.com/services/container-service/) (managed Kubernetes) e [Funzioni di azure](https://azure.microsoft.com/services/functions/) per un approccio senza server. Tutti questi approcci (ad esempio i microservizi e un'infrastruttura senza server) richiedono in genere per il cloud per progettare e scrivere nuovo codice, ovvero codice che è stato adattato per piattaforme PaaS specifiche o allineato ad architetture specifiche, ad esempio i microservizi.

La figura 1-3 illustra le tecnologie interne che è possibile usare per ogni livello di maturità:

![Tecnologie interne per ogni livello di maturità della modernizzazione](./media/image1-3.png)

> **Figura 1-3.** Tecnologie interne per ogni livello di maturità della modernizzazione

## <a name="lift-and-shift-scenario"></a>Scenario lift- and -shift

Per le migrazioni con trasferimento in modalità lift-and-shift, tenere presente che è possibile scegliere tra diverse varianti per gli scenari dell'applicazione. Se si rialloca solo l'applicazione, lo scenario potrebbe essere simile a quello illustrato nella figura 1-4, dove si usano le macchine virtuali nel cloud solo per l'applicazione e per il server di database.

![Esempio di scenario IaaS puro nel cloud](./media/image1-4.png)

> **Figura 1-4**. Esempio di scenario IaaS puro nel cloud

## <a name="modernization-scenarios"></a>Scenari di modernizzazione

Per gli scenari di modernizzazione, potrebbe essere un'applicazione ottimizzato per il Cloud pura che usa elementi solo di quel livello di maturità. Oppure, potrebbe essere un'applicazione di uno stato intermedio con alcuni elementi di pronto per l'infrastruttura Cloud e altri elementi da ottimizzato per il Cloud (un "scegliere" modello misto o), come nella figura 1-5.

![Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori](./media/image1-5.png)

> **Figura 1-5.** Esempio di scenario con possibilità di scelta, con database in asset IaaS, DevOps e contenitori

Successivamente, come lo scenario ideale per molte applicazioni .NET Framework esistente eseguire la migrazione, è possibile eseguire la migrazione a un'applicazione ottimizzato per il Cloud, per ottenere vantaggi significativi da poco lavoro. Questo approccio anche la strada Native del Cloud come una possibile evoluzione futura. La figura 1-6 mostra un esempio.

![Scenario ottimizzato per il Cloud delle app di esempio con i contenitori Windows e i servizi gestiti](./media/image1-6.png)

> **Figura 1-6.** Scenario ottimizzato per il Cloud delle app di esempio con i contenitori Windows e i servizi gestiti

Procedendo ulteriormente, è possibile estendere l'applicazione ottimizzato per il Cloud esistente aggiungendo alcuni microservizi per scenari specifici. In questo modo si passerebbe parzialmente al livello del modello e Native del Cloud, che esula dall'ambito della presente Guida principale.

## <a name="what-this-guide-does-not-cover"></a>Argomenti non trattati dalla guida

Questa guida descrive un sottoinsieme specifico di scenari di esempio, come illustrato nella figura 1-7. Questa guida è incentrata solo su scenari lift- and -shift e in definitiva, sul modello ottimizzato per il Cloud. Nel modello ottimizzato per il Cloud, un'applicazione .NET Framework viene modernizzata usando i contenitori Windows e componenti aggiuntivi, ad esempio monitoraggio e la pipeline di integrazione continua/recapito Continuo. Ogni componente è fondamentale per la distribuzione delle applicazioni nel cloud in modo più rapido e con maggiore flessibilità.

![Native del cloud non è illustrata in questa Guida](./media/image1-7.png)

> **Figura 1-7.** Native del cloud non è illustrata in questa Guida

L'obiettivo di questa guida è specifico. Viene illustrato il percorso da che seguire per ottenere una modalità lift- and -shift le applicazioni .NET esistenti, senza riarchitettare e senza modifiche al codice. In definitiva, illustra come rendere l'applicazione ottimizzato per il Cloud.

Questa Guida non illustra come creare applicazioni Native del Cloud, come l'evoluzione di un'architettura di microservizi. Ridefinizione dell'architettura delle applicazioni o per creare applicazioni completamente nuove basate su microservizi, vedere l'e-book [Microservizi .NET: Architettura per applicazioni .NET in contenitori](https://aka.ms/microservicesebook).

### <a name="additional-resources"></a>Risorse aggiuntive

- **In contenitori Docker application Lifecycle Management con piattaforma e strumenti Microsoft** (e-book scaricabile) \
  <https://aka.ms/dockerlifecycleebook>

- **Microservizi .NET.: Architettura per applicazioni .NET in contenitori** (e-book scaricabile) \
  <https://aka.ms/microservicesebook>

- **Architettura delle applicazioni web moderne con ASP.NET Core e Azure** (e-book scaricabile) \
  <https://aka.ms/webappebook>

## <a name="who-should-use-this-guide"></a>Destinatari della guida

Questa guida è stata scritta per gli sviluppatori e architetti di soluzioni che vogliono modernizzare le applicazioni web ASP.NET esistenti o i servizi WCF che si basano su .NET Framework, per ottenere una migliore flessibilità nella distribuzione e nel rilascio delle applicazioni.

Questa guida è utile anche per i responsabili delle decisioni tecniche, ad esempio un progettista aziendale o un responsabile/direttore dello sviluppo che vuole semplicemente una panoramica dei vantaggi che è possibile ottenere usando i contenitori di Windows ed eseguendo la distribuzione nel cloud con Microsoft Azure.

## <a name="how-to-use-this-guide"></a>Come usare questa guida

Questa guida illustra i motivi per cui è consigliabile modernizzare le applicazioni esistenti e i vantaggi specifici offerti dall'uso di contenitori di Windows quando si spostano le app nel cloud. Il contenuto dei primi capitoli di questa guida è destinato ai progettisti e ai responsabili delle decisioni tecniche che vogliono una panoramica generale, senza informazioni dettagliate relative all'implementazione e agli aspetti tecnici.

L'ultimo capitolo di questa guida presenta diverse procedure dettagliate relative a scenari di distribuzione specifici. Questa guida fornisce le versioni abbreviate delle procedure dettagliate, per riepilogare gli scenari ed evidenziarne i vantaggi. Le procedure dettagliate complete analizzano in dettaglio le fasi di configurazione e implementazione e sono pubblicate come set di [post wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki) nello stesso [repository GitHub](https://github.com/dotnet-architecture/eShopModernizing) pubblico in cui si trovano le app di esempio correlate (illustrate nella sezione successiva). L'ultimo capitolo e le procedure wiki dettagliate in GitHub sono di particolare interesse per gli sviluppatori e i progettisti che vogliono concentrarsi sui dettagli dell'implementazione.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>App di esempio per la modernizzazione delle app legacy: eShopModernizing

Il repository [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) in GitHub offre due applicazioni di esempio che simulano le applicazioni Web monolitiche legacy. Viene sviluppata un'app web con ASP.NET MVC; la seconda app web è sviluppata con Web Form ASP.NET e il terzo app è un'app a più livelli con un'app desktop client Windows Form utilizzo di un servizio WCF back-end. Tutte queste App si basano su .NET Framework tradizionale. Le app di esempio non usano .NET Core o ASP.NET Core in quanto devono rappresentare applicazioni .NET Framework esistenti/legacy da modernizzare.

Le app di esempio hanno una seconda versione, con codice modernizzato, e sono piuttosto semplici. La differenza più importante tra le versioni delle app è che le seconde versioni usano i contenitori di Windows come opzione di distribuzione. Nelle seconde versioni sono state introdotte anche alcune aggiunte, ad esempio BLOB di archiviazione di Azure per la gestione delle immagini, Azure Active Directory per la gestione della sicurezza e Azure Application Insights per il monitoraggio e il controllo delle applicazioni.

## <a name="send-your-feedback"></a>Invia commenti e suggerimenti

Questa guida è stata scritta per aiutare a comprendere le opzioni per migliorare e modernizzare le applicazioni web .NET esistenti. La guida e le applicazioni di esempio correlate sono in continua evoluzione. I tuoi commenti sono molto apprezzati! È possibile inviare eventuali commenti su come rendere la guida ancora più utile all'indirizzo: [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
>[avanti](lift-and-shift-existing-apps-azure-iaas.md)
