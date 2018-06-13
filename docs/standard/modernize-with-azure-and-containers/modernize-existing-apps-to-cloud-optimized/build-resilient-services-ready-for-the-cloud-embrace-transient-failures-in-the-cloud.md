---
title: Compilare servizi resilienti pronti per il cloud. Adottare gli errori temporanei nel cloud
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Compilare servizi resilienti pronti per il cloud. Adottare gli errori temporanei nel cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 1df21d0f647b96c315686921276be3526f66bbc8
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957931"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Compilare servizi resilienti pronti per il cloud: adottare gli errori temporanei nel cloud

La resilienza è la capacità di correggere gli errori e continuare a funzionare. Resilienza non è tuttavia evitare errori, ma che accetta il fatto che si verificheranno errori e rispondere ad essi in modo da evitare tempi di inattività o perdita di dati. L'obiettivo della resilienza è riportare l'applicazione in uno stato pienamente operativo dopo un errore.

Quando, come minimo, implementa un modello basato sul software di resilienza, piuttosto che un modello basato su hardware, l'applicazione è pronta per il cloud. L'applicazione cloud deve prevedere l'eventualità di errori parziali che certamente si verificherà. Progettare o parzialmente effettuarne il refactoring dell'applicazione per ottenere resilienza con errori parziali previsti. Deve essere progettato per gestire gli errori parziali, ad esempio interruzioni temporanee della rete e i nodi o le macchine virtuali nel cloud di un arresto anomalo. Anche i contenitori viene spostati su un nodo diverso all'interno di un cluster di orchestrator possono causare errori di breve intermittenti all'interno dell'applicazione.

## <a name="handling-partial-failure"></a>Gestione degli errori parziali

In un'applicazione basata su cloud, c'è un rischio più di un errore parziale. Ad esempio, un'istanza singola del sito Web o un contenitore potrebbe non riuscire oppure potrebbe essere non disponibile o non risponde per un breve periodo di tempo. In alternativa, una macchina virtuale o un server singolo potrebbe arrestarsi in modo anomalo.

Poiché i client e servizi sono processi separati, un servizio potrebbe non essere in grado di rispondere in modo tempestivo a una richiesta del client. Il servizio potrebbe essere sottoposto a overload e rispondere lentamente alle richieste o potrebbe non essere accessibile per un breve periodo di tempo a causa di problemi di rete.

Si consideri ad esempio un'applicazione .NET monolitica che accede a un database nel Database di SQL Azure. Se il database SQL di Azure o qualsiasi altro servizio di terze parti non risponde per una breve tempo (un database SQL di Azure potrebbe essere spostato in un nodo diverso o un server e che non risponde per alcuni secondi), quando l'utente tenta di eseguire qualsiasi azione, l'applicazione potrebbe bloccarsi e m w un'eccezione nello stesso momento.

Uno scenario analogo può verificarsi in un'applicazione che utilizza i servizi HTTP. La rete o del servizio potrebbe non essere disponibile nel cloud durante un errore temporaneo, breve.

Un'applicazione simile a quello illustrato nella figura 4-9 resiliente deve implementare tecniche come "tentativi con backoff esponenziale" per assegnare all'applicazione la possibilità di gestire gli errori temporanei nelle risorse. È inoltre necessario utilizzare "interruttori" nelle applicazioni. Un interruttore arresta un'applicazione di tentare di accedere a una risorsa quando è effettivamente un errore a lungo termine. Utilizzando un interruttore, l'applicazione evita avere provocato un attacco denial of service a se stessa.

![Errori parziali gestiti dai tentativi con backoff esponenziale](./media/image9.png)

> **Figura 4 a 9.** Errori parziali gestiti dai tentativi con backoff esponenziale

È possibile utilizzare queste tecniche in risorse HTTP e nelle risorse di database. Nella figura 4-9, l'applicazione si basa su un'architettura a 3 livelli, pertanto è necessario queste tecniche a livello di servizi (HTTP) e al livello dati (TCP). In un'applicazione monolitica che utilizza solo un livello di singola app oltre al database (servizi aggiuntivi o microservizi), gestione degli errori temporanei a livello di connessione di database potrebbe essere sufficiente. In questo scenario, è necessario solo una particolare configurazione della connessione al database.

Quando si implementa resiliente delle comunicazioni che accedono al database, a seconda della versione di .NET in uso, può essere semplice (ad esempio [con Entity Framework 6 o versione successiva](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), si tratta solo di configurare il connessione al database). In alternativa, potrebbe essere necessario utilizzare librerie aggiuntive come la [Transient Fault Handling Application Block](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (per le versioni precedenti di .NET), o anche di implementare la propria libreria.

Quando si implementa tentativi HTTP e circuito, l'indicazione per .NET consiste nell'utilizzare il [Polly](https://github.com/App-vNext/Polly) libreria, destinato a .NET Framework 4.0, .NET Framework 4.5 e .NET Standard 1.1, che include il supporto di .NET Core.

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
