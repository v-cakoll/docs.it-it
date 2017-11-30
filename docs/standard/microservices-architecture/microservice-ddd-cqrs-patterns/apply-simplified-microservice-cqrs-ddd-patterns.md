---
title: L'applicazione di modelli CQRS e DDD semplificate in un microservizio.
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | L'applicazione di modelli CQRS e DDD semplificate in un microservizio.
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 99fd7ce32039742e23f8e01aa4c33cddd7a9f698
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="applying-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>L'applicazione di modelli CQRS e DDD semplificate in un microservizio.

CQRS è un modello architetturale che separa i modelli per la lettura e scrittura dei dati. Il termine correlato [comando Query separazione (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html) è stato originariamente definito da Bertrand Meyer nel suo libro *la costruzione dell'oggetto orientato alla Software*. L'idea di base è che è possibile dividere le operazioni del sistema in due categorie nettamente separate:

-   Esegue una query. Questi restituiscono un risultato e non modificare lo stato del sistema e che sono liberi di effetti collaterali.

-   I comandi. Questi modificare lo stato di un sistema.

CQS è un concetto semplice, ovvero è sui metodi all'interno dell'oggetto stesso da query o comandi. Ogni metodo restituisce lo stato oppure viene modificato lo stato, ma non entrambi. Anche un oggetto modello di repository singolo può essere conformi con CQS. CQS può essere considerato un principio fondamentale di CQRS.

[Comando e Query Responsibility Segregation (CQRS)](https://martinfowler.com/bliki/CQRS.html) introdotto da Greg Young e fortemente innalzata di livello dal Udi Dahan e altri. È basato sul principio CQS, sebbene più dettagliata. Può essere considerato un modello basato sui comandi e gli eventi e facoltativamente nei messaggi asincroni. In molti casi, CQRS è correlata a scenari più avanzati, ad esempio disporre di un database diverso per operazioni di lettura (query) anziché per operazioni di scrittura (aggiornamenti). Inoltre, è possibile implementare un sistema CQRS più evoluto [evento-Sourcing (ES)](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/) per il database di aggiornamenti, pertanto è sarebbe archiviare solo gli eventi nel modello di dominio anziché archiviare i dati dello stato corrente. Tuttavia, non si tratta dell'approccio utilizzato in questa Guida. viene usato l'approccio più semplice CQRS, che include solo le query la separazione dei comandi.

L'aspetto di separazione di CQRS avviene mediante il raggruppamento di operazioni di query in un livello e i comandi in un altro livello. Ogni livello è presente un modello di dati (si noti che è ad esempio modello, non necessariamente un database diverso) e viene compilato utilizzando il proprio combinazione di modelli e le tecnologie. Ancora più importante, i due livelli possono essere entro lo stesso livello o microservizio, come illustrato nell'esempio (ordinamento microservizio) utilizzato per questa Guida. O potrebbe essere implementati in diversi microservizi o processi in modo ottimizzati e scalabilità separatamente senza influire su un altro.

CQRS, significa creare due oggetti per un'operazione di lettura/scrittura in cui in altri contesti è presente. Esistono motivi per cui dispone di un database denormalizzato letture, che è possibile acquisire informazioni nella documentazione CQRS più avanzata. Ma non vengono utilizzati in questo caso, un approccio in cui l'obiettivo è per una maggiore flessibilità nelle query invece di limitare le query con vincoli dai modelli DDD come funzioni di aggregazione.

Un esempio di questo tipo di servizio è l'ordinamento microservizio dall'applicazione di riferimento eShopOnContainers. Il servizio implementa un microservizio in base a un approccio CQRS semplificato. Usa una singola origine dati o database, ma due modelli logici più modelli DDD per il dominio transazionale, come illustrato nella figura 9-2.

![](./media/image2.png)

**Figura 9-2**. Semplificato basato su CQRS e DDD microservizio

Il livello di applicazione può essere la stessa interfaccia API di Web. In questo caso l'aspetto importante è che il microservizio è suddiviso le query e ViewModel (modelli di data particolare creati per le applicazioni client) dal modello di dominio, i comandi e le transazioni in cui il modello CQRS. Questo approccio consente di mantenere le query indipendente da restrizioni e i vincoli provenienti da modelli DDD che servono esclusivamente per transazioni e gli aggiornamenti, come illustrato nelle sezioni successive.


>[!div class="step-by-step"]
[Precedente] [Avanti] (eshoponcontainers cqrs-ggg microservice.md) (index.md)
