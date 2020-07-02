---
ms.openlocfilehash: 78faa5f4008b41bac75c94ce09a58c8227e5b485
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614449"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a>CurrentCulture e CurrentUICulture vengono propagate tra le attività

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6, le proprietà <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> sono archiviate in <xref:System.Threading.ExecutionContext?displayProperty=fullName> del thread, che viene propagato tra le operazioni asincrone. Ciò significa che le modifiche apportate a <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> verranno riflesse nelle attività che vengono eseguite in un secondo momento in modo asincrono. Questo comportamento è diverso rispetto alle versioni precedenti di .NET Framework, in cui <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> vengono reimpostate in tutte le attività asincrone.

#### <a name="suggestion"></a>Suggerimento

Le app interessate da questa modifica possono aggirarla impostando in modo esplicito il valore <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> desiderato come prima operazione in un'attività asincrona. In alternativa, è possibile acconsentire esplicitamente al comportamento precedente (ovvero non propagare <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) impostando la seguente opzione di compatibilità:

```csharp
AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);
```

Il problema è stato risolto da WPF in .NET Framework 4.6.2. È stato risolto anche in .NET Framework 4.6 e 4.6.1 mediante [KB 3139549](https://support.microsoft.com/kb/3139549). Le applicazioni destinate a .NET Framework 4.6 o versioni successive otterranno automaticamente il comportamento corretto nelle applicazioni WPF: le proprietà <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> vengono mantenute tra operazioni Dispatcher.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType>
