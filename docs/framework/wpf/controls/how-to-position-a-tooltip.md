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
ms.openlocfilehash: 218d8814cf75cd80a63c94397ed00e92c6a9a8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555938"
---
# <a name="how-to-position-a-tooltip"></a>Procedura: posizionare un oggetto ToolTip
In questo esempio viene illustrato come specificare la posizione di una descrizione comando sullo schermo.  
  
## <a name="example"></a>Esempio  
 È possibile posizionare una descrizione comando con un set di cinque proprietà definite in entrambe le <xref:System.Windows.Controls.ToolTip> e <xref:System.Windows.Controls.ToolTipService> classi. Nella tabella seguente mostra questi due set di cinque proprietà e vengono forniti collegamenti alla relativa documentazione di riferimento in base alla classe.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Proprietà di descrizione comandi corrispondenti in base alla classe  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> proprietà della classe|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> proprietà della classe|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Se si definisce il contenuto di una descrizione comando con un <xref:System.Windows.Controls.ToolTip> dell'oggetto, è possibile utilizzare le proprietà della classe; tuttavia, il <xref:System.Windows.Controls.ToolTipService> proprietà hanno la precedenza. Utilizzare il <xref:System.Windows.Controls.ToolTipService> proprietà per le descrizioni comandi che non sono definite come <xref:System.Windows.Controls.ToolTip> oggetti.  
  
 Le illustrazioni seguenti mostrano come posizionare una descrizione comando utilizzando queste proprietà. Anche se, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] negli esempi di queste illustrazioni viene illustrato come impostare le proprietà definite dal <xref:System.Windows.Controls.ToolTip> classe, le proprietà corrispondenti del <xref:System.Windows.Controls.ToolTipService> classe seguono le stesse regole di layout. Per ulteriori informazioni sui possibili valori della proprietà Placement, vedere [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  
  
 ![Posizionamento di ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
Posizionamento di ToolTip mediante la proprietà di posizionamento  
  
 ![Posizionamento di ToolTip mediante un rettangolo di selezione host](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
Posizionamento di ToolTip mediante le proprietà di posizionamento e PlacementRectangle  
  
 ![Diagramma di posizionamento di ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
Posizionamento di ToolTip mediante le proprietà Placement, PlacementRectangle e Offset  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTip> le proprietà per specificare la posizione di una descrizione comando il cui contenuto è un <xref:System.Windows.Controls.ToolTip> oggetto.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTipService> le proprietà per specificare la posizione di una descrizione comando il cui contenuto non è un <xref:System.Windows.Controls.ToolTip> oggetto.  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [Panoramica sul controllo ToolTip](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [Utilizzare le ContextMenuService e ToolTipService](http://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
