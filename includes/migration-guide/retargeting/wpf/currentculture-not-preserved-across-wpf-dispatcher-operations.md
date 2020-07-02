---
ms.openlocfilehash: bd656478a55856e676853e57f3e7386ea0aa0211
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614826"
---
### <a name="currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>CurrentCulture non viene mantenuto nelle operazioni Dispatcher di WPF

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6, le modifiche apportate a <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> all'interno di un <xref:System.Windows.Threading.Dispatcher?displayProperty=fullName> vanno perdute al termine dell'operazione del dispatcher. In modo analogo, le modifiche apportate a <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> all'esterno di un'operazione di Dispatcher potrebbero non essere disponibili quando viene eseguita l'operazione. In pratica, ciò significa che le modifiche <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> potrebbero non essere trasferite tra i callback UI di WPF e altro codice in un'applicazione WPF. Questo è dovuto a una modifica in <xref:System.Threading.ExecutionContext?displayProperty=fullName> in seguito alla quale <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> vengono archiviati nel contesto di esecuzione a partire dalle app destinate a .NET Framework 4.6. Le operazioni del dispatcher WPF archiviano il contesto di esecuzione usato per avviare l'operazione e ripristinano il contesto precedente dopo il completamento dell'operazione. Dato che <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> fanno ora parte di tale contesto, le modifiche di questi elementi all'interno di un'operazione di Dispatcher non vengono mantenute all'esterno dell'operazione.

#### <a name="suggestion"></a>Suggerimento

Le app interessate da questa modifica possono risolvere il problema archiviando i valori <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> desiderati in un campo e controllando che siano impostati i valori corretti di <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> in tutti i corpi delle operazioni del dispatcher (inclusi i gestori di callback degli eventi dell'interfaccia utente). In alternativa, dato che la modifica di ExecutionContext sottostante questa modifica WPF influisce solo sulle app destinate a .NET Framework 4.6 o versione successiva, è possibile evitare il problema destinando le app a .NET Framework 4.5.2. Anche le app destinate a .NET Framework 4.6 o versioni successive possono evitare il problema impostando la seguente opzione di compatibilità:

<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;Switch.System.Globalization.NoAsyncCurrentCulture&quot;, true);&#13;&#10;</code></pre>

Il problema è stato risolto da WPF in .NET Framework 4.6.2. È stato risolto anche in .NET Framework 4.6 e 4.6.1 mediante [KB 3139549](https://support.microsoft.com/kb/3139549). Le applicazioni destinate a .NET Framework 4.6 o versioni successive otterranno automaticamente il comportamento corretto nelle applicazioni WPF: le proprietà <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> vengono mantenute tra operazioni Dispatcher.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6         |
| Type    | Ridestinazione |
