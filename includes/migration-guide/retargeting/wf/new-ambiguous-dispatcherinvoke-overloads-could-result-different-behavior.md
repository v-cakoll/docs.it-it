---
ms.openlocfilehash: 80e61d4dd5b8d4754a39e95e37475fefff57fcbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617173"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>Nuovi overload per Dispatcher.Invoke (ambigui) potrebbe causare un comportamento diverso

#### <a name="details"></a>Dettagli

.NET Framework 4.5 aggiunge nuovi overload a <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> che includono un parametro di tipo <xref:System.Action>. Se il codice esistente viene ricompilato, i compilatori possono risolvere le chiamate ai metodi Dispatcher.Invoke con un parametro <xref:System.Delegate> come chiamate ai metodi Dispatcher.Invoke con un parametro <xref:System.Action>. Se una chiamata a un overload di Dispatcher.Invoke con un parametro <xref:System.Delegate> viene risolta come una chiamata a un overload di Dispatcher.Invoke con un parametro <xref:System.Action>, è possibile che si verifichino le seguenti differenze nel comportamento:

- Se si verifica un'eccezione, gli eventi <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> e <xref:System.Windows.Threading.Dispatcher.UnhandledException> non vengono generati. Al contrario, le eccezioni vengono gestite dall'evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName>.
- Le chiamate ad alcuni membri, come <xref:System.Windows.Threading.DispatcherOperation.Result>, si bloccano fino a quando l'operazione non verrà completata.

#### <a name="suggestion"></a>Suggerimento

Per evitare ambiguità (e potenziali differenze nella gestione delle eccezioni o per i comportamenti di blocco), il codice che chiama Dispatcher.Invoke può passare un oggetto vuoto [] come secondo parametro della chiamata Invoke per essere certi di usare l'overload del metodo .NET Framework 4.0.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.5         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
