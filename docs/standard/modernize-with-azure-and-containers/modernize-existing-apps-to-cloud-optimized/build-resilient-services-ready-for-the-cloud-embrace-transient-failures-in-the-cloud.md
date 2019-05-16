---
title: Creare servizi resilienti pronti per il cloud. Gestire gli errori temporanei nel cloud
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Creare servizi resilienti pronti per il cloud. Gestire gli errori temporanei nel cloud
ms.date: 04/30/2018
ms.openlocfilehash: ca5d5e0c3af772ac52a02894c96889c776cf7d48
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643730"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Creare servizi resilienti pronti per il cloud: Gestire gli errori temporanei nel cloud

La resilienza è la capacità di correggere gli errori e continuare a funzionare. La resilienza non è presente su come evitare errori, ma accettare il fatto che si verificheranno errori e quindi rispondere in modo da evitare tempi di inattività o perdita di dati. L'obiettivo della resilienza è riportare l'applicazione in uno stato pienamente operativo dopo un errore.

L'applicazione è pronta per il cloud quando, come minimo, implementa un modello basato su software di resilienza, anziché un modello basato su hardware. L'applicazione cloud deve cogliere gli errori parziali che sicuramente si. Progetta o parzialmente il refactoring dell'applicazione per ottenere la resilienza previsto degli errori parziali. Deve essere progettata per gestire errori parziali, ad esempio interruzioni di rete temporanei e i nodi o macchine virtuali nel cloud di un arresto anomalo. Anche i contenitori da spostare in un nodo diverso all'interno di un cluster dell'agente di orchestrazione possono causare brevi errori intermittenti nell'applicazione.

## <a name="handling-partial-failure"></a>Gestione degli errori parziali

In un'applicazione basata su cloud, è presente un onnipresente rischio di errori parziali. Ad esempio, un'istanza del singolo sito Web o in un contenitore potrebbe non riuscire oppure potrebbe essere non disponibile o non risponda per breve tempo. In alternativa, una singola macchina virtuale o server potrebbe arrestarsi in modo anomalo.

Poiché i client e servizi sono processi separati, un servizio potrebbe non essere in grado di rispondere tempestivamente a una richiesta del client. Il servizio potrebbe essere soggetto a overload e rispondere molto lentamente alle richieste, o potrebbe non essere accessibile per un breve periodo di tempo a causa di problemi di rete.

Ad esempio, prendere in considerazione un'applicazione monolitica di .NET che accede a un database nel Database SQL di Azure. Se il database SQL di Azure o qualsiasi altro servizio di terze parti non risponde per una breve tempo (un database SQL di Azure potrebbe essere spostato in un server o un altro nodo e da non rispondere per pochi secondi), quando l'utente tenta di eseguire qualsiasi azione, l'applicazione potrebbe bloccarsi e Mostra w un'eccezione nello stesso momento.

Uno scenario simile può verificarsi in un'app che utilizza i servizi HTTP. La rete o il servizio stesso non sia disponibile nel cloud in caso di errore breve e temporaneo.

Un'applicazione resiliente simile a quello illustrato nella figura 4-9 deve implementare tecniche quali "tentativi con backoff esponenziale" per assegnare all'applicazione la possibilità di gestire gli errori temporanei nelle risorse. È anche consigliabile usare "gli interruttori di circuito" nelle applicazioni. Un interruttore di circuito si arresta un'applicazione tenti di accedere a una risorsa quando è effettivamente un errore a lungo termine. Usando un interruttore di circuito, l'applicazione evita provocato un attacco denial of service a se stesso.

![Errori parziali gestiti da tentativi con backoff esponenziale](./media/image9.png)

> **Figura 4-9.** Errori parziali gestiti da tentativi con backoff esponenziale

È possibile usare queste tecniche in risorse HTTP sia in risorse del database. Nella figura 4-9, l'applicazione si basa su un'architettura a 3 livelli, pertanto è necessario queste tecniche a livello di servizi (HTTP) e a livello di livello dati (TCP). In un'applicazione monolitica che utilizza solo un livello di singola app, oltre che il database (senza servizi aggiuntivi o microservizi), la gestione degli errori temporanei a livello di connessione di database potrebbe essere sufficiente. In questo scenario, è necessaria solo una particolare configurazione della connessione di database.

Quando si implementa resiliente delle comunicazioni che accedono al database, a seconda della versione di .NET si usa, può essere semplice (ad esempio, [con Entity Framework 6 o versione successiva](/ef/ef6/fundamentals/connection-resiliency/retry-logic). È sufficiente per configurare la connessione di database). Oppure potrebbe essere necessario usare librerie aggiuntive, ad esempio la [Transient Fault Handling Application Block](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (per le versioni precedenti di .NET), o anche implementare una libreria personalizzata.

Quando si implementano tentativi HTTP e gli interruttori di circuito, la raccomandazione per .NET consiste nell'usare la [Polly](https://github.com/App-vNext/Polly) libreria che ha come destinazione .NET Framework 4.0, .NET Framework 4.5 e .NET Standard 1.1, che include il supporto di .NET Core.

Per informazioni su come implementare strategie di gestione degli errori parziali nel cloud, vedere i seguenti riferimenti.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Implementazione della comunicazione resiliente per gestire errori parziali**

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

- **Entity Framework connessione tentativi e la resilienza per la logica (versione 6 e versioni successive)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **Il blocco applicazione per la gestione degli errori temporanei**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **Libreria Polly per la comunicazione HTTP resiliente**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
>[Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[Successivo](modernize-your-apps-with-monitoring-and-telemetry.md)
