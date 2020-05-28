---
title: Crea servizi resilienti pronti per il cloud. Gestire gli errori temporanei nel cloud
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Crea servizi resilienti pronti per il cloud. Gestire gli errori temporanei nel cloud
ms.date: 04/30/2018
ms.openlocfilehash: 899084ac00d9be0df47ef88c026f4e8c19722bb6
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144252"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Creare servizi resilienti pronti per il cloud: gestire gli errori temporanei nel cloud

La resilienza è la capacità di recupero da errori che consente un funzionamento continuativo. La resilienza non riguarda l'evitare gli errori, ma accettando il fatto che si verifichino errori e quindi rispondendo a tali errori in modo da evitare tempi di inattività o perdite di dati. L'obiettivo della resilienza è riportare l'applicazione in uno stato pienamente operativo dopo un errore.

L'applicazione è pronta per il cloud quando, come minimo, implementa un modello basato sul software di resilienza, anziché un modello basato su hardware. L'applicazione cloud deve accettare gli errori parziali che certamente si verificheranno. Progettare o eseguire il refactoring parziale dell'applicazione per ottenere la resilienza con errori parziali previsti. Deve essere progettato per gestire gli errori parziali, ad esempio interruzioni della rete transitoria e nodi, o arresti anomali delle macchine virtuali nel cloud. Anche i contenitori spostati in un nodo diverso all'interno di un cluster dell'agente di orchestrazione possono causare errori intermittenti all'interno dell'applicazione.

## <a name="handling-partial-failure"></a>Gestione degli errori parziali

In un'applicazione basata sul cloud è presente un rischio costante di errore parziale. Ad esempio, una singola istanza di sito Web o un contenitore potrebbe non riuscire o potrebbe non essere disponibile o non rispondere per un breve periodo di tempo. In alternativa, è possibile che una singola macchina virtuale o un server si arresti

Poiché i client e i servizi sono processi distinti, un servizio potrebbe non essere in grado di rispondere tempestivamente a una richiesta del client. Il servizio potrebbe essere sovraccarico e rispondere lentamente alle richieste oppure potrebbe non essere accessibile per un breve periodo di tempo a causa di problemi di rete.

Si consideri, ad esempio, un'applicazione .NET monolitica che accede a un database nel database SQL di Azure. Se il database SQL di Azure o qualsiasi altro servizio di terze parti non risponde per un breve periodo di tempo (un database SQL di Azure può essere spostato in un nodo o un server diverso e non risponde per pochi secondi), quando l'utente tenta di eseguire un'azione, l'applicazione potrebbe arrestarsi in modo anomalo e visualizzare un'eccezione nello stesso momento.

Uno scenario simile potrebbe verificarsi in un'app che usa i servizi HTTP. La rete o il servizio stesso potrebbe non essere disponibile nel cloud durante un breve errore temporaneo.

Un'applicazione resiliente come quella illustrata nella figura 4-9 dovrebbe implementare tecniche quali "tentativi con backoff esponenziale" per offrire all'applicazione la possibilità di gestire gli errori temporanei nelle risorse. È inoltre consigliabile usare "interruttori di circuito" nelle applicazioni. Un interruttore impedisce a un'applicazione di provare ad accedere a una risorsa quando si tratta in realtà di un errore a lungo termine. Usando un interruttore, l'applicazione evita di provocare un attacco Denial of Service a se stesso.

![Diagramma degli errori parziali gestiti da tentativi con backoff esponenziale.](./media/retry-partial-failures.png)

**Figura 4-9.** Errori parziali gestiti da tentativi con backoff esponenziale

È possibile utilizzare queste tecniche sia nelle risorse HTTP che nelle risorse del database. Nella figura 4-9, l'applicazione è basata su un'architettura a 3 livelli, quindi sono necessarie queste tecniche a livello di servizi (HTTP) e a livello di livello dati (TCP). In un'applicazione monolitica che usa un solo livello app, oltre al database (senza servizi o microservizi aggiuntivi), la gestione degli errori temporanei a livello di connessione al database potrebbe essere sufficiente. In questo scenario è necessaria solo una particolare configurazione della connessione al database.

Quando si implementano comunicazioni resilienti che accedono al database, a seconda della versione di .NET in uso, può essere semplice, ad esempio [con Entity Framework 6 o versioni successive](/ef/ef6/fundamentals/connection-resiliency/retry-logic). È sufficiente configurare la connessione al database. In alternativa, potrebbe essere necessario usare librerie aggiuntive come il [blocco di applicazioni per la gestione degli errori temporanei](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (per le versioni precedenti di .NET) o persino implementare una libreria personalizzata.

Quando si implementano i tentativi HTTP e gli interruttori di circuito, la raccomandazione per .NET consiste nell'usare la libreria [Polly](https://github.com/App-vNext/Polly) , che ha come destinazione .NET Framework 4,0, .NET Framework 4,5 e .NET standard 1,1, che include il supporto di .NET Core.

Per informazioni su come implementare strategie per la gestione di errori parziali nel cloud, vedere i riferimenti seguenti.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Implementazione della comunicazione resiliente per la gestione di errori parziali**

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- **Entity Framework la resilienza della connessione e la logica di ripetizione dei tentativi (versione 6 e successive)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **Blocco di applicazioni per la gestione degli errori temporanei**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **Libreria Polly per la comunicazione HTTP resiliente**

    <https://github.com/App-vNext/Polly>

>[!div class="step-by-step"]
>[Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md) 
> [Avanti](modernize-your-apps-with-monitoring-and-telemetry.md)
