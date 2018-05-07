---
title: Compilare servizi resilienti pronti per il cloud. Adottare gli errori temporanei nel cloud
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Compilare servizi resilienti pronti per il cloud. Adottare gli errori temporanei nel cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 23b8dce9fb5dd3388c1d76e5ba9c2412c7d17a21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Compilare servizi resilienti pronti per il cloud: adottare gli errori temporanei nel cloud

La resilienza è la capacità di correggere gli errori e continuare a funzionare. Resilienza non è tuttavia evitare errori, ma che accetta il fatto che si verificheranno errori e rispondere ad essi in modo da evitare tempi di inattività o perdita di dati. L'obiettivo della resilienza è riportare l'applicazione in uno stato pienamente operativo dopo un errore.

Quando, come minimo, implementa un modello basato sul software di resilienza, piuttosto che un modello basato su hardware, l'applicazione è pronta per il cloud. L'applicazione cloud deve prevedere l'eventualità di errori parziali che certamente si verificherà. È necessario progettare o parzialmente il refactoring dell'applicazione se si desidera ottenere resilienza agli errori parziali previsto. Deve essere progettato per gestire gli errori parziali, ad esempio interruzioni temporanee della rete e i nodi o le macchine virtuali nel cloud di un arresto anomalo. Anche i contenitori viene spostati su un nodo diverso all'interno di un cluster di orchestrator possono causare errori di breve intermittenti all'interno dell'applicazione.

## <a name="handling-partial-failure"></a>Gestione degli errori parziali

In un'applicazione basata su cloud, c'è un rischio più di un errore parziale. Ad esempio, un'istanza singola del sito Web o un contenitore potrebbe non riuscire oppure potrebbe essere non disponibile o non risponde per un breve periodo di tempo. In alternativa, una macchina virtuale o un server singolo potrebbe arrestarsi in modo anomalo.

Poiché i client e servizi sono processi separati, un servizio potrebbe non essere in grado di rispondere in modo tempestivo a una richiesta del client. Il servizio potrebbe essere sottoposto a overload e solo molto lentamente rispondere alle richieste o potrebbe semplicemente non essere accessibile per un breve periodo di tempo a causa di problemi di rete.

Si consideri ad esempio un'applicazione .NET monolitica che accede a un database nel Database di SQL Azure. Se il database SQL di Azure o qualsiasi altro servizio di terze parti non risponde per una breve tempo (un database SQL di Azure potrebbe essere spostato in un server o un nodo diverso e non risponde per alcuni secondi), quando l'utente tenta di eseguire alcuna azione, l'applicazione potrebbe bloccarsi e un'eccezione al momento stessa w.

Uno scenario analogo può verificarsi in un'applicazione che utilizza i servizi HTTP. La rete o del servizio potrebbe non essere disponibile nel cloud durante un errore temporaneo, breve.

Un'applicazione simile a quello illustrato nella figura 4-9 resiliente deve implementare tecniche come "tentativi con backoff esponenziale" per assegnare all'applicazione la possibilità di gestire gli errori temporanei nelle risorse. È inoltre necessario utilizzare "interruttori" nelle applicazioni. Un interruttore arresta un'applicazione di tentare di accedere a una risorsa quando è effettivamente un errore a lungo termine. Utilizzando un interruttore, l'applicazione evita avere provocato un attacco denial of service a se stessa.

![Errori parziali gestiti dai tentativi con backoff esponenziale](./media/image9.png)

> **Figura 4 a 9.** Errori parziali gestiti dai tentativi con backoff esponenziale

È possibile utilizzare queste tecniche in risorse HTTP e nelle risorse di database. Nella figura 4-9, l'applicazione si basa su un'architettura a 3 livelli, pertanto è necessario queste tecniche a livello di servizi (HTTP) e al livello dati (TCP). In un'applicazione monolitica che utilizza solo un livello di singola app oltre al database (servizi aggiuntivi o microservizi), gestione degli errori temporanei a livello di connessione di database potrebbe essere sufficiente. In questo scenario, è necessario in genere solo una particolare configurazione della connessione di database.

Quando si implementa resiliente delle comunicazioni che accedono al database, a seconda della versione di .NET in uso, può essere molto semplice (ad esempio, [con Entity Framework 6 o versione successiva](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), è sufficiente la configurazione di connessione di database). In alternativa, potrebbe essere necessario utilizzare librerie aggiuntive come la [Transient Fault Handling Application Block](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (per le versioni precedenti di .NET), o anche di implementare la propria libreria.

Quando si implementa tentativi HTTP e circuito, l'indicazione per .NET consiste nell'usare il [Polly](https://github.com/App-vNext/Polly) libreria che ha come destinazione .NET 4.0, .NET 4.5 e .NET Standard 1.1, che include il supporto di .NET Core.

Per informazioni su come implementare strategie di gestione degli errori parziali nel cloud, vedere i seguenti riferimenti.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Implementazione di comunicazione resiliente per gestire gli errori parziali**

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

-   **Entità connessione resilienza e riprovare la logica del Framework (versione 6 e versioni successive)**

    [https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx)

-   **Il blocco applicazione di gestione degli errori temporanei**

-   [https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx)

-   **Libreria Polly per le comunicazioni HTTP resilienti**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
[Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Successivo](modernize-your-apps-with-monitoring-and-telemetry.md)
