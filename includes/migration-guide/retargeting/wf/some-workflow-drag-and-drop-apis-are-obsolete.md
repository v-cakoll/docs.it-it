---
ms.openlocfilehash: 297af393e86c65e84ea7271d98eab36dbc6dbb0e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774383"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="54ab5-101">Alcune API WorkFlow con trascinamento della selezione sono obsolete</span><span class="sxs-lookup"><span data-stu-id="54ab5-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="54ab5-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="54ab5-102">Details</span></span>|<span data-ttu-id="54ab5-103">Questa API WorkFlow con trascinamento della selezione è obsoleta e genera avvisi del compilatore se l'app viene ricompilata per la versione 4.5.</span><span class="sxs-lookup"><span data-stu-id="54ab5-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>|
|<span data-ttu-id="54ab5-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="54ab5-104">Suggestion</span></span>|<span data-ttu-id="54ab5-105">In alternativa è consigliabile usare le nuove API <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name> che supportano operazioni con più oggetti.</span><span class="sxs-lookup"><span data-stu-id="54ab5-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="54ab5-106">In alternativa, è possibile eliminare gli avvisi di compilazione o evitarli usando un compilatore precedente.</span><span class="sxs-lookup"><span data-stu-id="54ab5-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="54ab5-107">Le API sono ancora supportate.</span><span class="sxs-lookup"><span data-stu-id="54ab5-107">The APIs are still supported.</span></span>|
|<span data-ttu-id="54ab5-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="54ab5-108">Scope</span></span>|<span data-ttu-id="54ab5-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="54ab5-109">Minor</span></span>|
|<span data-ttu-id="54ab5-110">Versione</span><span class="sxs-lookup"><span data-stu-id="54ab5-110">Version</span></span>|<span data-ttu-id="54ab5-111">4.5</span><span class="sxs-lookup"><span data-stu-id="54ab5-111">4.5</span></span>|
|<span data-ttu-id="54ab5-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="54ab5-112">Type</span></span>|<span data-ttu-id="54ab5-113">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="54ab5-113">Retargeting</span></span>|
|<span data-ttu-id="54ab5-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="54ab5-114">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType></li></ul>|
