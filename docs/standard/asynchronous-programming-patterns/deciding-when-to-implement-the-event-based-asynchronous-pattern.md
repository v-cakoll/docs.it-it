---
title: Quando implementare il modello asincrono basato su eventi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
ms.openlocfilehash: c235a838504889a105ef98df47f7373a145503da
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289447"
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>Quando implementare il modello asincrono basato su eventi

Il modello asincrono basato su eventi fornisce un modello per esporre il comportamento asincrono di una classe. Con l'introduzione di questo modello, .NET Framework definisce due modelli per l'esposizione del comportamento asincrono: il modello asincrono basato sull'interfaccia <xref:System.IAsyncResult?displayProperty=nameWithType> e il modello basato su eventi. Questo argomento illustra quando è appropriato implementare entrambi i modelli.

Per altre informazioni sulla programmazione asincrona con l'interfaccia <xref:System.IAsyncResult>, vedere [Modello di programmazione asincrona (APM)](asynchronous-programming-model-apm.md).

## <a name="general-principles"></a>Principi generali

In generale, è consigliabile esporre le funzionalità asincrone usando il modello asincrono basato su eventi ogni volta che è possibile. Tuttavia, esistono alcuni requisiti che il modello basato su eventi non riesce a soddisfare. In questi casi, potrebbe essere necessario implementare il modello <xref:System.IAsyncResult> oltre al modello basato su eventi.

> [!NOTE]
> È raro che il modello <xref:System.IAsyncResult> venga implementato senza che venga implementato anche il modello basato su eventi.

## <a name="guidelines"></a>Linee guida

L'elenco seguente illustra le linee guida che indicano quando è consigliabile implementare il modello asincrono basato su eventi:

- Usare il modello basato su eventi come API predefinita per esporre il comportamento asincrono per la classe.

- Non esporre il modello <xref:System.IAsyncResult> quando la classe viene usata principalmente in un'applicazione client, ad esempio Windows Form.

- Esporre il modello <xref:System.IAsyncResult> solo quando è necessario per soddisfare i requisiti. Ad esempio, per la compatibilità con un'API esistente potrebbe essere necessario esporre il modello <xref:System.IAsyncResult>.

- Non esporre il modello <xref:System.IAsyncResult> senza esporre anche il modello basato su eventi.

- Se è necessario esporre il modello <xref:System.IAsyncResult>, eseguire questa operazione come opzione avanzata. Se ad esempio si genera un oggetto proxy, generare il modello basato su eventi per impostazione predefinita, con un'opzione per generare il modello <xref:System.IAsyncResult>.

- Basare l'implementazione del modello basato su eventi sull'implementazione del modello <xref:System.IAsyncResult>.

- Evitare di esporre sia il modello basato su eventi che il modello <xref:System.IAsyncResult> nella stessa classe. Esporre il modello basato su eventi nelle classi "di livello superiore" e il modello <xref:System.IAsyncResult> nelle classi "livello inferiore". Confrontare, ad esempio, il modello basato su eventi nel componente <xref:System.Net.WebClient> con il modello <xref:System.IAsyncResult> nella classe <xref:System.Web.HttpRequest>.

  - Esporre il modello basato su eventi e il modello <xref:System.IAsyncResult> nella stessa classe quando è necessario per la compatibilità. Se ad esempio già stata rilasciata un'API che usa il modello <xref:System.IAsyncResult>, sarà necessario mantenere il modello <xref:System.IAsyncResult> per la compatibilità con le versioni precedenti.

  - Esporre il modello basato su eventi e il modello <xref:System.IAsyncResult> nella stessa classe se la complessità del modello a oggetti risultante riduce il vantaggio offerto dalle implementazioni separate. È meglio esporre entrambi i modelli in una singola classe che evitare di esporre il modello basato su eventi.

  - Se è necessario esporre sia il modello basato su eventi che il modello <xref:System.IAsyncResult> in una singola classe, usare <xref:System.ComponentModel.EditorBrowsableAttribute> impostato su <xref:System.ComponentModel.EditorBrowsableState.Advanced> per contrassegnare l'implementazione del modello <xref:System.IAsyncResult> come funzionalità avanzata. Questo indica agli ambienti di progettazione, ad esempio Visual Studio IntelliSense, di non visualizzare le proprietà e i metodi <xref:System.IAsyncResult>. Queste proprietà e metodi sono ancora completamente utilizzabili, ma lo sviluppatore che usa IntelliSense ha un quadro più chiaro dell'API.

## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>Criteri per esporre il modello IAsyncResult oltre al modello basato su eventi

Anche se il modello asincrono basato su eventi offre numerosi vantaggi negli scenari indicati prima, presenta tuttavia alcuni svantaggi, di cui è meglio essere a conoscenza se le prestazioni sono il requisito più importante.

Esistono tre scenari che non contemplano il modello basato su eventi oltre al modello <xref:System.IAsyncResult>:

- Blocco dell'attesa di un oggetto <xref:System.IAsyncResult>

- Blocco dell'attesa di più oggetti <xref:System.IAsyncResult>

- Polling del completamento di <xref:System.IAsyncResult>

È possibile gestire questi scenari usando il modello basato su eventi, che è tuttavia più complesso che usare il modello <xref:System.IAsyncResult>.

Gli sviluppatori usano spesso il modello <xref:System.IAsyncResult> per i servizi che in genere presentano requisiti di prestazioni molto elevate. Ad esempio, lo scenario del polling del completamento è una tecnica per i server con prestazioni elevate.

Il modello basato su eventi è anche meno efficiente del modello <xref:System.IAsyncResult> perché crea più oggetti, soprattutto <xref:System.EventArgs>, ed esegue la sincronizzazione nei thread.

L'elenco seguente illustra alcuni consigli da seguire se si decide di usare il modello <xref:System.IAsyncResult>:

- Esporre il modello <xref:System.IAsyncResult> solo quando è necessario supporto specifico per gli oggetti <xref:System.Threading.WaitHandle> o <xref:System.IAsyncResult>.

- Esporre il modello <xref:System.IAsyncResult> solo quando si ha un'API esistente che usa il modello <xref:System.IAsyncResult>.

- Se si ha un'API esistente basata sul modello <xref:System.IAsyncResult>, considerare anche la possibilità di esporre il modello basato su eventi nella versione successiva.

- Esporre il modello <xref:System.IAsyncResult> solo se è stato verificato che i requisiti di prestazioni non possono essere soddisfatti dal modello basato su eventi, ma possono essere soddisfatti dal modello <xref:System.IAsyncResult>.

## <a name="see-also"></a>Vedere anche

- [Procedura: implementare un componente che supporta il modello asincrono basato su eventi](component-that-supports-the-event-based-asynchronous-pattern.md)
- [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)
- [Implementazione del modello asincrono basato su eventi](implementing-the-event-based-asynchronous-pattern.md)
- [Suggerimenti per l'implementazione del modello asincrono basato su eventi](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Cenni preliminari sul modello asincrono basato su eventi](event-based-asynchronous-pattern-overview.md)
