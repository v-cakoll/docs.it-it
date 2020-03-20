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
ms.openlocfilehash: 0f52703e4fe127daa40f220280f084b2026580cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186946"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="06bec-102">Procedura: posizionare un oggetto ToolTip</span><span class="sxs-lookup"><span data-stu-id="06bec-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="06bec-103">In questo esempio viene illustrato come specificare la posizione di una descrizione comando sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="06bec-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06bec-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="06bec-104">Example</span></span>  
 <span data-ttu-id="06bec-105">È possibile posizionare una descrizione comando utilizzando un set <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> di cinque proprietà definite in entrambe le classi e .</span><span class="sxs-lookup"><span data-stu-id="06bec-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="06bec-106">Nella tabella seguente vengono illustrati questi due set di cinque proprietà e vengono forniti collegamenti alla relativa documentazione di riferimento in base alla classe.</span><span class="sxs-lookup"><span data-stu-id="06bec-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="06bec-107">Proprietà della descrizione comando corrispondenti in base alla classe</span><span class="sxs-lookup"><span data-stu-id="06bec-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="06bec-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>proprietà della classe</span><span class="sxs-lookup"><span data-stu-id="06bec-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="06bec-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>proprietà della classe</span><span class="sxs-lookup"><span data-stu-id="06bec-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="06bec-110">Se si definisce il contenuto <xref:System.Windows.Controls.ToolTip> di una descrizione comandi utilizzando un oggetto , è possibile utilizzare le proprietà di entrambe le classi; tuttavia, <xref:System.Windows.Controls.ToolTipService> le proprietà hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="06bec-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="06bec-111">Utilizzare <xref:System.Windows.Controls.ToolTipService> le proprietà per le descrizioni comandi che non sono definite come <xref:System.Windows.Controls.ToolTip> oggetti.</span><span class="sxs-lookup"><span data-stu-id="06bec-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="06bec-112">Nelle illustrazioni seguenti viene illustrato come posizionare una descrizione comando utilizzando queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="06bec-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="06bec-113">Sebbene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] negli esempi di queste illustrazioni venga illustrato come <xref:System.Windows.Controls.ToolTip> impostare le proprietà <xref:System.Windows.Controls.ToolTipService> definite dalla classe, le proprietà corrispondenti della classe seguono le stesse regole di layout.</span><span class="sxs-lookup"><span data-stu-id="06bec-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="06bec-114">Per ulteriori informazioni sui possibili valori per la proprietà Placement, consultate [Comportamento del posizionamento popup.](popup-placement-behavior.md)</span><span class="sxs-lookup"><span data-stu-id="06bec-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  

 <span data-ttu-id="06bec-115">L'immagine seguente mostra il posizionamento delle descrizioni comandi utilizzando la proprietà Posizionamento:</span><span class="sxs-lookup"><span data-stu-id="06bec-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![Diagramma che mostra il posizionamento della descrizione comando tramite la proprietà Placement.Diagram showing ToolTip placement by using the Placement property.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 <span data-ttu-id="06bec-117">L'immagine seguente mostra il posizionamento delle descrizioni comandi utilizzando le proprietà Placement e PlacementRectangle:</span><span class="sxs-lookup"><span data-stu-id="06bec-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>

 ![Diagramma che mostra il posizionamento della descrizione comando tramite una proprietà PlacementRectangle.Diagram showing ToolTip placement by using a PlacementRectangle property.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 <span data-ttu-id="06bec-119">L'immagine seguente mostra il posizionamento delle descrizioni comandi utilizzando le proprietà Placement, PlacementRectangle e Offset:</span><span class="sxs-lookup"><span data-stu-id="06bec-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>
  
 ![Diagramma che mostra il posizionamento della descrizione comando tramite la proprietà Offset.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="06bec-121">Nell'esempio seguente viene <xref:System.Windows.Controls.ToolTip> illustrato come utilizzare le proprietà per <xref:System.Windows.Controls.ToolTip> specificare la posizione di una descrizione comando il cui contenuto è un oggetto .</span><span class="sxs-lookup"><span data-stu-id="06bec-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="06bec-122">Nell'esempio seguente viene <xref:System.Windows.Controls.ToolTipService> illustrato come utilizzare le proprietà per specificare la posizione di una descrizione comando il cui contenuto non è un <xref:System.Windows.Controls.ToolTip> oggetto.</span><span class="sxs-lookup"><span data-stu-id="06bec-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="06bec-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06bec-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="06bec-124">Argomenti relativi alle procedure</span><span class="sxs-lookup"><span data-stu-id="06bec-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="06bec-125">Panoramica sul controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="06bec-125">ToolTip Overview</span></span>](tooltip-overview.md)
