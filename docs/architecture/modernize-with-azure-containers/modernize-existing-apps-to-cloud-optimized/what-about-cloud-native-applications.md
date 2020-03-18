---
title: Informazioni sulle app cloud native
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . E le applicazioni Cloud-Native?
ms.date: 04/28/2018
ms.openlocfilehash: d2a7f89e347d75ddbdae84c8eb57e32447b83297
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543547"
---
# <a name="what-about-cloud-native-applications"></a>Informazioni sulle app cloud native

Anche se le applicazioni [Cloud-Native](https://azure.microsoft.com/overview/cloudnative/) non sono l'obiettivo principale di questa guida, è utile avere una comprensione di questo livello di maturità di modernizzazione e distinguerlo dalle applicazioni ottimizzate per il cloud.

Figura 4-3 posizioni Cloud-Native applicazioni nei livelli di maturità di modernizzazione dell'applicazione:

![Diagramma che illustra come posizionare le applicazioni native nel cloud.](./media/what-about-cloud-native-applications/positioning-cloud-native-applications.png)

**Figura 4-3.** Posizionamento di applicazioni Cloud-Native

Il livello di maturità della modernizzazione Cloud-Native richiede solitamente nuovi investimenti di sviluppo. Il passaggio al livello Cloud-Native è in genere guidato dalle esigenze aziendali per modernizzare le applicazioni il più possibile per migliorare drasticamente la scalabilità nelle applicazioni di grandi dimensioni creando sottosistemi autonomi (microservizi) che possono essere distribuiti e scalabili in modo indipendente da altre aree dell'applicazione, riducendo i costi a lungo termine e aumentando l'agilità evolutiva delle parti di tali applicazioni autonome che forniscono vantaggi di concorrenza significativi.

I pilastri principali delle applicazioni Cloud-Native sono basati su approcci di architettura di microservizi, che possono evolvere con agilità e scalabilità a limiti difficili da raggiungere in un'architettura monolitica, distribuita in locale o cloud Ambiente.

Nella figura 4-4 sono illustrate le caratteristiche principali del modello Cloud-Native.

![Diagramma che elenca le principali caratteristiche native del cloud.](./media/what-about-cloud-native-applications/cloud-native-characteristics.png)

**Figura 4-4.** Caratteristiche di Cloud-Native

Inoltre, è possibile estendere le app Web moderne di base e le app native nel cloud aggiungendo altri servizi, ad esempio l'intelligenza artificiale (AI), l'apprendimento automatico (ML) e l'IoT. È possibile utilizzare uno di questi servizi per estendere uno dei possibili approcci ottimizzati per il cloud.

La differenza fondamentale nelle applicazioni a livello di Cloud-Native è nell'architettura dell'applicazione. Le applicazioni native del cloud sono, per definizione, app basate su microservizi. Le app native per il cloud richiedono architetture, tecnologie e piattaforme speciali, rispetto a un'applicazione Web monolitica o a un'applicazione a più livelli tradizionale.

## <a name="cloud-native-applications-details"></a>Dettagli sulle applicazioni native del cloud

Cloud-Native è uno stato più avanzato o maturo per applicazioni di grandi dimensioni e mission-critical. Le applicazioni cloud native richiedono in genere l'architettura e la progettazione create da zero anziché la modernizzazione delle applicazioni esistenti. La differenza principale tra un'applicazione Cloud-Native e un'app Web ottimizzata per il cloud più semplice è la raccomandazione di usare le architetture di microservizi in un approccio cloud-native. Le app ottimizzate per il cloud possono anche essere app Web monolitiche o app a più livelli.

[L'app](https://12factor.net/) a dodici fattori (una raccolta di modelli strettamente correlati agli approcci ai microservizi) è anche considerata un requisito per le architetture di applicazioni native del cloud.

La [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) è un promotore primario dei principi cloud-native. Microsoft è [membro del CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Per indicazioni dettagliate su come progettare e sviluppare applicazioni native cloud, leggere i seguenti e-book gratuiti:

* [Architettura di applicazioni .NET native cloud per AzureArchitecting Cloud-Native .NET Applications for Azure](../../cloud-native/introduction.md)
* [Microservizi .NET: architettura per applicazioni .NET containerizzate.](../../microservices/index.md)

Il fattore più importante da considerare se si esegue la migrazione di un'applicazione completa al modello nativo cloud è che è necessario riprogettare un'architettura basata su microservizi. Ciò richiede chiaramente un investimento significativo nello sviluppo a causa del grande processo di refactoring coinvolto. Questa opzione viene in genere scelta per le applicazioni mission-critical che necessitano di nuovi livelli di scalabilità e agilità a lungo termine. Tuttavia, è possibile iniziare a passare a cloud-native aggiungendo microservizi per pochi nuovi scenari ed eventualmente refactoring l'applicazione completamente come microservizi. Si tratta di un approccio incrementale che è l'opzione migliore per alcuni scenari.

## <a name="what-about-microservices"></a>E i microservizi?

Comprendere i microservizi e il loro funzionamento è importante quando si considerano le applicazioni native cloud per l'organizzazione.

L'architettura dei microservizi è un approccio avanzato che è possibile usare per le applicazioni create da zero o quando si evolveno le applicazioni esistenti verso applicazioni native nel cloud. È possibile iniziare aggiungendo alcuni microservizi alle applicazioni esistenti per conoscere i nuovi paradigmi dei microservizi. Ma chiaramente, è necessario architetto e codice, soprattutto per questo tipo di approccio architettonico.

Tuttavia, i microservizi non sono obbligatori per qualsiasi applicazione nuova o moderna. I microservizi non sono un "proiettile magico" e non sono l'unico modo migliore per creare ogni applicazione. La modalità e l'utilizzo dei microservizi dipende dal tipo di applicazione che è necessario compilare.

L'architettura dei microservizi sta diventando l'approccio preferito per applicazioni mission-critical distribuite e complesse che si basano su più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata su microservizi, un'applicazione viene compilata come una raccolta di servizi che possono essere sviluppati, testati, sottoposti a controllo delle versioni, distribuiti e scalati in modo indipendente. Questo può includere qualsiasi database autonomo correlato per microservizio.

Per un'analisi dettagliata di un'architettura di microservizi che è possibile implementare utilizzando .NET Core, vedere i [microservizi .NET .NET scaricabili, vedere i microservizi .NET .NET scaricabili.](https://aka.ms/microservicesebook) La guida è disponibile anche [online.](../../microservices/index.md)

Ma anche in scenari in cui i microservizi offrono una distribuzione potente e indipendente dalle funzionalità, forti limiti dei sottosistemi e diversità tecnologica, sollevano anche molte nuove sfide. Le sfide sono correlate allo sviluppo di applicazioni distribuite, ad esempio modelli di dati frammentati e indipendenti; raggiungere una comunicazione resiliente tra i microservizi; la necessità di un'eventuale coerenza; complessità operativa. I microservizi introducono un livello di complessità più elevato rispetto alle applicazioni monolitiche tradizionali.

A causa della complessità di un'architettura di microservizi, solo scenari specifici e determinati tipi di applicazioni sono adatti per le applicazioni basate su microservizi. Queste includono applicazioni di grandi dimensioni e complesse con più sottosistemi in evoluzione. In questi casi, vale la pena investire in un'architettura software più complessa, per una maggiore agilità a lungo termine e una manutenzione delle applicazioni più efficiente. Tuttavia, per gli scenari meno complessi, potrebbe essere preferibile continuare con un approccio applicativo monolitico o approcci a più livelli più semplici.

Come nota finale, anche a rischio di essere ripetitivi su questo concetto, non si dovrebbe considerare l'utilizzo di microservizi nelle applicazioni come "all-in o niente affatto." È possibile estendere ed evolvere le applicazioni monolitiche esistenti aggiungendo nuovi scenari di piccole dimensioni basati su microservizi. Non è necessario iniziare da zero per iniziare a lavorare con un approccio all'architettura di microservizi. In effetti, è consigliabile evoluzione dall'utilizzo di un'applicazione monolitica o a più livelli esistente aggiungendo nuovi scenari. Infine, è possibile suddividere l'applicazione in componenti autonomi o microservizi. È possibile iniziare a sviluppare le applicazioni monolitiche in una direzione di microservizi, passo dopo passo.

In ogni caso, il resto di queste linee guida attuali si concentra soprattutto su "nessuna app basata su microservizi" perché questa guida è principalmente mirata alla modernizzazione delle app esistenti che di solito hanno architetture monolitiche o a più livelli.

> [!div class="step-by-step"]
> [Successivo](microsoft-technologies-in-cloud-optimized-applications.md)
> [precedente](deploy-existing-net-apps-as-windows-containers.md)
