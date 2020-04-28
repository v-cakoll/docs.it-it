---
title: Modelli di resilienza delle applicazioni
description: Architettura di app .NET cloud native per Azure | Modelli di resilienza delle applicazioni
ms.date: 06/30/2019
ms.openlocfilehash: 6805603f349578655b2535c7346af368c5ce1841
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199690"
---
# <a name="application-resiliency-patterns"></a>Modelli di resilienza delle applicazioni

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La prima linea di difesa è la resilienza dell'applicazione abilitata per il software.

Sebbene sia possibile investire molto tempo nella scrittura di un Framework di resilienza personalizzato, tali prodotti esistono già. Ad esempio, [Polly](http://www.thepollyproject.org/) è una libreria completa di resilienza .NET e di gestione degli errori temporanei che consente agli sviluppatori di esprimere i criteri di resilienza in modo Fluent e thread-safe. Polly è destinato alle applicazioni compilate con il .NET Framework completo o .NET Core. La figura 6-2 illustra i criteri di resilienza (ovvero funzionalità) disponibili nella libreria Polly. Questi criteri possono essere applicati singolarmente o combinati insieme.

![Framework Polly](./media/polly-resiliency-framework.png)

**Figura 6-2**. Funzionalità del Framework di resilienza di Polly

Si noti come nella figura precedente i criteri di resilienza si applicano ai messaggi di richiesta, sia provenienti da un client esterno che da un altro servizio back-end. L'obiettivo consiste nel compensare la richiesta di un servizio che potrebbe essere temporaneamente non disponibile. Queste brevi interruzioni si manifestano in genere con i codici di stato HTTP illustrati nella figura 6-3.

![Codici di stato HTTP da ritentare](./media/http-status-codes.png)

**Figura 6-3**. Codici di stato HTTP da ritentare

Domanda: si tenterà di ritentare un codice di stato HTTP 403-accesso negato? No. Il sistema funziona correttamente, ma informa il chiamante che non è autorizzato a eseguire l'operazione richiesta. È necessario prestare attenzione per ritentare solo le operazioni causate da errori.

Come consigliato nel capitolo 1, gli sviluppatori Microsoft che creano applicazioni native del cloud dovrebbero avere come destinazione .NET Core. Nella versione 2,1 è stata introdotta la libreria [HTTPClientFactory](https://www.stevejgordon.co.uk/introduction-to-httpclientfactory-aspnetcore) per la creazione di istanze client HTTP per l'interazione con risorse basate su URL. Sostituendo la classe HTTPClient originale, la classe factory supporta molte funzionalità avanzate, una delle quali è una [stretta integrazione](../microservices/implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md) con la libreria di resilienza di Polly. Con esso, è possibile definire facilmente i criteri di resilienza nella classe di avvio dell'applicazione per gestire errori parziali e problemi di connettività.

Successivamente, espandere i modelli di ripetizione dei tentativi e degli interruttori.

### <a name="retry-pattern"></a>Modello di ripetizione dei tentativi

In un ambiente cloud distribuito, le chiamate a servizi e risorse cloud possono avere esito negativo a causa di errori temporanei (di breve durata), che in genere si correggono dopo un breve periodo di tempo. L'implementazione di una strategia di ripetizione dei tentativi consente a un servizio nativo del cloud di gestire questi scenari.

Il [modello di ripetizione dei tentativi](https://docs.microsoft.com/azure/architecture/patterns/retry) consente a un servizio di ritentare un'operazione di richiesta non riuscita (configurabile) il numero di volte con un tempo di attesa in aumento esponenziale. La figura 6-4 illustra un nuovo tentativo di azione.

![Modello di ripetizione dei tentativi in azione](./media/retry-pattern.png)

**Figura 6-4**. Modello di ripetizione dei tentativi in azione

Nella figura precedente è stato implementato un modello di ripetizione dei tentativi per un'operazione di richiesta. È configurata in modo da consentire fino a quattro tentativi prima di avere esito negativo con un intervallo di backoff (tempo di attesa) a partire da due secondi, che viene raddoppiato in modo esponenziale per ogni tentativo successivo.

- La prima chiamata ha esito negativo e restituisce un codice di stato HTTP 500. L'applicazione attende due secondi e ritenta la chiamata.
- Anche la seconda chiamata ha esito negativo e restituisce un codice di stato HTTP 500. L'applicazione ora raddoppia l'intervallo di backoff a quattro secondi e ritenta la chiamata.
- Infine, la terza chiamata ha esito positivo.
- In questo scenario, l'operazione di ripetizione dei tentativi avrebbe tentato fino a quattro tentativi, raddoppiando la durata di backoff prima della mancata chiamata.

È importante aumentare il periodo di backoff prima di ritentare la chiamata per consentire la corretta correzione automatica del servizio. È consigliabile implementare un backoff con aumento esponenziale (raddoppiando il periodo a ogni tentativo) per consentire un tempo di correzione adeguato.

## <a name="circuit-breaker-pattern"></a>Modello di interruttore

Sebbene il modello di ripetizione dei tentativi possa aiutare a recuperare una richiesta coinvolta in un errore parziale, in alcuni casi gli errori possono essere causati da eventi imprevisti che richiedono più tempo per la risoluzione. Questi errori possono variare, in base alla gravità, dalla perdita parziale della connettività alla totale interruzione di un servizio. In questi casi, è inutile che un'applicazione ritenti continuamente un'operazione che potrebbe non riuscire.

Per peggiorare le cose, l'esecuzione di operazioni di ripetizione continua su un servizio che non risponde può comportare uno scenario di attacco di tipo Denial of Service autonomo, in cui il servizio viene sottoposto a chiamate continue che esauriscono le risorse, ad esempio memoria, thread e connessioni di database, causando un errore in parti non correlate del sistema che usano le stesse risorse.

In queste situazioni è preferibile che l'operazione abbia esito negativo immediatamente e tenti di richiamare il servizio solo se è probabile che abbia esito positivo.

Il [modello a interruttore](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker) può impedire che un'applicazione tenti ripetutamente di eseguire un'operazione che probabilmente avrà esito negativo. Monitora inoltre l'applicazione con una chiamata di valutazione periodica per determinare se l'errore è stato risolto. La figura 6-5 illustra il modello di interruttore in azione.

![Modello di interruttore in azione](./media/circuit-breaker-pattern.png)

**Figura 6-5**. Modello di interruttore in azione

Nella figura precedente è stato aggiunto un modello di interruttore al modello di ripetizione dei tentativi originale. Si noti come dopo 10 richieste non riuscite, gli interruttori di circuito si aprono e non consentono più chiamate al servizio. Il valore CheckCircuit, impostato su 30 secondi, specifica la frequenza con cui la libreria consente a una richiesta di procedere al servizio. Se la chiamata ha esito positivo, il circuito si chiude e il servizio è nuovamente disponibile per il traffico.

Tenere presente che lo scopo del modello di interruttore è *diverso* da quello del modello di ripetizione dei tentativi. Il modello di ripetizione dei tentativi consente a un'applicazione di ritentare un'operazione nella previsione che avrà esito positivo. Il modello di interruttore impedisce a un'applicazione di eseguire un'operazione che probabilmente avrà esito negativo. Spesso, un'applicazione *combinerà* questi due modelli usando il modello di ripetizione dei tentativi per richiamare un'operazione tramite un interruttore. Tuttavia, la logica di ripetizione dei tentativi deve essere sensibile alle eventuali eccezioni restituite dall'interruttore e abbandonare i tentativi se l'interruttore indica che un errore non è temporaneo.

La resilienza dell'applicazione è un must per la gestione di operazioni richieste problematiche. Ma solo metà della storia. Si tratteranno quindi le funzionalità di resilienza disponibili nel cloud di Azure.

>[!div class="step-by-step"]
>[Precedente](resiliency.md)
>[successivo](infrastructure-resiliency-azure.md)
