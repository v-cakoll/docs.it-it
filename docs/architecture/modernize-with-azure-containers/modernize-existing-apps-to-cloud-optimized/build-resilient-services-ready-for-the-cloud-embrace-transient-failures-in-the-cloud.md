---
title: Crea servizi resilienti pronti per il cloud. Gestire gli errori temporanei nel cloud
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Crea servizi resilienti pronti per il cloud. Gestire gli errori temporanei nel cloud
ms.date: 04/30/2018
ms.openlocfilehash: e516dc675ceb8def25c6d676bced0ea7f253b2d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74711256"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Creare servizi resilienti pronti per il cloud: gestire gli errori temporanei nel cloud

La resilienza è la capacità di recupero da errori che consente un funzionamento continuativo. La resilienza non riguarda l'evitare gli errori, ma accettare il fatto che si verificheranno errori e quindi rispondere in modo da evitare tempi di inattività o perdita di dati. L'obiettivo della resilienza è riportare l'applicazione in uno stato pienamente operativo dopo un errore.

L'applicazione è pronta per il cloud quando, come minimo, implementa un modello di resilienza basato su software, anziché un modello basato su hardware. L'applicazione cloud deve accettare gli errori parziali che si verificheranno sicuramente. Progettare o eseguire parzialmente il refactoring dell'applicazione per ottenere resilienza con errori parziali previsti. Deve essere progettato per far fronte a errori parziali, ad esempio interruzioni e nodi di rete temporanei o arrestarsi di macchine virtuali nel cloud. Anche i contenitori spostati in un nodo diverso all'interno di un cluster dell'agente di orchestrazione possono causare errori brevi intermittenti all'interno dell'applicazione.

## <a name="handling-partial-failure"></a>Gestione degli errori parziali

In un'applicazione basata su cloud, c'è un rischio sempre presente di errore parziale. Ad esempio, una singola istanza del sito Web o un contenitore potrebbe non riuscire o potrebbe non essere disponibile o non rispondere per un breve periodo di tempo. In alternativa, una singola macchina virtuale o server potrebbe bloccarsi.

Poiché i client e i servizi sono processi separati, un servizio potrebbe non essere in grado di rispondere in modo tempestivo alla richiesta di un client. Il servizio potrebbe essere sovraccarico e rispondere lentamente alle richieste o potrebbe non essere accessibile per un breve periodo di tempo a causa di problemi di rete.

Si consideri ad esempio un'applicazione .NET monolitica che accede a un database nel database SQL di Azure.For example, consider a monolithic .NET application that accesses a database in Azure SQL Database. Se il database SQL di Azure o qualsiasi altro servizio di terze parti non risponde per un breve periodo di tempo (un database SQL di Azure potrebbe essere spostato in un altro nodo o server e non rispondere per alcuni secondi), quando l'utente tenta di eseguire qualsiasi azione, l'applicazione potrebbe bloccarsi e visualizzare un'eccezione nello stesso momento.

Uno scenario simile potrebbe verificarsi in un'app che utilizza servizi HTTP. La rete o il servizio stesso potrebbe non essere disponibile nel cloud durante un errore breve e temporaneo.

Un'applicazione resiliente come quella illustrata nella Figura 4-9 deve implementare tecniche come "tentativi con backoff esponenziale" per dare all'applicazione l'opportunità di gestire errori temporanei nelle risorse. È inoltre necessario utilizzare "interruttori di circuito" nelle applicazioni. Un interruttore impedisce a un'applicazione di tentare di accedere a una risorsa quando si tratta effettivamente di un errore a lungo termine. Utilizzando un interruttore, l'applicazione evita di provocare un Denial of Service a se stessa.

![Diagramma degli errori parziali gestiti da tentativi con backoff esponenziale.](./media/retry-partial-failures.png)

**Figura 4-9.** Errori parziali gestiti da tentativi con backoff esponenzialePartial failures handled by retries with exponential backoff

È possibile utilizzare queste tecniche sia nelle risorse HTTP che nelle risorse di database. Nella Figura 4-9, l'applicazione è basata su un'architettura a 3 livelli, pertanto sono necessarie queste tecniche a livello di servizi (HTTP) e a livello di dati (TCP). In un'applicazione monolitica che usa un solo livello di app oltre al database (senza servizi aggiuntivi o microservizi), la gestione degli errori temporanei a livello di connessione al database potrebbe essere sufficiente. In questo scenario, è necessaria solo una particolare configurazione della connessione al database.

Quando si implementano comunicazioni resilienti che accedono al database, a seconda della versione di .NET in uso, può essere semplice (ad esempio, [con Entity Framework 6 o versione successiva.](/ef/ef6/fundamentals/connection-resiliency/retry-logic) Si tratta solo di configurare la connessione al database). In alternativa, potrebbe essere necessario utilizzare librerie aggiuntive come [Transient Fault Handling Application Block](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (per le versioni precedenti di .NET) o anche implementare la propria libreria.

Quando si implementano tentativi HTTP e interruttori di circuito, si consiglia di utilizzare la libreria [Polly,](https://github.com/App-vNext/Polly) destinata a .NET Framework 4.0, .NET Framework 4.5 e .NET Standard 1.1, che include il supporto di .NET Core.

Per informazioni su come implementare strategie per la gestione di errori parziali nel cloud, vedere i riferimenti seguenti.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Implementazione di una comunicazione resiliente per gestire un errore parzialeImplementing resilient communication to handle partial failure**

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- **Resilienza della connessione di Entity Framework e logica di ripetizione dei tentativi (versione 6 e successive)Entity Framework connection resiliency and retry logic (version 6 and later)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **Blocco di applicazioni per la gestione degli errori temporanei**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **Libreria Polly per una comunicazione HTTP resiliente**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
>[Successivo](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[precedente](modernize-your-apps-with-monitoring-and-telemetry.md)
