---
title: 'Procedura: posizionare un oggetto ToolTip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: e51be52301197a66ef49339245e60404d823b36c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512293"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="77582-102">Procedura: posizionare un oggetto ToolTip</span><span class="sxs-lookup"><span data-stu-id="77582-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="77582-103">In questo esempio viene illustrato come specificare la posizione della descrizione comando sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="77582-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77582-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="77582-104">Example</span></span>  
 <span data-ttu-id="77582-105">È possibile posizionare una descrizione comando con un set di cinque proprietà definite in entrambe le <xref:System.Windows.Controls.ToolTip> e <xref:System.Windows.Controls.ToolTipService> classi.</span><span class="sxs-lookup"><span data-stu-id="77582-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="77582-106">Nella tabella seguente mostra questi due set di cinque proprietà e vengono forniti collegamenti alla relativa documentazione di riferimento in base alla classe.</span><span class="sxs-lookup"><span data-stu-id="77582-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="77582-107">Proprietà della descrizione comando corrispondente in base alla classe</span><span class="sxs-lookup"><span data-stu-id="77582-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="77582-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> proprietà della classe</span><span class="sxs-lookup"><span data-stu-id="77582-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="77582-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> proprietà della classe</span><span class="sxs-lookup"><span data-stu-id="77582-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="77582-110">Se si definisce il contenuto di una descrizione comando con un <xref:System.Windows.Controls.ToolTip> dell'oggetto, è possibile usare le proprietà delle classi, tuttavia, il <xref:System.Windows.Controls.ToolTipService> proprietà hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="77582-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="77582-111">Usare la <xref:System.Windows.Controls.ToolTipService> delle proprietà per le descrizioni comandi che non sono definite come <xref:System.Windows.Controls.ToolTip> oggetti.</span><span class="sxs-lookup"><span data-stu-id="77582-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="77582-112">Le illustrazioni seguenti mostrano come posizionare un oggetto tooltip utilizzando queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="77582-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="77582-113">Anche se, il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] negli esempi di queste illustrazioni mostrano come impostare le proprietà definite dal <xref:System.Windows.Controls.ToolTip> classe, le proprietà corrispondenti del <xref:System.Windows.Controls.ToolTipService> classe seguono le stesse regole di layout.</span><span class="sxs-lookup"><span data-stu-id="77582-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="77582-114">Per altre informazioni sui valori possibili per la proprietà di posizionamento, vedere [comportamento del posizionamento di Popup](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="77582-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="77582-115">![Posizionamento di ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="77582-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="77582-116">Posizionamento di ToolTip mediante la proprietà di posizionamento</span><span class="sxs-lookup"><span data-stu-id="77582-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="77582-117">![Posizionamento di ToolTip mediante un rettangolo di selezione host](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="77582-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="77582-118">Posizionamento di ToolTip mediante le proprietà di posizionamento e PlacementRectangle</span><span class="sxs-lookup"><span data-stu-id="77582-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="77582-119">![Diagramma di posizionamento di ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="77582-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="77582-120">Posizionamento di ToolTip mediante le proprietà di posizionamento e PlacementRectangle Offset</span><span class="sxs-lookup"><span data-stu-id="77582-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="77582-121">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTip> delle proprietà per specificare la posizione della descrizione comando il cui contenuto è un <xref:System.Windows.Controls.ToolTip> oggetto.</span><span class="sxs-lookup"><span data-stu-id="77582-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="77582-122">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTipService> delle proprietà per specificare la posizione della descrizione comando il cui contenuto non è un <xref:System.Windows.Controls.ToolTip> oggetto.</span><span class="sxs-lookup"><span data-stu-id="77582-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="77582-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77582-123">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="77582-124">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="77582-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="77582-125">Panoramica sul controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="77582-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [<span data-ttu-id="77582-126">Usare il ContextMenuService e ToolTipService</span><span class="sxs-lookup"><span data-stu-id="77582-126">Use the ContextMenuService and ToolTipService</span></span>](https://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
