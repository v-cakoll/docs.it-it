---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621244"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>Il flusso di lavoro ora genera l'eccezione originale anziché NullReferenceException in alcuni casi

#### <a name="details"></a>Dettagli

In .NET Framework 4.6.2 e versioni precedenti, quando il metodo Execute di un'attività flusso di lavoro genera un'eccezione con un valore <code>null</code> per la proprietà <xref:System.Exception.Message>, il runtime del flusso di lavoro System.Activities genera un <xref:System.NullReferenceException?displayProperty=fullName>, occultando l'eccezione originale. In .NET Framework 4.7 viene generata l'eccezione occultata in precedenza.

#### <a name="suggestion"></a>Suggerimento

Se il codice si basa sulla gestione di <xref:System.NullReferenceException?displayProperty=fullName>, modificarlo per intercettare le eccezioni che potrebbero essere generate da attività personalizzate.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.7|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
