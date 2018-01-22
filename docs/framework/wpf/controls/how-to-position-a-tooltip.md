---
title: 'Procedura: posizionare un oggetto ToolTip'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc81fa247f21448a4ccbd62baccb72c0ec14bb31
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="4c256-102">Procedura: posizionare un oggetto ToolTip</span><span class="sxs-lookup"><span data-stu-id="4c256-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="4c256-103">In questo esempio viene illustrato come specificare la posizione di una descrizione comando sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="4c256-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c256-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c256-104">Example</span></span>  
 <span data-ttu-id="4c256-105">È possibile posizionare una descrizione comando con un set di cinque proprietà definite in entrambe le <xref:System.Windows.Controls.ToolTip> e <xref:System.Windows.Controls.ToolTipService> classi.</span><span class="sxs-lookup"><span data-stu-id="4c256-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="4c256-106">Nella tabella seguente mostra questi due set di cinque proprietà e vengono forniti collegamenti alla relativa documentazione di riferimento in base alla classe.</span><span class="sxs-lookup"><span data-stu-id="4c256-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="4c256-107">Proprietà di descrizione comandi corrispondenti in base alla classe</span><span class="sxs-lookup"><span data-stu-id="4c256-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="4c256-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>proprietà della classe</span><span class="sxs-lookup"><span data-stu-id="4c256-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="4c256-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>proprietà della classe</span><span class="sxs-lookup"><span data-stu-id="4c256-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="4c256-110">Se si definisce il contenuto di una descrizione comando con un <xref:System.Windows.Controls.ToolTip> dell'oggetto, è possibile utilizzare le proprietà della classe; tuttavia, il <xref:System.Windows.Controls.ToolTipService> proprietà hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="4c256-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="4c256-111">Utilizzare il <xref:System.Windows.Controls.ToolTipService> proprietà per le descrizioni comandi che non sono definite come <xref:System.Windows.Controls.ToolTip> oggetti.</span><span class="sxs-lookup"><span data-stu-id="4c256-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="4c256-112">Le illustrazioni seguenti mostrano come posizionare una descrizione comando utilizzando queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c256-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="4c256-113">Anche se, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] negli esempi di queste illustrazioni viene illustrato come impostare le proprietà definite dal <xref:System.Windows.Controls.ToolTip> classe, le proprietà corrispondenti del <xref:System.Windows.Controls.ToolTipService> classe seguono le stesse regole di layout.</span><span class="sxs-lookup"><span data-stu-id="4c256-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="4c256-114">Per ulteriori informazioni sui possibili valori della proprietà Placement, vedere [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="4c256-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="4c256-115">![Posizionamento di ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="4c256-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="4c256-116">Posizionamento di ToolTip mediante la proprietà di posizionamento</span><span class="sxs-lookup"><span data-stu-id="4c256-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="4c256-117">![Posizionamento di ToolTip mediante un rettangolo di posizionamento](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="4c256-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="4c256-118">Posizionamento di ToolTip mediante le proprietà di posizionamento e PlacementRectangle</span><span class="sxs-lookup"><span data-stu-id="4c256-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="4c256-119">![Diagramma di posizionamento di ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="4c256-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="4c256-120">Posizionamento di ToolTip mediante le proprietà Placement, PlacementRectangle e Offset</span><span class="sxs-lookup"><span data-stu-id="4c256-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="4c256-121">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTip> le proprietà per specificare la posizione di una descrizione comando il cui contenuto è un <xref:System.Windows.Controls.ToolTip> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4c256-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="4c256-122">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTipService> le proprietà per specificare la posizione di una descrizione comando il cui contenuto non è un <xref:System.Windows.Controls.ToolTip> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4c256-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="4c256-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c256-123">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="4c256-124">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="4c256-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="4c256-125">Panoramica sul controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="4c256-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [<span data-ttu-id="4c256-126">Utilizzare la ContextMenuService e ToolTipService</span><span class="sxs-lookup"><span data-stu-id="4c256-126">Use the ContextMenuService and ToolTipService</span></span>](http://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
