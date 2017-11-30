---
title: Strategie di gestione degli errori parziali
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Strategie di gestione degli errori parziali
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ff3bed530b13a9b1822c7cccf5a4d47df6fc6239
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="strategies-for-handling-partial-failure"></a>Strategie di gestione degli errori parziali

Di seguito sono elencate le strategie per affrontare gli errori parziali.

**Usare la comunicazione asincrona (ad esempio, comunicazione basata su messaggi) tra microservizi interno**. È consigliabile non creare lunghe catene di chiamate HTTP sincrone tra l'interno microservizi perché tale progettazione corretta infine diventerà la causa principale di interruzioni non valide. Al contrario, ad eccezione delle comunicazioni front-end tra le applicazioni client e il primo livello di microservizi o granulari per le API gateway, è consigliabile usare solo (basata su messaggi) comunicazione asincrona di una volta dopo la richiesta iniziale / ciclo di risposta, attraverso il microservizi interno. Architetture di basato su eventi e la coerenza eventuale consente di ridurre gli effetti ripple. Questi approcci, applicano un livello superiore di autonomia microservizio e pertanto prevenire il problema indicato di seguito.

**Utilizzare i tentativi con backoff esponenziale**. Questa tecnica consente di evitare breve e verificati errori intermittenti eseguendo chiamate Riprova a eseguire un determinato numero di volte, nel caso in cui il servizio non era disponibile solo per un breve periodo di tempo. Questa situazione può verificarsi a causa di problemi intermittenti della rete o quando un microservizio/contenitore viene spostato su un nodo in un cluster diverso. Tuttavia, se questi tentativi non sono progettati in modo corretto con circuito, è possibile aggravare gli effetti di ripple, infine anche che provocano un [Denial of Service (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).

**Risolvere i timeout di rete**. In generale, i client devono essere progettati non bloccare in modo indefinito e di utilizzare sempre i timeout durante l'attesa di una risposta. Utilizzo di timeout assicura che le risorse non sono mai associate per un periodo illimitato.

**Utilizzare il modello di interruttore**. In questo approccio, il processo client tiene traccia del numero di richieste non riuscite. Se la frequenza degli errori supera un limite configurato, un trip "interruttore" in modo che i tentativi non riescono immediatamente. (Se non riesce, un numero elevato di richieste che suggerisce il servizio è disponibile e che l'invio delle richieste è inutile.) Dopo un periodo di timeout, il client deve ripetere l'operazione e, se le nuove richieste hanno esito positivo, chiudere l'interruttore.

**Fornire fallback**. In questo approccio, il processo client esegue una logica di fallback quando una richiesta ha esito negativo, ad esempio la restituzione di dati memorizzati nella cache o un valore predefinito. Questo è un approccio adatto per le query e si è più complesso per gli aggiornamenti o i comandi.

**Limitare il numero di richieste in coda**. I client inoltre devono imporre un limite superiore al numero di richieste in attesa che un microservizio client può inviare a un particolare servizio. Se è stato raggiunto il limite, è probabilmente inutile effettuare richieste aggiuntive e i tentativi dovrebbero generare immediatamente un errore. In termini di implementazione, il Polly [isolamento ponte](https://github.com/App-vNext/Polly/wiki/Bulkhead) criteri possono essere usato per soddisfare questo requisito. Questo approccio è essenzialmente una limitazione di parallelizzazione con [SemaphoreSlim](https://docs.microsoft.com/dotnet/api/system.threading.semaphoreslim?view=netcore-1.1) dell'implementazione. Consente inoltre di una "coda" di fuori di ponte. È possibile lasci eccessivo carico anche prima dell'esecuzione in modo proattivo (ad esempio, perché la capacità viene considerata completa). In questo modo la risposta a determinati scenari di errore più velocemente rispetto a un interruttore, poiché l'interruttore è in attesa per gli errori. L'oggetto BulkheadPolicy in Polly espone il livello di riempimento di ponte e coda sono offerte eventi in caso di overflow così utilizzabile anche per favorire la scalabilità orizzontale automatica.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Modelli di resilienza**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Aggiunta di resilienza e ottimizzazione delle prestazioni**
    [*https://msdn.microsoft.com/en-us/library/jj591574.aspx*](https://msdn.microsoft.com/en-us/library/jj591574.aspx)

-   **Ponte.** Repository di GitHub. Implementazione con criteri Polly. \
    [*https://github.com/App-vNext/Polly/Wiki/Bulkhead*](https://github.com/App-vNext/Polly/wiki/Bulkhead)

-   **Progettazione di applicazioni Azure resilienti**
    [*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)

-   **Gestione degli errori temporanei**
    <https://docs.microsoft.com/azure/architecture/best-practices/transient-faults>


>[!div class="step-by-step"]
[Precedente] (handle-parziale-failure.md) [Avanti] (implementare-tentativi-esponenziale-backoff.md)
