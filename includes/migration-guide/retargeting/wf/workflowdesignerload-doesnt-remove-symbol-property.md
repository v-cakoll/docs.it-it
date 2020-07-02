---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616091"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="11acf-101">WorkflowDesigner.Load non rimuove la proprietà del simbolo</span><span class="sxs-lookup"><span data-stu-id="11acf-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

#### <a name="details"></a><span data-ttu-id="11acf-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="11acf-102">Details</span></span>

<span data-ttu-id="11acf-103">Se si usa .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro e si carica un flusso di lavoro 3.5 riallocato con il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load>, viene generata un'eccezione <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> durante il salvataggio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="11acf-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> is thrown while saving the workflow.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="11acf-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="11acf-104">Suggestion</span></span>

<span data-ttu-id="11acf-105">Questo bug si manifesta solo quando si seleziona .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro, quindi è possibile evitarlo impostando `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` su .NET Framework 4.0. In alternativa il problema può essere evitato usando il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> per caricare il flusso di lavoro, invece di <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span><span class="sxs-lookup"><span data-stu-id="11acf-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>

| <span data-ttu-id="11acf-106">Nome</span><span class="sxs-lookup"><span data-stu-id="11acf-106">Name</span></span>    | <span data-ttu-id="11acf-107">Valore</span><span class="sxs-lookup"><span data-stu-id="11acf-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="11acf-108">Scope</span><span class="sxs-lookup"><span data-stu-id="11acf-108">Scope</span></span>   | <span data-ttu-id="11acf-109">Principale</span><span class="sxs-lookup"><span data-stu-id="11acf-109">Major</span></span>       |
| <span data-ttu-id="11acf-110">Version</span><span class="sxs-lookup"><span data-stu-id="11acf-110">Version</span></span> | <span data-ttu-id="11acf-111">4.5</span><span class="sxs-lookup"><span data-stu-id="11acf-111">4.5</span></span>         |
| <span data-ttu-id="11acf-112">Type</span><span class="sxs-lookup"><span data-stu-id="11acf-112">Type</span></span>    | <span data-ttu-id="11acf-113">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="11acf-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="11acf-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="11acf-114">Affected APIs</span></span>

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>
