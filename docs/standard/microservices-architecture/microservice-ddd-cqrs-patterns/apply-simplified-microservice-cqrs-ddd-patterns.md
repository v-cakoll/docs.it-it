---
title: Applicazione di schemi CQRS e DDD semplificati in un microservizio
description: Architettura dei microservizi .NET per le applicazioni .NET in contenitori | Applicazione di schemi CQRS e DDD semplificati in un microservizio
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5369ff73a0614170b220177f1e5d388483ca19f8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="applying-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>Applicazione di schemi CQRS e DDD semplificati in un microservizio

CQRS è uno schema architetturale che separa i modelli per la lettura e la scrittura dei dati. Il termine correlato [Command Query Separation (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html) è stato originariamente definito da Bertrand Meyer nel suo libro *Object Oriented Software Construction*. L'idea di base è che è possibile dividere le operazioni di un sistema in due categorie nettamente distinte:

-   Query. Restituiscono un risultato, non modificano lo stato del sistema e sono prive di effetti collaterali.

-   Comandi. Modificano lo stato di un sistema.

CQS è un concetto semplice: riguarda i metodi all'interno di un oggetto, che si tratti di query o comandi. Ogni metodo restituisce lo stato oppure modifica lo stato, ma non esegue entrambe le operazioni. Anche un singolo oggetto di schema di repository può essere conforme a CQS. CQS può essere considerato un principio fondamentale per CQRS.

[Command and Query Responsibility Segregation (CQRS)](https://martinfowler.com/bliki/CQRS.html) è stato introdotto da Greg Young e fortemente promosso da Udi Dahan e altri esperti. È basato sul principio CQS, sebbene sia più dettagliato. Può essere considerato uno schema basato sui comandi e sugli eventi, oltre che facoltativamente sui messaggi asincroni. In molti casi, CQRS è correlato a scenari più avanzati, come l'uso di un database per le operazioni di lettura (query) diverso da quello per le operazioni di scrittura (aggiornamenti). Inoltre, un sistema CQRS più evoluto potrebbe implementare la [determinazione dell'origine degli eventi](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/) per il database degli aggiornamenti, consentendo di archiviare solo gli eventi nel modello di dominio, anziché archiviare i dati sullo stato corrente. In questa guida, tuttavia, non sarà applicato tale approccio. Verrà usato l'approccio più semplice a CQRS, che prevede solo la separazione delle query dai comandi.

L'aspetto di separazione di CQRS viene ottenuto mediante il raggruppamento delle operazioni di query in un livello e dei comandi in un altro livello. Ogni livello dispone di un proprio modello di dati (si noti che parliamo di modello, non necessariamente di un database diverso) e viene creato tramite una specifica combinazione di schemi e tecnologie. Cosa ancora più importante, i due livelli possono essere contenuti nello stesso livello o microservizio, come illustrato nell'esempio (microservizio per gli ordini) usato per questa guida. In alternativa, possono essere implementati in diversi microservizi o processi, in modo da poter essere ottimizzati e scalati in orizzontale separatamente senza influire l'uno sull'altro.

CQRS significa creare due oggetti per un'operazione di lettura/scrittura, dove in altri contesti ne è presente uno. Esistono diversi motivi per cui è consigliabile disporre di un database denormalizzato per le letture (informazioni in proposito sono disponibili nella documentazione più avanzata su CQRS). In questo caso, non useremo tale approccio, perché il nostro obiettivo è avere maggiore flessibilità nelle query invece di limitare le query con vincoli dagli schemi DDD come gli aggregati.

Un esempio di questo tipo di servizio è il microservizio per gli ordini dell'applicazione di riferimento eShopOnContainers. Questo servizio implementa un microservizio basato su un approccio CQRS semplificato. Usa una singola origine dati o un singolo database, ma due modelli logici, più schemi DDD per il dominio transazionale, come illustrato nella figura 9-2.

![](./media/image2.png)

**Figura 9-2**. Microservizio semplificato basato su CQRS e DDD

Il livello dell'applicazione può essere la stessa API Web. L'aspetto di progettazione importante a questo proposito è che il microservizio ha suddiviso le query e i ViewModel (modelli di dati creati appositamente per le applicazioni client) dai comandi, dal modello di dominio e dalle transazioni seguendo lo schema CQRS. Questo approccio mantiene le query indipendenti da restrizioni e vincoli provenienti da schemi DDD che sono applicabili esclusivamente per le transazioni e gli aggiornamenti, come descritto nelle sezioni successive.


>[!div class="step-by-step"]
[Indietro] (index.md) [Avanti] (eshoponcontainers-cqrs-ddd-microservice.md)
