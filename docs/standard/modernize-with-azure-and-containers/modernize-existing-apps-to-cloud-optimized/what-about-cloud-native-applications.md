---
title: Informazioni sulle app cloud native
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Per quanto riguarda le applicazioni Native del Cloud?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 10f7761b7c0d2ddd8cb9247b1a02aa49cdc4e5d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012100"
---
# <a name="what-about-cloud-native-applications"></a>Informazioni sulle app cloud native

Sebbene [nativa del Cloud](https://azure.microsoft.com/overview/cloudnative/) applicazioni non sono l'obiettivo principale di questa Guida, è utile per avere una conoscenza di questo livello di maturità della modernizzazione e per distinguerlo dalle applicazioni ottimizzato per il Cloud.

Figura 4-3 posiziona App Native del Cloud nei livelli di maturità modernizzazione di applicazioni:

![Posizionamento di applicazioni Native del Cloud](./media/image3.png)

> **Figura 4-3.** Posizionamento di applicazioni Native del Cloud

Il livello di maturità di modernizzazione Native del Cloud richiede in genere nuovi investimenti di sviluppo. Passare al livello di Cloud Native in genere si basa sulle esigenze aziendali per modernizzare le applicazioni quanto più possibile per migliorare concretamente la scalabilità in applicazioni di grandi dimensioni mediante la creazione di sottosistemi autonomi (microservizi) che possono essere distribuiti e scalabilità in modo indipendente da altre aree dell'applicazione riducendo i costi nella flessibilità di evoluzione di lungo termine e l'aumento delle parti dell'app tali autonomi che forniscono significativi competere vantaggi.

I concetti di base di applicazioni Native del Cloud si basano su approcci di architettura di microservizi, che possono evolvere con la flessibilità e scalabilità per i limiti che sarebbero difficili da eseguire in un'architettura monolitica, distribuita in locale o cloud ambiente.

Figura 4-4 illustra le caratteristiche principali del modello e Native del Cloud.

> ![Caratteristiche Native del cloud sono resilienti per il cloud, agenti di orchestrazione dei contenitori, Microservizi e senza server](./media/image4.png)
>
> **Figura 4-4.** Caratteristiche e Native del cloud

Inoltre, è possibile estendere base moderne App web e App native del cloud aggiungendo altri servizi, come l'intelligenza artificiale (AI), machine learning (ML) e IoT. È possibile usare uno di questi servizi per estendere uno degli approcci possibili ottimizzato per il Cloud.

La differenza fondamentale nelle applicazioni a livello nativo del Cloud è nell'architettura dell'applicazione. Le applicazioni native del cloud sono, per definizione, le app basate su microservizi. App native del cloud richiedono speciali architetture, tecnologie e piattaforme, rispetto a un'applicazione web monolitica o a più livelli tradizionali.

## <a name="cloud-native-applications-details"></a>Dettagli di applicazioni native del cloud

Native del cloud è uno stato più avanzato o maturo per le applicazioni di grandi dimensioni e mission-critical. Applicazioni Native del cloud in genere richiedono l'architettura e progettazione che vengono creati da zero anziché tramite la modernizzazione delle applicazioni esistenti. La differenza principale tra un'applicazione nativa del Cloud e una semplice app web ottimizzato per il Cloud è consigliabile utilizzare le architetture di microservizi in un approccio native del cloud. Le app ottimizzato per il cloud possono essere anche App web monolitica o a più livelli.

Il [App a dodici fattori](https://12factor.net/) (una raccolta di modelli che sono strettamente correlati agli approcci di microservizi) considerata anche un requisito per architetture di applicazioni native del cloud.

Il [Foundation Computing nativa Cloud (CNCF)](https://www.cncf.io/) è un promotore primario dei principi native del cloud. Microsoft è un [membro del CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Per una definizione di esempio e per altre informazioni sulle caratteristiche di applicazioni native del cloud, vedere l'articolo di Gartner [come definire l'architettura e progettazione di applicazioni native del cloud](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Per indicazioni specifiche su come implementare un'applicazione nativa del cloud di Microsoft, vedere [microservizi .NET: Architettura per applicazioni .NET in contenitori](https://aka.ms/microservicesebook).

Il fattore più importante da prendere in considerazione se si esegue la migrazione di un'applicazione completa al modello e native del cloud è che è necessario ridefinizione dell'architettura per un'architettura basata su microservizi. Chiaramente ciò richiede un investimento significativo in fase di sviluppo a causa del processo di refactoring grande coinvolto. In genere si sceglie questa opzione per applicazioni mission-critical che richiedono nuovi livelli di scalabilità e flessibilità a lungo termine. Tuttavia, è possibile avviare lo spostamento verso native del cloud mediante l'aggiunta di microservizi per pochi nuovi scenari e infine eseguire il refactoring l'applicazione completamente come microservizi. Si tratta di un approccio incrementale che è l'opzione migliore per alcuni scenari.

## <a name="what-about-microservices"></a>Per quanto riguarda i microservizi?

Se si siano valutando le applicazioni native del cloud per l'organizzazione è importante comprendere i microservizi e sul relativo funzionamento.

L'architettura di microservizi è un approccio avanzato che è possibile usare per le applicazioni che vengono create da zero oppure quando è sviluppare le applicazioni esistenti verso applicazioni native del cloud. È possibile iniziare aggiungendo alcuni microservizi per le applicazioni esistenti per apprendere nuovi paradigmi di microservizi. Ma, ovviamente, è necessario architect e codice, in particolare per questo tipo di approccio architetturale.

Tuttavia, i microservizi non sono obbligatori per tutte le applicazioni moderne o nuovo. I Microservizi non sono un "punto elenco magic" e non sono il metodo migliore singolo per creare tutte le applicazioni. Come e quando si usano i microservizi varia a seconda del tipo di applicazione che si vuole compilare.

L'architettura di microservizi sta diventando l'approccio consigliato per applicazioni mission-critical distribuite di grandi dimensioni o complesse basate su più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata su microservizi, un'applicazione viene compilata come una raccolta di servizi che possono essere sviluppate in modo indipendente, testati, con controllo delle versioni, distribuiti e ridimensionati. Può trattarsi di qualsiasi database autonomo correlato per ogni microservizio.

Per un approfondimento su un'architettura di microservizi che è possibile implementare usando .NET Core, vedere l'e-book PDF scaricabile [microservizi .NET: Architettura per applicazioni .NET in contenitori](https://aka.ms/microservicesebook). Questa guida è inoltre disponibile [online](../../microservices-architecture/index.md).

Ma anche negli scenari in cui i microservizi offrono potenti indipendente dalla funzionalità di distribuzione, i limiti del sottosistema sicuro ed eterogeneità di tecnologie-generano anche numerose problematiche di nuovo. Le problematiche correlate allo sviluppo di applicazioni distribuite, ad esempio modelli di dati indipendenti e frammentati. comunicazione resiliente tra microservizi; la necessità di coerenza finale; e complessità operativa. I Microservizi presentano un livello superiore di complessità rispetto alle tradizionali applicazioni monolitiche.

A causa della complessità di un'architettura di microservizi, solo scenari specifici e ad alcuni tipi di applicazione sono adatte per applicazioni basate su microservizi. Sono incluse le applicazioni di grandi dimensioni e complesse con più sottosistemi in fase di evoluzione. In questi casi, vale la pena investire in un'architettura software più complessa, per una maggiore flessibilità a lungo termine e la manutenzione dell'applicazione più efficiente. Tuttavia, per gli scenari meno complessi, potrebbe essere meglio continuare con un approccio applicazione monolitica o approcci più semplici a più livelli.

Come nota finale, anche a rischio being ricorrenti su questo concetto e non deve esaminare usando i microservizi nelle applicazioni come "tua o niente affatto." È possibile estendere e sviluppare le applicazioni monolitiche esistenti mediante l'aggiunta di nuovi scenari di piccole dimensioni basati su microservizi. Non è necessario iniziare da zero per iniziare a usare un approccio di architettura di microservizi. In effetti, è consigliabile che evolvono dall'uso di un'applicazione monolitica o a più livelli esistente aggiungendo nuovi scenari. Infine, è possibile suddividere l'applicazione in componenti autonomi o microservizi. È possibile iniziare l'evoluzione delle applicazioni monolitiche in una direzione di microservizi, passo a passo.

In ogni caso, il resto della presenta Guida si concentra la maggior parte di tutte sul "Nessuna App basate su microservizi" perché questo materiale sussidiario è destinato principalmente alla modernizzazione delle App esistenti che hanno in genere le architetture monolitiche o a più livelli.

> [!div class="step-by-step"]
> [Precedente](microsoft-technologies-in-cloud-optimized-applications.md)
> [Successivo](deploy-existing-net-apps-as-windows-containers.md)
