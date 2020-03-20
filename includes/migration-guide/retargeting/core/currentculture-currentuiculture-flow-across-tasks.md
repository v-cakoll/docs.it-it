---
ms.openlocfilehash: efe8a2dd98865f6a24b65ce0f08eb0c574b708f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804546"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a>CurrentCulture e CurrentUICulture vengono propagate tra le attività

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6, le proprietà <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> sono archiviate in <xref:System.Threading.ExecutionContext?displayProperty=name> del thread, che viene propagato tra le operazioni asincrone. Ciò significa che le modifiche apportate a <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> verranno riflesse nelle attività che vengono eseguite in un secondo momento in modo asincrono. Questo comportamento è diverso rispetto alle versioni precedenti di .NET Framework, in cui <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> vengono reimpostate in tutte le attività asincrone.|
|Suggerimento|Le app interessate da questa modifica possono aggirarla impostando in modo esplicito il valore <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> desiderato come prima operazione in un'attività asincrona. In alternativa, è possibile acconsentire esplicitamente al comportamento precedente (ovvero non propagare <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name>) impostando la seguente opzione di compatibilità:<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;Switch.System.Globalization.NoAsyncCurrentCulture&quot;, true);&#13;&#10;</code></pre>Il problema è stato risolto da WPF in .NET Framework 4.6.2. È stato risolto anche in .NET Framework 4.6 e 4.6.1 mediante [KB 3139549](https://support.microsoft.com/kb/3139549). Le applicazioni destinate a .NET Framework 4.6 o versioni successive otterranno automaticamente il comportamento corretto nelle applicazioni WPF: le proprietà <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> vengono mantenute tra operazioni Dispatcher.|
|Scope|Minorenne|
|Versione|4.6|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType></li><li><xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType></li><li><xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType></li><li><xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType></li></ul>|
