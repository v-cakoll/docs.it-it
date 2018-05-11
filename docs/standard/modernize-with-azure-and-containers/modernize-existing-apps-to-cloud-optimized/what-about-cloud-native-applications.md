---
title: Per quanto riguarda le applicazioni Native Cloud?
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Per quanto riguarda le applicazioni Native Cloud?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 0e880689001ece2b770811cfbe3fea43aa425b32
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
---
# <a name="what-about-cloud-native-applications"></a>Per quanto riguarda le applicazioni Native Cloud?

Sebbene [Cloud nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) applicazioni non sono l'obiettivo principale di questa Guida, è utile per avere una conoscenza di questo livello di maturità modernizzazione e per distinguerlo dalle applicazioni ottimizzato su Cloud.

Figura 4-3 posiziona le app Cloud nativo nei livelli di maturità modernizzazione applicazione:

![Posizionamento delle applicazioni Cloud-nativo](./media/image3.png)

> **Figura 4-3.** Posizionamento delle applicazioni Cloud-nativo

Il livello di maturità modernizzazione nativo Cloud richiede in genere nuovi investimenti di sviluppo. Spostamento a livello di Cloud nativo in genere è dovuto a esigenze aziendali per modernizzare le applicazioni quanto più possibile migliorare drasticamente scala in applicazioni di grandi dimensioni mediante la creazione di sottosistemi autonomi (microservizi) che possono essere distribuiti e la scala in modo indipendente da altre aree dell'applicazione riducendo i costi nella flessibilità di evoluzione di lungo termine e l'aumento delle parti dell'app tali autonomi che forniscono significativi competere vantaggi. 

I concetti di base di [Cloud nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) applicazioni si basano gli approcci di architettura microservizi, che possono evolvere con una maggiore flessibilità e scalabilità entro i limiti che sarebbe difficile da eseguire in un'architettura monolitica distribuita a uno in locale o un ambiente cloud.

Figura 4-4 mostra le principali caratteristiche del modello di Cloud nativo.  

> ![Caratteristiche di cloud nativo sono Microservizi, contenitori, cloud resilienti, orchestrators e serverles](./media/image4.png)
>
> **Figura 4-4.** Caratteristiche di cloud-nativo

Inoltre, è possibile estendere le app web moderna base e le app cloud nativo mediante l'aggiunta di altri servizi, quali intelligence artificiale (AI), l'apprendimento automatico (ML) e IoT. È possibile utilizzare uno di questi servizi per estendere uno degli approcci possibili ottimizzato su Cloud.

La differenza fondamentale nelle applicazioni a livello di codice nativo Cloud è nell'architettura dell'applicazione. [Cloud nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) applicazioni sono per definizione, le applicazioni basate su microservizi. App cloud nativo richiedono speciali architetture, tecnologie e piattaforme, rispetto a un'applicazione web monolitico o a più livelli tradizionale.

## <a name="cloud-native-applications-details"></a>Dettagli di applicazioni cloud-nativo

[Cloud nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) è uno stato più avanzato o avanzato per le applicazioni di grandi dimensioni e mission-critical. Le applicazioni cloud nativo richiedono in genere architettura e progettazione vengono creati da zero anziché modernizzazione le applicazioni esistenti. La differenza principale tra un'applicazione Cloud nativa e un'app web ottimizzato su Cloud più semplice è le raccomandazioni per usare le architetture di microservizi in un approccio cloud nativo. Le app ottimizzato su cloud possono essere anche le app web monolitico o a più livelli.

