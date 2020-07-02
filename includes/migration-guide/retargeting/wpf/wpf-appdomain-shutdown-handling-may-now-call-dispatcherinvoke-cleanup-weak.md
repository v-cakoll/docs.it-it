---
ms.openlocfilehash: 8b804d23247b95381f3ff83bc12c32215a420fb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614957"
---
### <a name="wpf-appdomain-shutdown-handling-may-now-call-dispatcherinvoke-in-cleanup-of-weak-events"></a>La gestione degli arresti di AppDomain WPF potrebbe ora chiamare Dispatcher. Invoke nella pulizia degli eventi vulnerabili

#### <a name="details"></a>Dettagli

In .NET Framework 4.7.1 e versioni precedenti, WPF crea potenzialmente un oggetto <xref:System.Windows.Threading.Dispatcher?displayProperty=nameWithType> nel thread del finalizzatore .NET durante l'arresto di AppDomain.  Questo problema è stato risolto in .NET Framework 4.7.2 e nelle versioni successive, rendendo la pulitura degli eventi vulnerabili in grado di riconoscere i thread.  Per questo motivo, WPF può chiamare <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> per completare il processo di pulizia. In alcune applicazioni, questa modifica nell'intervallo di tempo del finalizzatore può causare eccezioni durante il dominio AppDomain o l'arresto del processo.  Questo problema si verifica in genere nelle applicazioni che non arrestano correttamente i dispatcher in esecuzione nei thread di lavoro prima dell'arresto del processo o dell'AppDomain.  Tali applicazioni devono prestare attenzione a gestire correttamente la durata dei dispatcher.

#### <a name="suggestion"></a>Suggerimento

In .NET Framework 4.7.2 e versioni successive, gli sviluppatori possono disabilitare questa correzione per ridurre (ma non eliminare) i problemi di temporizzazione che possono verificarsi a causa della modifica della pulizia. Per disabilitare la modifica nella pulizia, usare il flag AppContext seguente.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotInvokeInWeakEventTableShutdownListener=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |
