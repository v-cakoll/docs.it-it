---
title: Informazioni sulle app cloud native
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Cosa accade per le applicazioni native del cloud?
ms.date: 04/28/2018
ms.openlocfilehash: d2a7f89e347d75ddbdae84c8eb57e32447b83297
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543547"
---
# <a name="what-about-cloud-native-applications"></a>Informazioni sulle app cloud native

Sebbene le applicazioni [native del cloud](https://azure.microsoft.com/overview/cloudnative/) non siano l'obiettivo principale di questa guida, è utile conoscere il livello di maturità della modernizzazione e distinguerlo dalle applicazioni ottimizzate per il cloud.

Figura 4-3 posizioni delle app native del cloud nei livelli di maturità della modernizzazione delle applicazioni:

![Diagramma che illustra come posizionare le applicazioni native del cloud.](./media/what-about-cloud-native-applications/positioning-cloud-native-applications.png)

**Figura 4-3.** Posizionamento di applicazioni native del cloud

Il livello di maturità della modernizzazione nativa del cloud richiede in genere nuovi investimenti di sviluppo. Il passaggio al livello nativo del cloud è in genere determinato dalla necessità aziendale di modernizzare le applicazioni il più possibile per migliorare drasticamente la scalabilità in applicazioni di grandi dimensioni creando sottosistemi autonomi (microservizi) che possono essere distribuiti e ridimensionati in modo indipendente da altre aree dell'applicazione, riducendo i costi a lungo termine e aumentando l'agilità dell'evoluzione delle parti dell'app autonoma che offrono vantaggi significativi in termini di concorrenza.

I principali pilastri delle applicazioni native del cloud sono basati su approcci di architettura di microservizi, che possono evolversi con agilità e scalabilità fino a limiti che sarebbero difficili da ottenere in un'architettura monolitica, distribuiti in locale o nel cloud. ambiente.

La figura 4-4 illustra le caratteristiche principali del modello nativo del cloud.

![Diagramma che elenca le principali caratteristiche native del cloud.](./media/what-about-cloud-native-applications/cloud-native-characteristics.png)

**Figura 4-4.** Caratteristiche native del cloud

Inoltre, è possibile estendere app Web moderne e app native del cloud aggiungendo altri servizi, ad esempio intelligenza artificiale, Machine Learning (ML) e molto altro. È possibile usare uno di questi servizi per estendere i possibili approcci ottimizzati per il cloud.

La differenza fondamentale nelle applicazioni a livello nativo del cloud è l'architettura dell'applicazione. Le applicazioni native del cloud sono, per definizione, app basate su microservizi. Le app native del cloud richiedono architetture, tecnologie e piattaforme speciali, rispetto a un'applicazione Web monolitica o a una tradizionale applicazione a più livelli.

## <a name="cloud-native-applications-details"></a>Dettagli sulle applicazioni native del cloud

Il cloud nativo è uno stato più avanzato o maturo per applicazioni di grandi dimensioni e cruciali. Le applicazioni native del cloud richiedono in genere architettura e progettazione create da zero anziché modernizzando le applicazioni esistenti. La differenza principale tra un'applicazione nativa del cloud e una più semplice app Web ottimizzata per il cloud è la raccomandazione di usare architetture di microservizi in un approccio nativo per il cloud. Le app ottimizzate per il cloud possono essere anche app Web monolitiche o app a più livelli.

L' [app a dodici fattori](https://12factor.net/) (una raccolta di modelli strettamente correlati a approcci di microservizi) viene considerata anche un requisito per le architetture di applicazioni native del cloud.

[Cloud native Computing Foundation (CNCF)](https://www.cncf.io/) è un promotore primario di principi nativi del cloud. Microsoft è [membro di CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Per istruzioni dettagliate su come progettare e sviluppare applicazioni native del cloud, leggere gli e-book gratuiti seguenti:

* [Architettura di applicazioni .NET native del cloud per Azure](../../cloud-native/introduction.md)
* [Microservizi .NET: architettura per le applicazioni .NET in contenitori](../../microservices/index.md).

Il fattore più importante da considerare quando si esegue la migrazione di un'applicazione completa al modello nativo del cloud è che è necessario riprogettare un'architettura basata su microservizi. Questa operazione richiede chiaramente un investimento significativo nello sviluppo a causa del notevole processo di refactoring. Questa opzione viene in genere scelta per le applicazioni cruciali che necessitano di nuovi livelli di scalabilità e agilità a lungo termine. Tuttavia, è possibile iniziare a passare a native del cloud aggiungendo microservizi per alcuni nuovi scenari e infine effettuare il refactoring dell'applicazione come microservizi. Si tratta di un approccio incrementale che rappresenta la scelta migliore per alcuni scenari.

## <a name="what-about-microservices"></a>Quali sono i microservizi?

Conoscere i microservizi e il relativo funzionamento è importante quando si considerano le applicazioni native del cloud per l'organizzazione.

L'architettura dei microservizi è un approccio avanzato che è possibile usare per le applicazioni create da zero o quando si evolvono le applicazioni esistenti verso applicazioni native del cloud. È possibile iniziare aggiungendo alcuni microservizi alle applicazioni esistenti per ottenere informazioni sui nuovi paradigmi di microservizi. Ovviamente, è necessario progettare e scrivere codice, in particolare per questo tipo di approccio architettonico.

I microservizi, tuttavia, non sono obbligatori per qualsiasi applicazione nuova o moderna. I microservizi non sono "Magic Bullet" e non sono il singolo modo migliore per creare tutte le applicazioni. Il modo in cui e quando si usano i microservizi dipende dal tipo di applicazione che è necessario compilare.

L'architettura dei microservizi sta diventando l'approccio preferito per le applicazioni mission-critical distribuite e grandi o complesse basate su più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata su microservizi, un'applicazione viene creata come una raccolta di servizi che possono essere sviluppati, testati, sottoposti a controllo delle versioni, distribuiti e ridimensionati in modo indipendente. Questo può includere qualsiasi database autonomo correlato per microservizio.

Per un'analisi dettagliata di un'architettura di microservizi che è possibile implementare con .NET Core, vedere l'e-book PDF scaricabile [per i microservizi .NET: architettura per le applicazioni .NET in contenitori](https://aka.ms/microservicesebook). La guida è disponibile anche in [linea](../../microservices/index.md).

Tuttavia, anche negli scenari in cui i microservizi offrono potenti funzionalità indipendenti dalla distribuzione, i limiti del sottosistema e la diversità tecnologica, generano anche molte nuove problemi. I problemi sono correlati allo sviluppo di applicazioni distribuite, ad esempio modelli di dati frammentati e indipendenti; raggiungimento di una comunicazione resiliente tra microservizi; la necessità di coerenza finale; e complessità operativa. I microservizi introducono un livello di complessità superiore rispetto alle applicazioni monolitiche tradizionali.

A causa della complessità di un'architettura di microservizi, solo scenari specifici e determinati tipi di applicazioni sono adatti per le applicazioni basate su microservizi. Sono incluse applicazioni complesse e di grandi dimensioni con più sottosistemi in continua evoluzione. In questi casi, vale la pena investire in un'architettura software più complessa, per una maggiore agilità a lungo termine e una maggiore efficienza di manutenzione delle applicazioni. Per gli scenari meno complessi, tuttavia, può essere preferibile continuare con un approccio di applicazione monolitica o approcci più semplici a più livelli.

Come nota finale, anche al rischio di essere ripetitivo di questo concetto, non è consigliabile usare microservizi nelle applicazioni come "tutto o niente". È possibile estendere e sviluppare applicazioni monolitiche esistenti aggiungendo nuovi scenari piccoli basati sui microservizi. Non è necessario iniziare da zero per iniziare a usare un approccio di architettura di microservizi. Si consiglia infatti di evolvere dall'uso di un'applicazione monolitica o a più livelli esistente aggiungendo nuovi scenari. Infine, è possibile suddividere l'applicazione in componenti autonomi o microservizi. È possibile iniziare a sviluppare le applicazioni monolitiche in una direzione di microservizi, passo per passo.

In ogni caso, la parte restante di questa guida è incentrata principalmente su "nessuna app basata su microservizi" perché questa guida è destinata principalmente alla modernizzazione di app esistenti che in genere hanno architetture monolitiche o a più livelli.

> [!div class="step-by-step"]
> [Precedente](microsoft-technologies-in-cloud-optimized-applications.md)
> [Successivo](deploy-existing-net-apps-as-windows-containers.md)
