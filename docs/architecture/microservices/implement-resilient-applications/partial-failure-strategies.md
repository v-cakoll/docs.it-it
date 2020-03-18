---
title: Strategie di gestione degli errori parziali
description: Informazioni su diverse strategie per la gestione normale degli errori parziali.
ms.date: 10/16/2018
ms.openlocfilehash: e96fe99ab44b924460e01abaad30aa3e2432117a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674508"
---
# <a name="strategies-to-handle-partial-failure"></a>Strategie di gestione degli errori parziali

Le strategie di gestione degli errori parziali sono le seguenti.

**Usare la comunicazione asincrona, ad esempio la comunicazione basata su messaggi, tra i microservizi interni**. È consigliabile evitare di creare lunghe catene di chiamate HTTP sincrone tra i microservizi interni, perché questa configurazione non corretta finirà per diventare la causa principale di interruzioni di servizio prolungate. Al contrario è consigliabile usare solo la comunicazione asincrona (basata su messaggi) tra i microservizi interni dopo il ciclo di richiesta/risposta iniziale, salvo per le comunicazioni front-end tra le applicazioni client e il primo livello dei microservizi o i gateway API con granularità fine. Le architetture di coerenza finale e basate su eventi consentiranno di ridurre al minimo l'effetto domino. Questi approcci impongono un livello di autonomia dei microservizi più elevato e consentono di prevenire il problema specificato.

**Usare i tentativi con backoff incrementale**. Questa tecnica permette di evitare errori brevi e intermittenti tramite la ripetizione delle chiamate per un determinato numero di volte, nel caso in cui il servizio non sia stato disponibile per un breve periodo di tempo. Questa situazione può essere causata da problemi di rete intermittenti o quando un microservizio/contenitore viene spostato in un altro nodo del cluster. Tuttavia, se i tentativi non sono progettati correttamente con interruttori di circuito, l'effetto domino può aggravarsi fino a generare un errore di tipo [Denial of Service (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).

**Usare i timeout di rete**. In generale, i client devono essere progettati in modo da non bloccarsi a tempo indefinito e per usare sempre i timeout durante l'attesa per una risposta. L'uso dei timeout garantisce che le risorse non rimangano bloccate per un periodo di tempo indefinito.

**Usare lo schema Circuit Breaker**. Con questo approccio, il processo client tiene traccia del numero di richieste non riuscite. Se la frequenza di errori supera un limite configurato, si attiva un "interruttore di circuito" affinché i tentativi successivi abbiano immediatamente esito negativo. Se un numero elevato di richieste non riesce, significa che il servizio non è disponibile e che l'invio di richieste è inutile. Dopo un periodo di timeout, il client deve riprovare e, se le nuove richieste hanno esito positivo, chiudere l'interruttore.

**Fornire fallback**. Con questo approccio, il processo client esegue la logica di fallback in caso di esito negativo di una richiesta, ad esempio restituendo i dati memorizzati nella cache o un valore predefinito. Questo approccio è adatto alle query, ma risulta più complesso per gli aggiornamenti o i comandi.

**Limitare il numero di richieste in coda**. I client devono inoltre imporre una soglia massima per il numero di richieste in sospeso che un microservizio può inviare a un determinato servizio. Se il limite è stato raggiunto, è in genere inutile inviare richieste aggiuntive e questi tentativi avranno immediatamente esito negativo. In termini di implementazione, è possibile usare i criteri [Bulkhead Isolation](https://github.com/App-vNext/Polly/wiki/Bulkhead) (isolamento a scomparti) in Polly per soddisfare questo requisito. Questo approccio rappresenta semplicemente una limitazione della parallelizzazione con <xref:System.Threading.SemaphoreSlim> come implementazione. Consente anche la creazione di una "coda" all'esterno dello scomparto. È possibile rimuovere il carico in eccesso anche prima dell'esecuzione, ad esempio se la capacità è considerata piena. La risposta a determinati scenari di errori risulta quindi più veloce rispetto a quella di un interruttore di circuito, dal momento che l'interruttore rimane in attesa degli errori. L'oggetto BulkheadPolicy in [Polly](http://www.thepollyproject.org/) visualizza il livello di riempimento dello scomparto e della coda, offre eventi di overflow e può anche essere usato per aumentare automaticamente il numero di istanze.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Modelli di resilienzaResiliency patterns**\
  [https://docs.microsoft.com/azure/architecture/patterns/category/resiliency](/azure/architecture/patterns/category/resiliency)

- **Aggiunta di resilienza e ottimizzazione delle prestazioniAdding Resilience and Optimizing Performance**\
  <https://docs.microsoft.com/previous-versions/msp-n-p/jj591574(v=pandp.10)>

- **Paratia.** Repository GitHub. Implementazione con i criteri Polly.\
  <https://github.com/App-vNext/Polly/wiki/Bulkhead>

- **Progettazione di applicazioni resilienti per AzureDesigning resilient applications for Azure**\
  [https://docs.microsoft.com/azure/architecture/resiliency/](/azure/architecture/resiliency/)

- **Gestione temporanea degli errori**\
  [https://docs.microsoft.com/azure/architecture/best-practices/transient-faults](/azure/architecture/best-practices/transient-faults)

>[!div class="step-by-step"]
>[Successivo](handle-partial-failure.md)
>[precedente](implement-retries-exponential-backoff.md)
