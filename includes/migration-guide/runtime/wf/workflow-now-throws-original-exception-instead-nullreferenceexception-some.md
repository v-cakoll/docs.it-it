---
ms.openlocfilehash: 6e5e90a4cfb862b3bfd74ac5a3715e97a736f598
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802466"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="af00c-101">Il flusso di lavoro ora genera l'eccezione originale anziché NullReferenceException in alcuni casi</span><span class="sxs-lookup"><span data-stu-id="af00c-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

|   |   |
|---|---|
|<span data-ttu-id="af00c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="af00c-102">Details</span></span>|<span data-ttu-id="af00c-103">In .NET Framework 4.6.2 e versioni precedenti, quando il metodo Execute di un'attività flusso di lavoro genera un'eccezione con un valore <code>null</code> per la proprietà <xref:System.Exception.Message>, il runtime del flusso di lavoro System.Activities genera un <xref:System.NullReferenceException?displayProperty=name>, occultando l'eccezione originale. In .NET Framework 4.7 viene generata l'eccezione occultata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="af00c-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=name>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>|
|<span data-ttu-id="af00c-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="af00c-104">Suggestion</span></span>|<span data-ttu-id="af00c-105">Se il codice si basa sulla gestione di <xref:System.NullReferenceException?displayProperty=name>, modificarlo per intercettare le eccezioni che potrebbero essere generate da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="af00c-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=name>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>|
|<span data-ttu-id="af00c-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="af00c-106">Scope</span></span>|<span data-ttu-id="af00c-107">Secondario</span><span class="sxs-lookup"><span data-stu-id="af00c-107">Minor</span></span>|
|<span data-ttu-id="af00c-108">Versione</span><span class="sxs-lookup"><span data-stu-id="af00c-108">Version</span></span>|<span data-ttu-id="af00c-109">4.7</span><span class="sxs-lookup"><span data-stu-id="af00c-109">4.7</span></span>|
|<span data-ttu-id="af00c-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="af00c-110">Type</span></span>|<span data-ttu-id="af00c-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="af00c-111">Runtime</span></span>|
|<span data-ttu-id="af00c-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="af00c-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|

