---
ms.openlocfilehash: 5ba2ddb76ab946339449246840667ba4a48e9c66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620244"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>Le eccezioni che si verificano durante l'elaborazione non osservata in System.Threading.Tasks.Task non si propagano più al thread finalizzatore

#### <a name="details"></a>Dettagli

Poiché la classe <xref:System.Threading.Tasks.Task?displayProperty=fullName> rappresenta un'operazione asincrona, intercetta tutte le eccezioni non gravi che si verificano durante l'elaborazione asincrona. In .NET Framework 4.5, se un'eccezione non viene osservata e il codice non è mai in attesa nell'attività, tale eccezione non verrà più propagata nel thread finalizzatore e il processo verrà arrestato in modo anomalo durante un'operazione di Garbage Collection. Questa modifica migliora l'affidabilità delle applicazioni che usano la classe Task per eseguire l'elaborazione asincrona non osservata.

#### <a name="suggestion"></a>Suggerimento

Se un'applicazione dipende dalla propagazione delle eccezioni asincrone non osservate al thread finalizzatore, il comportamento precedente può essere ripristinato specificando un gestore appropriato per l'evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> o impostando un [elemento di configurazione di runtime](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType></li></ul>|