Il [App dodici Factor](https://12factor.net/) (una raccolta di modelli che sono strettamente correlate agli approcci di microservizi) anche viene considerata un requisito per [cloud nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) architetture di applicazioni.

Il [Foundation elaborazione nativa Cloud (CNCF)](https://www.cncf.io/) è un promotore principale dei principi cloud nativo. Microsoft è un [appartenente il CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Per una definizione di esempio e per ulteriori informazioni sulle caratteristiche di applicazioni cloud nativo, vedere l'articolo Gartner [come a progettare le applicazioni cloud nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Per indicazioni specifiche su come implementare un'applicazione cloud nativo di Microsoft, vedere [microservizi .NET: architettura per applicazioni .NET nei contenitori](https://aka.ms/microservicesebook).

Il fattore più importante da considerare se si esegue la migrazione di un'applicazione completa per la [cloud nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) modello è che è necessario ridefinizione dell'architettura per un'architettura basata su microservizi. Chiaramente, ciò richiede un investimento significativo in fase di sviluppo a causa di grandi dimensioni refactoring processo. In genere si sceglie questa opzione per le applicazioni mission-critical che richiedono nuovi livelli di scalabilità e flessibilità a lungo termine. Tuttavia, è possibile avviare lo spostamento verso il cloud nativo mediante l'aggiunta di microservizi per pochi nuovi scenari e infine effettuare il refactoring dell'applicazione completamente in microservizi. Questo è un approccio incrementale è l'opzione migliore per alcuni scenari.

## <a name="what-about-microservices"></a>Per quanto riguarda microservizi? 

È importante comprendere microservizi e come funzionano se si siano valutando le applicazioni cloud nativo per l'organizzazione.

L'architettura di microservizi è un approccio avanzato che è possibile utilizzare per le applicazioni che vengono create da zero o quando è sviluppare le applicazioni esistenti per le applicazioni cloud nativo. È possibile avviare aggiungendo alcuni microservizi alle applicazioni esistenti per apprendere i paradigmi di microservizi nuovo. Ma ovviamente, è necessario architetto e codice, in particolare per questo tipo di approccio architetturale.

Tuttavia, microservizi non sono obbligatori per tutte le applicazioni moderne o nuovo. Microservizi non sono un "punto elenco magic" e non sono il modo migliore per creare ogni applicazione. Come e quando si usano microservizi dipende dal tipo di applicazione che si desidera compilare.

L'architettura di microservizi è sempre la scelta migliore per le applicazioni cruciali distribuite e grandi dimensioni o complesse basati su più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata su microservizi, un'applicazione basata su una raccolta di servizi che possono essere sviluppate in modo indipendente, testati, con controllo delle versioni, distribuiti e ridimensionata. Può trattarsi di qualsiasi database autonomo, correlati per microservizio.

Per informazioni dettagliate in un'architettura di microservizi che è possibile implementare con .NET Core, vedere l'e-book a PDF scaricabile [microservizi .NET: architettura per applicazioni .NET nei contenitori](https://aka.ms/microservicesebook). La Guida è disponibile anche [online](../../microservices-architecture/index.md).

Ma anche negli scenari in cui microservizi offrono potente funzionalità indipendenti dalla distribuzione, i limiti del sottosistema sicuro e diversità di tecnologia-generano anche molte nuove sfide. I problemi sono correlati allo sviluppo di applicazioni distribuite, ad esempio i modelli di dati frammentati e indipendente; ottenere resiliente comunicazione tra microservizi; la necessità di coerenza finale; e la complessità operativa. Microservizi introducono un livello superiore rispetto alle tradizionali applicazioni monolitiche di complessità.

A causa della complessità di un'architettura di microservizi, solo a scenari specifici e a determinati tipi di applicazioni sono adatti per le applicazioni basate su microservizio. Sono incluse le applicazioni di grandi e complesse con più evoluzione sottosistemi. In questi casi, è opportuno investire in un'architettura più complessa di software, per una maggiore flessibilità a lungo termine e la manutenzione dell'applicazione più efficiente. Ma per scenari meno complessi, potrebbe essere meglio continuare con un approccio monolitico applicazione o si avvicina di più semplice a più livelli.

Come nota finale, anche a rischio being ricorrenti su questo concetto, non dovrebbero esaminare tramite microservizi nelle applicazioni come "secondo o nulla." È possibile estendere e sviluppare applicazioni monolitiche esistente aggiungendo nuovi scenari di piccole dimensioni basati su microservizi. Non è necessario iniziare da zero per iniziare a lavorare con un approccio architetturale microservizi. In effetti, è consigliabile che evolvono dall'utilizzo di un'applicazione monolitica o a più livelli esistente aggiungendo nuovi scenari. Infine, è possibile suddividere l'applicazione in componenti autonomi o microservizi. È possibile avviare l'evoluzione monolitiche applicazioni in una direzione di microservizi dettagliate.

In ogni caso, il resto della presenta Guida è incentrata la maggior parte di tutti i su "Nessuna App basate su microservizi" poiché questa guida è destinato principalmente a moderna del App esistenti che hanno in genere architetture monolitiche o a più livelli.


>[!div class="step-by-step"]
[Precedente](microsoft-technologies-in-cloud-optimized-applications.md)
[Successivo](deploy-existing-net-apps-as-windows-containers.md)
