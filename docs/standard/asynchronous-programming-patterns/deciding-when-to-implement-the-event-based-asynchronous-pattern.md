---
title: Quando implementare il modello asincrono basato su eventi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48de1b736c251a61a2ad34975c77bc2bca139626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>Quando implementare il modello asincrono basato su eventi
Il modello asincrono basato su eventi fornisce un modello per esporre il comportamento asincrono di una classe. Con l'introduzione di questo modello, il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] definisce due modelli per l'esposizione del comportamento asincrono: il modello asincrono basato sul <xref:System.IAsyncResult?displayProperty=nameWithType> interfaccia e il modello basato su eventi. In questo argomento viene descritto quando è appropriato per l'implementazione di entrambi i modelli.  
  
 Per ulteriori informazioni sulla programmazione asincrona con il <xref:System.IAsyncResult> interfaccia, vedere [basato su eventi modello asincrono (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
## <a name="general-principles"></a>Principi generali  
 In generale, è necessario esporre funzionalità asincrone mediante il modello asincrono con codifica basata su eventi ogni volta che è possibile. Tuttavia, esistono alcuni requisiti che non soddisfa il criterio basato su eventi. In questi casi, è necessario implementare la <xref:System.IAsyncResult> modello oltre il modello basato su eventi.  
  
> [!NOTE]
>  È raro che il <xref:System.IAsyncResult> modello venga implementato senza anche il modello basato su eventi.  
  
## <a name="guidelines"></a>Indicazioni  
 Nell'elenco seguente vengono descritte le linee guida per quando è necessario implementare modello asincrono basato su eventi:  
  
-   Utilizzare il modello basato su eventi come API predefinita per esporre il comportamento asincrono per la classe.  
  
-   Non esporre il <xref:System.IAsyncResult> di schema quando la classe viene utilizzata principalmente in un'applicazione client, ad esempio Windows Form.  
  
-   Esporre solo le <xref:System.IAsyncResult> quando è necessario per soddisfare i requisiti di schema. Ad esempio, la compatibilità con un'API esistente potrebbe essere necessario esporre il <xref:System.IAsyncResult> modello.  
  
-   Non esporre il <xref:System.IAsyncResult> modello senza esporre anche il modello basato su eventi.  
  
-   Se è necessario esporre la <xref:System.IAsyncResult> di schema, eseguire questa operazione come un'opzione avanzata. Ad esempio, se si genera un oggetto proxy, generare il modello basato su eventi per impostazione predefinita, con un'opzione per generare il <xref:System.IAsyncResult> modello.  
  
-   L'implementazione del modello basato su eventi di compilazione <xref:System.IAsyncResult> implementazione del modello.  
  
-   Evitare di esporre il modello basato su eventi e <xref:System.IAsyncResult> modello sulla stessa classe. Esporre il modello basato su eventi nelle classi "di livello superiore" e <xref:System.IAsyncResult> su "livello inferiore" classi di pattern. Ad esempio, confrontare il modello basato su eventi nel <xref:System.Net.WebClient> componente con il <xref:System.IAsyncResult> serie sul <xref:System.Web.HttpRequest> classe.  
  
    -   Esporre il modello basato su eventi e <xref:System.IAsyncResult> modello nella stessa classe quando richiede la compatibilità. Ad esempio, se già stata rilasciata un'API che utilizza il <xref:System.IAsyncResult> modello, è necessario mantenere il <xref:System.IAsyncResult> modello per la compatibilità con le versioni precedenti.  
  
    -   Esporre il modello basato su eventi e <xref:System.IAsyncResult> sulla stessa classe di schema se la complessità del modello di oggetto risultante superiore al vantaggio offerto da implementazioni separate. È consigliabile esporre entrambi i modelli in una singola classe anziché evitare di esporre il modello basato su eventi.  
  
    -   Se è necessario esporre il modello basato su eventi e <xref:System.IAsyncResult> modello in una singola classe, utilizzare <xref:System.ComponentModel.EditorBrowsableAttribute> impostato su <xref:System.ComponentModel.EditorBrowsableState.Advanced> per contrassegnare il <xref:System.IAsyncResult> implementazione del modello come una funzionalità avanzata. Indica agli ambienti di sviluppo, ad esempio [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] IntelliSense, per non visualizzare il <xref:System.IAsyncResult> proprietà e metodi. Queste proprietà e metodi sono ancora completamente utilizzabili, ma lo sviluppatore in IntelliSense è una visualizzazione più chiara dell'API.  
  
## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>Criteri per esporre il modello di IAsyncResult oltre il modello basato su eventi  
 Mentre il modello asincrono basato su eventi offre numerosi vantaggi sotto gli scenari indicati in precedenza, presenta alcuni svantaggi, tra cui è necessario essere a conoscenza se le prestazioni sono un requisito fondamentale.  
  
 Esistono tre scenari in cui non si applica il modello basato su eventi, nonché <xref:System.IAsyncResult> modello:  
  
-   Attesa su una bloccante<xref:System.IAsyncResult>  
  
-   Attesa bloccante su numerosi <xref:System.IAsyncResult> oggetti  
  
-   Polling per il completamento nel<xref:System.IAsyncResult>  
  
 È possibile gestire questi scenari utilizzando il modello basato su eventi, ma in questo modo è più complesso rispetto all'utilizzo di <xref:System.IAsyncResult> modello.  
  
 Gli sviluppatori usano spesso il <xref:System.IAsyncResult> modello per i servizi che in genere presentano i requisiti di prestazioni molto elevate. Ad esempio, il polling per lo scenario di completamento è una tecnica di server ad alte prestazioni.  
  
 Inoltre, il modello basato su eventi è meno efficiente il <xref:System.IAsyncResult> di schema perché crea più oggetti, specialmente <xref:System.EventArgs>, ed esegue la sincronizzazione tra thread.  
  
 Nell'elenco seguente sono riportati alcuni consigli da seguire se si decide di utilizzare il <xref:System.IAsyncResult> modello:  
  
-   Esporre solo le <xref:System.IAsyncResult> di schema quando è necessario disporre del supporto per <xref:System.Threading.WaitHandle> o <xref:System.IAsyncResult> oggetti.  
  
-   Esporre solo le <xref:System.IAsyncResult> di schema quando si dispone di un'API esistente che utilizza il <xref:System.IAsyncResult> modello.  
  
-   Se si dispone di un'API esistente basata sul <xref:System.IAsyncResult> di schema, è consigliabile esporre anche il modello basato su eventi nel rilascio successivo.  
  
-   Esporre solo <xref:System.IAsyncResult> modello se si dispone di requisiti di prestazioni elevate, che significa che non possono essere soddisfatti dal modello basato su eventi, ma possono essere soddisfatti dal <xref:System.IAsyncResult> modello.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura dettagliata: implementazione di un componente che supporta il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)  
 [Programmazione multithreading con il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [Implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
