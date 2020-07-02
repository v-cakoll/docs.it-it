---
ms.openlocfilehash: 52406f1e4ea4eda417909e52cf6529631cb0ae33
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620221"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>Modifica del comportamento per i metodi Task.WaitAll con argomenti di timeout

#### <a name="details"></a>Dettagli

In .NET Framework 4.5 il comportamento di <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> è stato reso più coerente. In .NET Framework 4 questi metodi avevano un comportamento non coerente. Alla scadenza del timeout, se una o più attività sono state completate o annullate prima della chiamata al metodo, il metodo genera un'eccezione <xref:System.AggregateException?displayProperty=fullName>. Alla scadenza del timeout, se nessuna attività è stata completata o annullata prima della chiamata al metodo, ma una o più attività sono entrate in questi stati dopo la chiamata al metodo, il metodo restituisce false.<br/><br/>In .NET Framework 4.5 questi overload del metodo ora restituiscono false in presenza di attività ancora in esecuzione allo scadere dell'intervallo di timeout e generano un'eccezione <xref:System.AggregateException?displayProperty=fullName> solo se un'attività di input è stata annullata, indipendentemente dal fatto che sia stata annullata prima o dopo la chiamata del metodo, e non ci sono altre attività ancora in esecuzione.

#### <a name="suggestion"></a>Suggerimento

Se veniva rilevata un'eccezione <xref:System.AggregateException?displayProperty=fullName> come mezzo per rilevare un'attività annullata prima della chiamata al metodo <xref:System.Threading.Tasks.Task.WaitAll%2A>, il codice doveva invece eseguire lo stesso rilevamento tramite la proprietà <xref:System.Threading.Tasks.Task.IsCanceled%2A> (ad esempio: .Any(t = &gt; t.IsCanceled)), in quanto in questo caso .NET Framework 4.6 genera un'eccezione solo se tutte le attività attese vengono completate prima del timeout.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType></li></ul>|
