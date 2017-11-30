---
title: Approcci CQRS l'applicazione e CQS in un microservizio DDD in eShopOnContainers
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Approcci CQRS l'applicazione e CQS in un microservizio DDD in eShopOnContainers
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a2c4429a75ca47d4fbcde868b95e76bc65ea2bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a>Approcci CQRS l'applicazione e CQS in un microservizio DDD in eShopOnContainers

La progettazione dell'ordinamento microservizio l'applicazione di riferimento eShopOnContainers si basa sui principi CQRS. Tuttavia, utilizza l'approccio più semplice, che è sufficiente che separa le query dei comandi e utilizzando lo stesso database per le azioni.

Le tracce di tali modelli e in questo caso, l'aspetto importante sono che le query sono idempotenti: indipendentemente da quante volte si esegue un sistema, lo stato del sistema di una query non verranno modificato è anche possibile usare un modello di dati diverso "lettura" più la logica transazionale "scrittura" modello di dominio, anche se l'ordinamento microservizi utilizza lo stesso database. Pertanto, questo è un approccio CQRS semplificato.

D'altra parte, comandi, attivano le transazioni e gli aggiornamenti dei dati, modificano lo stato del sistema. Con i comandi, è necessario prestare attenzione quando relative complessità e le regole di business in continua evoluzione. Questa è la posizione in cui si desidera applicare le tecniche DDD per disporre di un sistema modellato meglio.

I modelli DDD presentati in questa Guida non devono essere applicati universalmente. Introducono vincoli alla progettazione. Tali vincoli offrono vantaggi, ad esempio una qualità più elevata nel tempo, soprattutto in comandi e altro codice che modifica lo stato del sistema. Tuttavia, tali vincoli aggiungono complessità con meno vantaggi per la lettura e di eseguire query sui dati.

Un modello di questo tipo è il modello di aggregazione, che verranno esaminati più nelle sezioni successive. In breve, nel modello di aggregazione, si considerano molti oggetti di dominio come una singola unità come risultato la relazione del dominio. È possibile che non sempre vantaggi da questo modello di query. è possibile aumentare la complessità della logica di query. Per le query di sola lettura, non è possibile ottenere i vantaggi di gestione di più oggetti come una singola funzione di aggregazione. Si ottiene solo la complessità.

Come illustrato nella figura 9-2, è consigliabile in base a modelli DDD solo nell'area transazionale, aggiornamenti del microservizio (vale a dire come attivata da comandi). Le query possono seguire un approccio più semplice e devono essere separate da comandi, adotta un approccio CQRS.

Per implementare il lato"query", è possibile scegliere tra molti approcci, tra l'autentico ORM come Core EF AutoMapper proiezioni o stored procedure, viste, viste materializzate una ORM micro.

In questa Guida e in eShopOnContainers (in particolare l'ordinamento microservizio) è stato scelto di implementare semplici query utilizzando un micro ORM come [Dapper](https://github.com/StackExchange/dapper-dot-net). Ciò consente di implementare qualsiasi query in base alle istruzioni SQL per ottenere prestazioni ottimali, grazie a un framework chiaro con un overhead minimo.

Si noti che, quando si utilizza questo approccio, tutti gli aggiornamenti al modello che influiscono su come le entità vengono resi persistenti in un database SQL necessario anche aggiornamenti separati in query SQL utilizzate da Dapper o eventuali altri approcci (non EF) separati per l'esecuzione di query.

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a>I modelli CQRS e DDD non sono le architetture di livello superiore

È importante comprendere che CQRS e la maggior parte dei modelli DDD (come livelli DDD o un modello di dominio con funzioni di aggregazione) non sono gli stili dell'architettura, ma solo i modelli di architettura. Microservizi, SOA e architettura basata su eventi (EDA) sono esempi di stili dell'architettura. Descrivono un sistema di molti componenti, ad esempio microservizi molti. Modelli di CQRS e DDD descrivono un aspetto all'interno di un unico sistema o un componente. In questo caso, oggetto all'interno di un microservizio.

Contesti diversi delimitata (BCs) verranno impiegati modelli diversi. Responsabilità diverse e che comporta diverse soluzioni. È la pena sottolineare che imporre lo stesso modello che Everywhere provoca un errore. Non utilizzare modelli di CQRS e DDD ovunque. Molti dei sottosistemi, BCs o microservizi sono più semplici e possono essere implementato più facilmente utilizzando servizi CRUD semplici o un altro approccio.

Vi è solo un'applicazione architettura: l'architettura dell'applicazione end-to-end o di sistema si progettano (ad esempio, l'architettura di microservizi). Tuttavia, la struttura di ogni contesto delimitata o microservizio all'interno di tale applicazione riflette il proprio compromessi e le decisioni di progettazione interna a livello di modelli di architettura. Non tentare di applicare gli stessi dell'architettura modelli come CQRS o DDD ovunque.

####  <a name="additional-resources"></a>Risorse aggiuntive

-   **Martin Fowler. CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)

-   **Greg Young. Visual Studio CQS. CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)

-   **Greg Young. Documenti CQRS**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)

-   **Greg Young. Attività di CQRS, basato su interfacce utente e determinazione dell'origine evento**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)

-   **udi Dahan. È stato chiarito CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **Evento-Sourcing (ES)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)


>[!div class="step-by-step"]
[Precedente] [Avanti] (cqrs-microservizio-reads.md) (apply-simplified-microservice-cqrs-ddd-patterns.md)
