---
ms.openlocfilehash: 6e5e90a4cfb862b3bfd74ac5a3715e97a736f598
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802466"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>Il flusso di lavoro ora genera l'eccezione originale anziché NullReferenceException in alcuni casi

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6.2 e versioni precedenti, quando il metodo Execute di un'attività flusso di lavoro genera un'eccezione con un valore <code>null</code> per la proprietà <xref:System.Exception.Message>, il runtime del flusso di lavoro System.Activities genera un <xref:System.NullReferenceException?displayProperty=name>, occultando l'eccezione originale. In .NET Framework 4.7 viene generata l'eccezione occultata in precedenza.|
|Suggerimento|Se il codice si basa sulla gestione di <xref:System.NullReferenceException?displayProperty=name>, modificarlo per intercettare le eccezioni che potrebbero essere generate da attività personalizzate.|
|Ambito|Secondario|
|Versione|4.7|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|

