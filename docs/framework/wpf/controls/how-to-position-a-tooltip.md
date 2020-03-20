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
# <a name="how-to-position-a-tooltip"></a>Procedura: posizionare un oggetto ToolTip
In questo esempio viene illustrato come specificare la posizione di una descrizione comando sullo schermo.  
  
## <a name="example"></a>Esempio  
 È possibile posizionare una descrizione comando utilizzando un set <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> di cinque proprietà definite in entrambe le classi e . Nella tabella seguente vengono illustrati questi due set di cinque proprietà e vengono forniti collegamenti alla relativa documentazione di riferimento in base alla classe.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Proprietà della descrizione comando corrispondenti in base alla classe  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>proprietà della classe|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>proprietà della classe|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Se si definisce il contenuto <xref:System.Windows.Controls.ToolTip> di una descrizione comandi utilizzando un oggetto , è possibile utilizzare le proprietà di entrambe le classi; tuttavia, <xref:System.Windows.Controls.ToolTipService> le proprietà hanno la precedenza. Utilizzare <xref:System.Windows.Controls.ToolTipService> le proprietà per le descrizioni comandi che non sono definite come <xref:System.Windows.Controls.ToolTip> oggetti.  
  
 Nelle illustrazioni seguenti viene illustrato come posizionare una descrizione comando utilizzando queste proprietà. Sebbene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] negli esempi di queste illustrazioni venga illustrato come <xref:System.Windows.Controls.ToolTip> impostare le proprietà <xref:System.Windows.Controls.ToolTipService> definite dalla classe, le proprietà corrispondenti della classe seguono le stesse regole di layout. Per ulteriori informazioni sui possibili valori per la proprietà Placement, consultate [Comportamento del posizionamento popup.](popup-placement-behavior.md)  

 L'immagine seguente mostra il posizionamento delle descrizioni comandi utilizzando la proprietà Posizionamento:  
  
 ![Diagramma che mostra il posizionamento della descrizione comando tramite la proprietà Placement.Diagram showing ToolTip placement by using the Placement property.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 L'immagine seguente mostra il posizionamento delle descrizioni comandi utilizzando le proprietà Placement e PlacementRectangle:

 ![Diagramma che mostra il posizionamento della descrizione comando tramite una proprietà PlacementRectangle.Diagram showing ToolTip placement by using a PlacementRectangle property.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 L'immagine seguente mostra il posizionamento delle descrizioni comandi utilizzando le proprietà Placement, PlacementRectangle e Offset:
  
 ![Diagramma che mostra il posizionamento della descrizione comando tramite la proprietà Offset.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 Nell'esempio seguente viene <xref:System.Windows.Controls.ToolTip> illustrato come utilizzare le proprietà per <xref:System.Windows.Controls.ToolTip> specificare la posizione di una descrizione comando il cui contenuto è un oggetto .  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.ToolTipService> illustrato come utilizzare le proprietà per specificare la posizione di una descrizione comando il cui contenuto non è un <xref:System.Windows.Controls.ToolTip> oggetto.  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Argomenti relativi alle procedure](tooltip-how-to-topics.md)
- [Panoramica sul controllo ToolTip](tooltip-overview.md)
