---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621244"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="630a6-101">Il flusso di lavoro ora genera l'eccezione originale anziché NullReferenceException in alcuni casi</span><span class="sxs-lookup"><span data-stu-id="630a6-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="630a6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="630a6-102">Details</span></span>

<span data-ttu-id="630a6-103">In .NET Framework 4.6.2 e versioni precedenti, quando il metodo Execute di un'attività flusso di lavoro genera un'eccezione con un valore <code>null</code> per la proprietà <xref:System.Exception.Message>, il runtime del flusso di lavoro System.Activities genera un <xref:System.NullReferenceException?displayProperty=fullName>, occultando l'eccezione originale. In .NET Framework 4.7 viene generata l'eccezione occultata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="630a6-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="630a6-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="630a6-104">Suggestion</span></span>

<span data-ttu-id="630a6-105">Se il codice si basa sulla gestione di <xref:System.NullReferenceException?displayProperty=fullName>, modificarlo per intercettare le eccezioni che potrebbero essere generate da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="630a6-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="630a6-106">Nome</span><span class="sxs-lookup"><span data-stu-id="630a6-106">Name</span></span>    | <span data-ttu-id="630a6-107">Valore</span><span class="sxs-lookup"><span data-stu-id="630a6-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="630a6-108">Scope</span><span class="sxs-lookup"><span data-stu-id="630a6-108">Scope</span></span>   |<span data-ttu-id="630a6-109">Minorenne</span><span class="sxs-lookup"><span data-stu-id="630a6-109">Minor</span></span>|
|<span data-ttu-id="630a6-110">Version</span><span class="sxs-lookup"><span data-stu-id="630a6-110">Version</span></span>|<span data-ttu-id="630a6-111">4.7</span><span class="sxs-lookup"><span data-stu-id="630a6-111">4.7</span></span>|
|<span data-ttu-id="630a6-112">Type</span><span class="sxs-lookup"><span data-stu-id="630a6-112">Type</span></span>|<span data-ttu-id="630a6-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="630a6-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="630a6-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="630a6-114">Affected APIs</span></span>

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
