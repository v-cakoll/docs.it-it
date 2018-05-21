---
title: Strategie di gestione degli errori parziali
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Strategie di gestione degli errori parziali
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: f1b2b59af96bf28035eeb32eb15eaa4105677cf4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="strategies-for-handling-partial-failure"></a>Strategie di gestione degli errori parziali

Le strategie di gestione degli errori parziali sono le seguenti.

**Usare la comunicazione asincrona, ad esempio la comunicazione basata su messaggi, tra i microservizi interni**. È consigliabile evitare di creare lunghe catene di chiamate HTTP sincrone tra i microservizi perché questa progettazione non corretta diventerà alla fine la causa principale delle interruzioni di servizio. Al contrario, ad eccezione delle comunicazioni front-end tra le applicazioni client e il primo livello dei microservizi o i gateway API con granularità fine, è consigliabile usare solo la comunicazione asincrona (basata su messaggi) immediatamente al termine del ciclo di richiesta/risposta iniziale, tra i microservizi interni. Le architetture di coerenza finale e basate su eventi consentiranno di ridurre al minimo l'effetto domino. Questi approcci impongono un livello di autonomia dei microservizi più elevato e consentono di prevenire il problema specificato.

**Usare i tentativi con backoff incrementale**. Questa tecnica permette di evitare errori brevi e intermittenti tramite la ripetizione delle chiamate per un determinato numero di volte, nel caso in cui il servizio non sia stato disponibile per un breve periodo di tempo. Questa situazione può essere causata da problemi di rete intermittenti o quando un microservizio/contenitore viene spostato in un altro nodo del cluster. Tuttavia, se i tentativi non sono progettati correttamente con interruttori di circuito, l'effetto domino può aggravarsi fino a generare un errore di tipo [Denial of Service (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).

**Usare i timeout di rete**. In generale, i client devono essere progettati in modo da non bloccarsi a tempo indefinito e per usare sempre i timeout durante l'attesa per una risposta. L'uso dei timeout garantisce che le risorse non rimangano bloccate per un periodo di tempo indefinito.

**Usare lo schema Circuit Breaker**. Con questo approccio, il processo client tiene traccia del numero di richieste non riuscite. Se la frequenza di errori supera un limite configurato, si attiva un "interruttore di circuito" affinché i tentativi successivi abbiano immediatamente esito negativo. Se un numero elevato di richieste presenta errori, il servizio potrebbe non essere disponibile e risulta inutile inviare altre richieste. Trascorso il periodo di timeout, il client deve riprovare e, se le nuove richieste hanno esito positivo, l'interruttore di circuito si chiude.

**Fornire fallback**. Con questo approccio, il processo client esegue la logica di fallback in caso di esito negativo di una richiesta, ad esempio restituendo i dati memorizzati nella cache o un valore predefinito. Questo approccio è adatto alle query, ma risulta più complesso per gli aggiornamenti o i comandi.

**Limitare il numero di richieste in coda**. I client devono inoltre imporre una soglia massima per il numero di richieste in sospeso che un microservizio può inviare a un determinato servizio. Se il limite è stato raggiunto, è inutile inviare richieste aggiuntive, quindi questi tentativi devono avere immediatamente esito negativo. In termini di implementazione, è possibile usare i criteri [Bulkhead Isolation](https://github.com/App-vNext/Polly/wiki/Bulkhead) (isolamento a scomparti) in Polly per soddisfare questo requisito. Questo approccio rappresenta semplicemente una limitazione della parallelizzazione con <xref:System.Threading.SemaphoreSlim> come implementazione. Consente anche la creazione di una "coda" all'esterno dello scomparto. È possibile rimuovere il carico in eccesso anche prima dell'esecuzione, ad esempio se la capacità è considerata piena. La risposta a determinati scenari di errori risulta quindi più veloce rispetto a quella di un interruttore di circuito, dal momento che l'interruttore rimane in attesa degli errori. L'oggetto BulkheadPolicy in Polly mostra il livello di riempimento di scomparto e coda, offre eventi di overflow e può anche essere usato per aumentare automaticamente il numero di istanze.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Modelli di resilienza**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Aggiunta di resilienza e ottimizzazione delle prestazioni**
    [*https://msdn.microsoft.com/library/jj591574.aspx*](https://msdn.microsoft.com/library/jj591574.aspx)

-   **Bulkhead.** Repository GitHub. Implementazione con i criteri Polly.\
    [*https://github.com/App-vNext/Polly/wiki/Bulkhead*](https://github.com/App-vNext/Polly/wiki/Bulkhead)

-   **Progettazione di applicazioni resilienti per Azure**
    [*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)

-   **Gestione degli errori temporanei**
    <https://docs.microsoft.com/azure/architecture/best-practices/transient-faults>


>[!div class="step-by-step"]
[Indietro] (handle-partial-failure.md) [Avanti] (implement-retries-exponential-backoff.md)
