---
ms.openlocfilehash: 97a92c6bce80b93e9a8bdd863bf881631eaffb27
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804684"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="39c55-101">WorkflowDesigner.Load non rimuove la proprietà del simbolo</span><span class="sxs-lookup"><span data-stu-id="39c55-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

|   |   |
|---|---|
|<span data-ttu-id="39c55-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="39c55-102">Details</span></span>|<span data-ttu-id="39c55-103">Se si usa .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro e si carica un flusso di lavoro 3.5 riallocato con il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load>, viene generata un'eccezione <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> durante il salvataggio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="39c55-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> is thrown while saving the workflow.</span></span>|
|<span data-ttu-id="39c55-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="39c55-104">Suggestion</span></span>|<span data-ttu-id="39c55-105">Questo bug si manifesta solo quando si seleziona .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro, quindi è possibile evitarlo impostando <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> su .NET Framework 4.0. In alternativa il problema può essere evitato usando il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> per caricare il flusso di lavoro, invece di <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span><span class="sxs-lookup"><span data-stu-id="39c55-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>|
|<span data-ttu-id="39c55-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="39c55-106">Scope</span></span>|<span data-ttu-id="39c55-107">Principale</span><span class="sxs-lookup"><span data-stu-id="39c55-107">Major</span></span>|
|<span data-ttu-id="39c55-108">Versione</span><span class="sxs-lookup"><span data-stu-id="39c55-108">Version</span></span>|<span data-ttu-id="39c55-109">4.5</span><span class="sxs-lookup"><span data-stu-id="39c55-109">4.5</span></span>|
|<span data-ttu-id="39c55-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="39c55-110">Type</span></span>|<span data-ttu-id="39c55-111">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="39c55-111">Retargeting</span></span>|
|<span data-ttu-id="39c55-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="39c55-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

