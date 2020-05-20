---
title: Modelli di resilienza delle applicazioni
description: Architettura di app .NET cloud native per Azure | Modelli di resilienza delle applicazioni
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: bb72e47704c833a2ce86f103a66b0414ce3a37ff
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614324"
---
# <a name="application-resiliency-patterns"></a>Modelli di resilienza delle applicazioni

La prima linea di difesa è la resilienza dell'applicazione.

Sebbene sia possibile investire molto tempo nella scrittura di un Framework di resilienza personalizzato, tali prodotti esistono già. [Polly](http://www.thepollyproject.org/) è una libreria di gestione degli errori e della resilienza .NET completa che consente agli sviluppatori di esprimere i criteri di resilienza in modo Fluent e thread-safe. Polly è destinato alle applicazioni compilate con il .NET Framework o .NET Core. La tabella seguente descrive le funzionalità di resilienza, denominate `policies` , disponibili nella libreria Polly. Possono essere applicati singolarmente o raggruppati.

| Policy | Esperienza |
| :-------- | :-------- |
| Riprova | Configura le operazioni di ripetizione dei tentativi sulle operazioni designate. |
| Interruttore | Blocca le operazioni richieste per un periodo predefinito quando gli errori superano una soglia configurata |
| Timeout | Consente di limitare la durata di attesa di una risposta da parte del chiamante. |
| A scomparti | Vincola le azioni al pool di risorse a dimensione fissa per evitare che le chiamate non riescano a eseguire il swamping di una risorsa. |
| Cache | Archivia le risposte automaticamente. |
| Fallback | Definisce il comportamento strutturato su un errore. |

Si noti come nella figura precedente i criteri di resilienza si applicano ai messaggi di richiesta, sia provenienti da un client esterno che da un servizio back-end. L'obiettivo consiste nel compensare la richiesta di un servizio che potrebbe essere temporaneamente non disponibile. Queste interruzioni di breve durata si manifestano in genere con i codici di stato HTTP indicati nella tabella seguente.

| Codice di stato HTTP| Causa |
| :-------- | :-------- |
| 404 | Non trovato |
| 408 | Timeout richiesta |
| 429 | Troppe richieste (probabilmente è stata limitata) |
| 502 | Gateway non valido |
| 503 | Servizio non disponibile. |
| 504 | Timeout del gateway |

Domanda: si tenterà di ritentare un codice di stato HTTP 403-accesso negato? No. Il sistema funziona correttamente, ma informa il chiamante che non è autorizzato a eseguire l'operazione richiesta. È necessario prestare attenzione per ritentare solo le operazioni causate da errori.

Come consigliato nel capitolo 1, gli sviluppatori Microsoft che creano applicazioni native del cloud dovrebbero avere come destinazione la piattaforma .NET Core. Nella versione 2,1 è stata introdotta la libreria [HTTPClientFactory](https://www.stevejgordon.co.uk/introduction-to-httpclientfactory-aspnetcore) per la creazione di istanze client HTTP per l'interazione con risorse basate su URL. Sostituendo la classe HTTPClient originale, la classe factory supporta molte funzionalità avanzate, una delle quali è una [stretta integrazione](../microservices/implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md) con la libreria di resilienza di Polly. Con esso, è possibile definire facilmente i criteri di resilienza nella classe di avvio dell'applicazione per gestire errori parziali e problemi di connettività.

Successivamente, espandere i modelli di ripetizione dei tentativi e degli interruttori.

### <a name="retry-pattern"></a>Modello di ripetizione dei tentativi

In un ambiente cloud distribuito, le chiamate a servizi e risorse cloud possono avere esito negativo a causa di errori temporanei (di breve durata), che in genere si correggono dopo un breve periodo di tempo. L'implementazione di una strategia di ripetizione dei tentativi consente a un servizio nativo del cloud di mitigare questi scenari.

Il [modello di ripetizione dei tentativi](https://docs.microsoft.com/azure/architecture/patterns/retry) consente a un servizio di ritentare un'operazione di richiesta non riuscita (configurabile) il numero di volte con un tempo di attesa in aumento esponenziale. La figura 6-2 illustra un nuovo tentativo di azione.

![Modello di ripetizione dei tentativi in azione](./media/retry-pattern.png)

**Figura 6-2**. Modello di ripetizione dei tentativi in azione

Nella figura precedente è stato implementato un modello di ripetizione dei tentativi per un'operazione di richiesta. È configurata in modo da consentire fino a quattro tentativi prima di avere esito negativo con un intervallo di backoff (tempo di attesa) a partire da due secondi, che viene raddoppiato in modo esponenziale per ogni tentativo successivo.

- La prima chiamata ha esito negativo e restituisce un codice di stato HTTP 500. L'applicazione attende due secondi e ritenta la chiamata.
- Anche la seconda chiamata ha esito negativo e restituisce un codice di stato HTTP 500. L'applicazione ora raddoppia l'intervallo di backoff a quattro secondi e ritenta la chiamata.
- Infine, la terza chiamata ha esito positivo.
- In questo scenario, l'operazione di ripetizione dei tentativi avrebbe tentato fino a quattro tentativi, raddoppiando la durata di backoff prima della mancata chiamata.
- Se il quarto tentativo non è riuscito, viene richiamato un criterio di fallback per gestire correttamente il problema.

È importante aumentare il periodo di backoff prima di ritentare la chiamata per consentire la corretta correzione automatica del servizio. È consigliabile implementare un backoff con aumento esponenziale (raddoppiando il periodo a ogni tentativo) per consentire un tempo di correzione adeguato.

## <a name="circuit-breaker-pattern"></a>Modello di interruttore

Sebbene il modello di ripetizione dei tentativi possa aiutare a recuperare una richiesta coinvolta in un errore parziale, in alcuni casi gli errori possono essere causati da eventi imprevisti che richiedono più tempo per la risoluzione. Questi errori possono variare, in base alla gravità, dalla perdita parziale della connettività alla totale interruzione di un servizio. In questi casi, è inutile che un'applicazione ritenti continuamente un'operazione che potrebbe non riuscire.

Per peggiorare le cose, l'esecuzione di operazioni di ripetizione continua su un servizio che non risponde può comportare uno scenario di attacco di tipo Denial of Service autonomo, in cui il servizio viene sottoposto a chiamate continue che esauriscono le risorse, ad esempio memoria, thread e connessioni di database, causando un errore in parti non correlate del sistema che usano le stesse risorse.

In queste situazioni è preferibile che l'operazione abbia esito negativo immediatamente e tenti di richiamare il servizio solo se è probabile che abbia esito positivo.

Il [modello a interruttore](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker) può impedire che un'applicazione tenti ripetutamente di eseguire un'operazione che probabilmente avrà esito negativo. Dopo un numero predefinito di chiamate non riuscite, blocca tutto il traffico verso il servizio. Periodicamente, consentirà a una chiamata di valutazione di determinare se l'errore è stato risolto. La figura 6-3 illustra il modello di interruttore in azione.

![Modello di interruttore in azione](./media/circuit-breaker-pattern.png)

**Figura 6-3**. Modello di interruttore in azione

Nella figura precedente è stato aggiunto un modello di interruttore al modello di ripetizione dei tentativi originale. Si noti come dopo 100 richieste non riuscite, gli interruttori di circuito si aprono e non consentono più chiamate al servizio. Il valore CheckCircuit, impostato su 30 secondi, specifica la frequenza con cui la libreria consente a una richiesta di procedere al servizio. Se la chiamata ha esito positivo, il circuito si chiude e il servizio è nuovamente disponibile per il traffico.

Tenere presente che lo scopo del modello di interruttore è *diverso* da quello del modello di ripetizione dei tentativi. Il modello di ripetizione dei tentativi consente a un'applicazione di ritentare un'operazione nella previsione che avrà esito positivo. Il modello di interruttore impedisce a un'applicazione di eseguire un'operazione che probabilmente avrà esito negativo. In genere, un'applicazione *combinerà* questi due modelli usando il modello di ripetizione dei tentativi per richiamare un'operazione tramite un interruttore.

## <a name="testing-for-resiliency"></a>Eseguire il test per la resilienza

I test per la resilienza non possono essere sempre eseguiti nello stesso modo in cui si verifica la funzionalità dell'applicazione (eseguendo unit test, test di integrazione e così via). Infatti, è necessario testare il modo in cui il carico di lavoro end-to-end viene eseguito in condizioni di errore che si verificano solo in modo intermittente. Ad esempio: inserire errori con processi arrestati in modo anomalo, certificati scaduti, rendere i servizi dipendenti non disponibili e così via. I Framework come [Chaos-Monkey](https://github.com/Netflix/chaosmonkey) possono essere usati per tali Chaos testing.

La resilienza dell'applicazione è un must per la gestione di operazioni richieste problematiche. Ma solo metà della storia. Si tratteranno quindi le funzionalità di resilienza disponibili nel cloud di Azure.

>[!div class="step-by-step"]
>[Precedente](resiliency.md) 
> [Avanti](infrastructure-resiliency-azure.md)
