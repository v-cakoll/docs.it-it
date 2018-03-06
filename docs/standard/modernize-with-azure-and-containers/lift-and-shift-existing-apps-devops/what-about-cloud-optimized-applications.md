---
title: Per quanto riguarda le applicazioni ottimizzato su cloud?
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Per quanto riguarda le applicazioni ottimizzato su Cloud?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: adcb9d2352022cc94238296562b3eb7677bdf20b
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2018
---
# <a name="what-about-cloud-optimized-applications"></a>Per quanto riguarda le applicazioni ottimizzato su cloud?

Anche se è ottimizzato per il Cloud e [cloud nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) applicazioni non sono l'obiettivo principale di questa Guida, è utile per comprendere di questo livello di maturità modernizzazione e per distinguerlo da DevOps pronta.

Figura 4-3 posiziona App ottimizzato su Cloud nei livelli di maturità modernizzazione applicazione:

![Posizionamento applicazioni ottimizzato su Cloud](./media/image3.png)

> **Figura 4-3.** Posizionamento applicazioni ottimizzato su Cloud

Il livello di maturità modernizzazione ottimizzato su Cloud richiede in genere nuovi investimenti di sviluppo. Lo spostamento al livello ottimizzato su Cloud in genere è determinato da esigenze aziendali per modernizzare le applicazioni il più possibile per ridurre i costi e aumentare la flessibilità e la concorrenza vantaggio. Questi obiettivi, vengono eseguiti da ottimizzare l'utilizzo di cloud PaaS. Ciò significa non solo mediante i servizi PaaS come DBaaS CaaS e archiviazione come servizio (STaaS), ma anche eseguendo la migrazione di applicazioni e servizi personalizzati in un PaaS calcolo piattaforma come servizio App di Azure o orchestrators.

Questo tipo di modernizzazione richiede in genere il refactoring o la scrittura di codice che è ottimizzato per il cloud PaaS piattaforme (come per il servizio App di Azure). Potrebbe essere anche necessario progettare specificamente per l'ambiente cloud, soprattutto se si passa a modelli di applicazione cloud nativo che si basano microservizi. Si tratta di una chiave rispetto al Cloud DevOps pronto, che non richiede alcuna riprogettazione e nessun codice nuovo fattore di differenziazione.

In alcuni casi più avanzati, è possibile creare [cloud nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) applicazioni basate su architetture microservizi, che possono evolvere con flessibilità e scalabilità entro i limiti che sarebbe difficile da eseguire in un'architettura monolitica distribuire un ambiente locale.

Figura 4-4 mostra il tipo di applicazioni che è possibile distribuire quando si utilizza il modello ottimizzato per il Cloud. Si dispone di due applicazioni web moderni scelte di base e le applicazioni cloud nativo.

> ![Tipi di App a livello di ottimizzato su Cloud](./media/image4.png)
>
> **Figura 4-4.** Tipi di App a livello di ottimizzato su Cloud

È possibile estendere le app di base web moderno e cloud nativo mediante l'aggiunta di altri servizi, ad esempio intelligenza artificiale (AI), l'apprendimento (ML) e IoT. È possibile utilizzare uno di questi servizi per estendere uno degli approcci possibili ottimizzato su Cloud.

La differenza fondamentale nelle applicazioni a livello di ottimizzazione Cloud consiste nell'architettura dell'applicazione. [Cloud nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) applicazioni sono per definizione, le applicazioni basate su microservizi. App cloud nativo richiedono speciali architetture, tecnologie e piattaforme, rispetto a un'applicazione web monolitico o a più livelli tradizionale.

Creazione di nuove applicazioni che non usano microservizi anche senso. Esistono molti scenari di nuovo e moderni ancora in cui un approccio basato su microservizi potrebbe superare le proprie esigenze. In alcuni casi, è consigliabile solo creare un'applicazione web monolitico più semplice, o aggiungere i servizi con granularità grossolana a un'applicazione a più livelli. In questi casi, è comunque possibile effettuare usufruire del cloud PaaS funzionalità come quelle offerte dal servizio App di Azure. È comunque ridurre il lavoro di manutenzione per il limite.

