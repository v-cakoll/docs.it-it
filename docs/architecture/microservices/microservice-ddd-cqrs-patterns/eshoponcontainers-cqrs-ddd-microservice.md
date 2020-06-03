---
title: Applicazione degli approcci CQRS e CQS in un microservizio DDD in eShopOnContainers
description: Architettura di microservizi .NET per applicazioni .NET incluse in contenitori | Modalità di implementazione di CQRS nel microservizio degli ordini in eShopOnContainers.
ms.date: 03/03/2020
ms.openlocfilehash: 2916df596a6d0f887411f3ef0074aed395ef58ba
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306942"
---
# <a name="apply-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a>Applicare gli approcci CQRS e CQS in un microservizio DDD in eShopOnContainers

La progettazione del microservizio per gli ordini nell'applicazione di riferimento eShopOnContainers è basata sui principi del modello CQRS. Tuttavia, usa l'approccio più semplice che consiste nella separazione delle query dai comandi e nell'uso dello stesso database per entrambe le azioni.

L'aspetto essenziale di tali modelli e, in questo caso, il punto importante è che le query sono idempotenti: indipendentemente da quante volte si esegue una query in un sistema, lo stato del sistema non viene modificato. In altre parole, le query non hanno effetti collaterali.

Pertanto, è possibile utilizzare un modello di dati "Reads" diverso rispetto al modello di dominio "Scritture" della logica transazionale, anche se i microservizi degli ordini utilizzano lo stesso database. Ecco perché questo è un approccio CQRS semplificato.

D'altra parte, lo stato dei comandi che attivano le transazioni e gli aggiornamenti dei dati cambia nel sistema. Con i comandi, occorre prestare attenzione quando si affrontano scenari complessi e regole aziendali in continua evoluzione. Ecco perché le tecniche di progettazione DDD consentono di ottenere un sistema con una modellazione ottimale.

Gli schemi DDD presentati in questa guida non devono essere applicati a livello universale, perché introducono vincoli nella progettazione. Questi vincoli offrono vantaggi come una migliore qualità nel tempo, in particolare per i comandi e il codice che modifica lo stato del sistema. Tuttavia, questi vincoli aggiungono complessità con vantaggi ridotti per la lettura e le query sui dati.

Uno di questi schemi è lo schema Aggregate che verrà esaminato più in dettaglio nelle sezioni successive. In breve, nello schema Aggregate, gli oggetti di dominio vengono considerati come una singola unità in virtù della relativa relazione nel dominio. Non sempre questo schema genera vantaggi nelle query, in quanto può aumentare la complessità della logica di query. Per le query di sola lettura non è vantaggioso considerare più oggetti come una singola aggregazione. Aumenta solo la complessità.

Come illustrato nella figura 7-2 della sezione precedente, questa guida suggerisce l'uso di modelli DDD solo nell'area transazionale/degli aggiornamenti del microservizio, ovvero come attivato dai comandi. Le query possono seguire un approccio più semplice e devono essere separate dai comandi, secondo quanto previsto dall'approccio CQRS.

Per implementare il "lato query", è possibile scegliere tra molti approcci, dall'ORM completo, ad esempio EF Core, le proiezioni di automapping, le stored procedure, le visualizzazioni, le visualizzazioni materializzate o un micro ORM.

In questa guida e in eShopOnContainers, in particolare nel microservizio degli ordini, è stato scelto di implementare query lineari tramite un micro ORM come [Dapper](https://github.com/StackExchange/dapper-dot-net). In questo modo è possibile implementare qualsiasi query basata su istruzioni SQL per ottenere prestazioni ottimali, grazie a un framework leggero con un sovraccarico ridotto.

Quando si usa questo approccio, eventuali aggiornamenti al modello che influiscano sul modo in cui le entità vengono rese disponibili in un database SQL devono anche eseguire aggiornamenti distinti per le query SQL usate da elegante o da altri approcci distinti (non EF) per eseguire query.

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a>Gli schemi CQRS e DDD non sono architetture di primo livello

È importante comprendere che gli schemi CQRS e la maggior parte degli schemi DDD, come i livelli DDD o un modello di dominio con aggregazioni, non sono stili architetturali, ma solo schemi di architetture. I microservizi, l'architettura orientata ai servizi (SOA) e l'architettura basata su eventi (EDA) sono esempi di stili architetturali. Descrivono un sistema costituito da molti componenti, ad esempio vari microservizi. Gli schemi CQRS e DDD descrivono un aspetto all'interno di un singolo sistema o componente. In questo caso, all'interno di un microservizio.

Diversi contesti delimitati useranno schemi differenti. Poiché hanno responsabilità diverse, verranno impiegate soluzioni differenziate. Tenere presente che forzare lo stesso schema ovunque può generare errori. Non usare gli schemi CQRS e DDD ovunque. Molti sottosistemi, contesti delimitati o microservizi sono più semplici e possono essere implementati facilmente con servizi CRUD o altri approcci.

Esiste una sola architettura dell'applicazione: l'architettura del sistema o dell'applicazione end-to-end che si sta progettando, ad esempio l'architettura di microservizi. Tuttavia la progettazione di ogni contesto delimitato o microservizio all'interno dell'applicazione riflette i compromessi e le decisioni di progettazione interne al livello degli schemi di architettura. Non provare ad applicare gli stessi schemi architetturali, come CQRS o DDD, ovunque.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Martin Fowler. CQRS** \
  <https://martinfowler.com/bliki/CQRS.html>

- **Greg Young. Documenti CQRS** \
  <https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf>

- **UDI. CQRS chiarificato** \
  <https://udidahan.com/2009/12/09/clarified-cqrs/>

>[!div class="step-by-step"]
>[Precedente](apply-simplified-microservice-cqrs-ddd-patterns.md) 
> [Avanti](cqrs-microservice-reads.md)
