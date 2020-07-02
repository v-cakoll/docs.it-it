---
ms.openlocfilehash: b6cb7edcd6bed50efdf59f3321320ac8cd1b1ab8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617226"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="765ad-101">Alcune API WorkFlow con trascinamento della selezione sono obsolete</span><span class="sxs-lookup"><span data-stu-id="765ad-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="765ad-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="765ad-102">Details</span></span>

<span data-ttu-id="765ad-103">Questa API WorkFlow con trascinamento della selezione è obsoleta e genera avvisi del compilatore se l'app viene ricompilata per la versione 4.5.</span><span class="sxs-lookup"><span data-stu-id="765ad-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="765ad-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="765ad-104">Suggestion</span></span>

<span data-ttu-id="765ad-105">In alternativa è consigliabile usare le nuove API <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> che supportano operazioni con più oggetti.</span><span class="sxs-lookup"><span data-stu-id="765ad-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="765ad-106">In alternativa, è possibile eliminare gli avvisi di compilazione o evitarli usando un compilatore precedente.</span><span class="sxs-lookup"><span data-stu-id="765ad-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="765ad-107">Le API sono ancora supportate.</span><span class="sxs-lookup"><span data-stu-id="765ad-107">The APIs are still supported.</span></span>

| <span data-ttu-id="765ad-108">Nome</span><span class="sxs-lookup"><span data-stu-id="765ad-108">Name</span></span>    | <span data-ttu-id="765ad-109">Valore</span><span class="sxs-lookup"><span data-stu-id="765ad-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="765ad-110">Scope</span><span class="sxs-lookup"><span data-stu-id="765ad-110">Scope</span></span>   | <span data-ttu-id="765ad-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="765ad-111">Minor</span></span>       |
| <span data-ttu-id="765ad-112">Version</span><span class="sxs-lookup"><span data-stu-id="765ad-112">Version</span></span> | <span data-ttu-id="765ad-113">4.5</span><span class="sxs-lookup"><span data-stu-id="765ad-113">4.5</span></span>         |
| <span data-ttu-id="765ad-114">Type</span><span class="sxs-lookup"><span data-stu-id="765ad-114">Type</span></span>    | <span data-ttu-id="765ad-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="765ad-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="765ad-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="765ad-116">Affected APIs</span></span>

- <xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType>