Inoltre, poiché si sviluppa un nuovo codice in ottimizzato per il Cloud scenari (per un'applicazione completa o parziali sottosistemi), quando si crea nuovo codice, utilizzare le versioni più recenti di .NET ([.NET Core](../../../core/index.md) e [ASP.NET Core](/aspnet/core/), in particolare). Ciò vale soprattutto se si creano contenitori e microservizi perché .NET Core è un framework pulito e veloce. Si otterrà un footprint di memoria di piccole dimensioni e l'avvio rapido nei contenitori e le applicazioni saranno elevate. Questo approccio si adatta perfettamente con i requisiti dei contenitori e microservizi e si ottengono i vantaggi di un libreria multipiattaforma framework-essere in grado di eseguire la stessa applicazione su Linux, Windows Server e computer Mac per ambienti di sviluppo.

## <a name="cloud-native-applications-with-cloud-optimized-applications"></a>Applicazioni cloud nativo con applicazioni ottimizzato su Cloud

[Cloud nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) è uno stato più avanzato o avanzato per le applicazioni di grandi dimensioni e mission-critical. Le applicazioni cloud nativo in genere richiedono l'architettura e progettazione creati da zero anziché modernizzazione applicazioni esistenti. La differenza principale tra un'applicazione cloud nativa e un'app web ottimizzato su Cloud più semplice distribuito PaaS è l'indicazione per utilizzare le architetture di microservizi in un approccio cloud nativo. Ottimizzato per il cloud App può anche essere le app web monolitico o a più livelli distribuito in un cloud servizio PaaS come servizio App di Azure.

Il [App dodici Factor](https://12factor.net/) (una raccolta di modelli che sono strettamente correlate agli approcci di microservizi) è considerata anche un requisito per [cloud nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) architetture di applicazioni.

Il [Foundation elaborazione nativa Cloud (CNCF)](https://www.cncf.io/) è un promotore principale dei principi cloud nativo. Microsoft è un [appartenente il CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Per una definizione di esempio e per ulteriori informazioni sulle caratteristiche di applicazioni cloud nativo, vedere l'articolo Gartner [come a progettare le applicazioni cloud nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Per indicazioni specifiche su come implementare un'applicazione cloud nativo di Microsoft, vedere [microservizi .NET: architettura per applicazioni .NET nei contenitori](https://aka.ms/microservicesebook).

Il fattore più importante da considerare se si esegue la migrazione di un'applicazione completa per la [cloud nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) modello è che è necessario progettare nuovamente in un'architettura basata su microservizi. Chiaramente, ciò richiede un investimento significativo in fase di sviluppo a causa di grandi dimensioni refactoring processo. In genere si sceglie questa opzione per le applicazioni mission-critical che richiedono nuovi livelli di scalabilità e flessibilità a lungo termine. Tuttavia, è possibile avviare lo spostamento verso il cloud nativo mediante l'aggiunta di microservizi per pochi nuovi scenari e infine effettuare il refactoring dell'applicazione completamente in microservizi. Questo è un approccio incrementale è l'opzione migliore per alcuni scenari.

## <a name="what-about-microservices"></a>Per quanto riguarda microservizi? 

È importante comprendere microservizi e come funzionano se si siano valutando le applicazioni cloud nativo per l'organizzazione.

L'architettura di microservizi è un approccio avanzato che è possibile utilizzare per le applicazioni che vengono create da zero o quando è sviluppare le applicazioni esistenti (locale o cloud pronto DevOps App) verso applicazioni cloud nativo. È possibile avviare aggiungendo alcuni microservizi alle applicazioni esistenti per apprendere i paradigmi di microservizi nuovo. Ma ovviamente, è necessario architetto e codice, in particolare per questo tipo di approccio architetturale.

Tuttavia, microservizi non sono obbligatori per tutte le applicazioni moderne o nuovo. Microservizi non sono un "punto elenco magic" e non sono il modo migliore per creare ogni applicazione. Come e quando si usano microservizi dipende dal tipo di applicazione che si desidera compilare.

L'architettura di microservizi è sempre la scelta migliore per le applicazioni cruciali distribuite e grandi dimensioni o complesse basati su più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata su microservizi, un'applicazione basata su una raccolta di servizi che possono essere sviluppate in modo indipendente, testati, con controllo delle versioni, distribuiti e ridimensionata. Può trattarsi di qualsiasi database autonomo, correlati per microservizio.

Per informazioni dettagliate in un'architettura di microservizi che è possibile implementare con .NET Core, vedere l'e-book a PDF scaricabile [microservizi .NET: architettura per applicazioni .NET nei contenitori](https://aka.ms/microservicesebook). La Guida è disponibile anche [online](../../microservices-architecture/index.md).

Ma anche negli scenari in cui microservizi offrono potente funzionalità indipendenti dalla distribuzione, i limiti del sottosistema sicuro e diversità di tecnologia-generano anche molte nuove sfide. I problemi sono correlati allo sviluppo di applicazioni distribuite, ad esempio i modelli di dati frammentati e indipendente; ottenere resiliente comunicazione tra microservizi; la necessità di coerenza finale; e la complessità operativa. Microservizi introducono un livello superiore rispetto alle tradizionali applicazioni monolitiche di complessità.

A causa della complessità di un'architettura di microservizi, solo a scenari specifici e a determinati tipi di applicazioni sono adatti per le applicazioni basate su microservizio. Sono incluse le applicazioni di grandi e complesse con più evoluzione sottosistemi. In questi casi, è opportuno investire in un'architettura più complessa di software, per una maggiore flessibilità a lungo termine e la manutenzione dell'applicazione più efficiente. Ma per scenari meno complessi, potrebbe essere meglio continuare con un approccio monolitico applicazione o si avvicina di più semplice a più livelli.

Come nota finale, anche a rischio di essere ricorrenti su questo concetto, non deve si osserva l'utilizzo di microservizi nelle applicazioni come "secondo o nulla*.*" È possibile estendere e sviluppare applicazioni monolitiche esistente aggiungendo nuovi scenari di piccole dimensioni basati su microservizi. Non è necessario iniziare da zero per iniziare a lavorare con un approccio architetturale microservizi. In effetti, è consigliabile che evolvono dall'utilizzo di un'applicazione monolitica o a più livelli esistente aggiungendo nuovi scenari. Infine, è possibile suddividere l'applicazione in componenti autonomi o microservizi. È possibile avviare l'evoluzione monolitiche applicazioni in una direzione di microservizi dettagliate.

## <a name="when-to-use-azure-app-service-for-modernizing-existing-net-apps"></a>Modalità di utilizzo di servizio App di Azure per modernizzazione app .NET esistenti

Quando si modernizzare le applicazioni web ASP.NET esistenti a livello di maturità ottimizzato su Cloud, poiché le applicazioni web sono state sviluppate con .NET Framework, le dipendenze principale sono in Windows e, probabilmente, Internet Information Server (IIS). È possibile utilizzare e distribuire le applicazioni basate su Windows e IIS tramite la distribuzione direttamente in [Azure App Service](https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is) o innanzitutto containerizing l'applicazione usando i contenitori di Windows. Se containerizing, distribuire le applicazioni di contenitori di Windows gli host (basato su macchina virtuale) o a un'infrastruttura di Azure del servizio cluster che supporta i contenitori di Windows.

Quando si usano i contenitori di Windows, si ottengono tutti i vantaggi di creazione dei contenitori. Aumentare la flessibilità di spedizione e la distribuzione dell'app e ridurre le forze di attrito per problemi di ambiente (gestione temporanea, sviluppo e test o produzione). Nelle sezioni successive, è più dettagliatamente sui vantaggi che offerti dall'utilizzo di contenitori.

Al momento della stesura di questa Guida, il servizio App di Azure non supporta i contenitori di Windows. Supporta i contenitori di Linux. Pertanto, potrebbe essere la domanda successiva, "Come è possibile scegliere tra servizio App di Azure e i contenitori di Windows?"

In pratica, se non ci siano tutti i server e dipendenze personalizzate bloccare il percorso per l'utilizzo di servizio App di servizio App di Azure appropriato per l'applicazione, è necessario eseguire la migrazione l'applicazione web .NET esistente al servizio App. Che è il modo più semplice ed efficace per gestire l'applicazione. In Azure, l'applicazione inoltre sarà necessario un percorso di manutenzione più semplice poiché vantaggi dall'infrastruttura di PaaS, quali DBaaS, CaaS e STaaS.

Tuttavia, se in un'applicazione server o dipendenze personalizzate che non sono supportate nel servizio App di Azure, potrebbe essere necessario considerare le opzioni che si basano sui contenitori di Windows. Esempi di server o dipendenze personalizzate includono software di terze parti o un file con estensione msi, che deve essere installato nel server, ma che non è supportato in Azure App Service. Un altro esempio è di qualsiasi altra configurazione di server che non è supportata in Azure App Service, come l'uso di assembly nella Global Assembly Cache (GAC) o COM / componenti COM+. Grazie a immagini contenitore di Windows, è possibile includere le dipendenze personalizzate nella stessa "unità di distribuzione."

In alternativa, è possibile eseguire il refactoring di aree dell'applicazione che non sono supportate dal servizio App di Azure. A seconda del volume di lavoro refactoring richiederebbe, è necessario valutare attentamente se che vale la pena in caso contrario.

### <a name="benefits-of-moving-to-azure-app-service"></a>Vantaggi di spostamento in Azure App Service

Servizio App di Azure è un PaaS completamente gestito che semplifica la creazione di applicazioni web che sono supportate da processi di business. Quando si utilizza il servizio App, si evita i costi di gestione dell'infrastruttura associati con l'aggiornamento e la gestione di App web in locale. In particolare, tagliare l'hardware e sui costi delle licenze di esecuzione di applicazioni web in locale.

Se l'applicazione web è idoneo per la migrazione di servizio App di Azure, il vantaggio principale è la quantità di tempo che necessario per spostare l'app ridotta. Servizio App offre un ambiente molto semplice in cui iniziare.

Servizio App di Azure è la scelta migliore per la maggior parte delle applicazioni web perché è la più semplice PaaS in Azure che è possibile utilizzare per eseguire le applicazioni web. Gestione e distribuzione sono integrati nella piattaforma, siti rapidamente ridimensionati in modo da gestire carichi di traffico elevata e la gestione di traffico e di bilanciamento del carico incorporati garantire un'elevata disponibilità.

Anche il monitoraggio delle applicazioni web è semplice, tramite Azure Application Insights. Application Insights viene distribuito gratuitamente con il servizio App e non richiede la scrittura di codice speciale nell'applicazione. Eseguire semplicemente l'app web nel servizio App e si otterrà un sistema di monitoraggio accattivanti, senza ulteriore lavoro.

Con il servizio App, è possibile utilizzare anche direttamente molte applicazioni open source dalla raccolta di applicazioni Web di Azure (ad esempio, WordPress o Umbraco) oppure è possibile creare un nuovo sito usando gli strumenti di propria scelta, come ASP.NET e framework. La funzionalità processi Web di servizio App è facile aggiungere processo in background di elaborazione per l'app web di servizio App.

Vantaggi della migrazione delle applicazioni web tramite la funzionalità di App Web di servizio App di Azure includono:

-   Ridimensionamento automatico per soddisfare la richiesta nei periodi di intensa e ridurre i costi orari non interattiva.

-   Backup automatico del sito per proteggere dati e le modifiche.

-   Elevata disponibilità e resilienza sulla piattaforma Azure PaaS.

-   Slot di distribuzione per lo sviluppo e di ambienti di gestione temporanea e per il testing di più modelli di sito.

-   Il bilanciamento del carico e la protezione Distributed Denial of Service (DDoS).

-   Gestione del traffico per indirizzare gli utenti per la distribuzione geografica più vicina.

Anche se il servizio App potrebbe essere la scelta migliore per nuove app web, tuttavia, per le applicazioni esistenti, servizio App potrebbe essere la scelta migliore solo se le dipendenze dell'applicazione sono supportate nel servizio App.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Analisi di compatibilità per il servizio App di Azure**  
[https://www.migratetoazure.net/Resources](https://www.migratetoazure.net/Resources)


### <a name="benefits-of-moving-to-windows-containers"></a>Vantaggi di spostamento per i contenitori di Windows

Il principale vantaggio dell'utilizzo di contenitori di Windows è che è possibile ottenere un'esperienza di distribuzione più affidabile e migliorata, rispetto alle App non contenitore. Inoltre, che l'applicazione moderno e in modo efficace con i contenitori rende l'applicazione pronto per molte altre piattaforme e i cloud che supportano i contenitori di Windows. I vantaggi di spostamento per i contenitori di Windows vengono analizzati più dettagliatamente nelle sezioni successive.

Gli ambienti di calcolo primario in Azure (in disponibilità generale, a partire da mid 2017) che supportano i contenitori di Windows sono Azure Service Fabric e base host di contenitori di Windows (Windows Server 2016 VM). Questi ambienti sono gli scenari dell'infrastruttura principale trattati in questa Guida.

È anche possibile distribuire i contenitori di Windows per altri orchestrators, ad esempio Kubernetes, Docker Swarm o controller di dominio o del sistema operativo. Attualmente (anticipata rientrano 2017), queste piattaforme sono in anteprima nel servizio contenitore di Azure per l'utilizzo di contenitori di Windows.

>[!div class="step-by-step"]
[Precedente](microsoft-technologies-in-cloud-devops-ready-applications.md)
[Successivo](how-to-deploy-existing-net-apps-to-azure-app-service.md)
