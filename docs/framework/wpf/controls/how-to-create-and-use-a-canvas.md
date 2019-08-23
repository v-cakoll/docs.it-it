---
title: "Procedura: Creare e usare un'area di disegno"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: edef660b2da2f09e0a6edbc0a87f0d1f26eb03da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964226"
---
# <a name="how-to-create-and-use-a-canvas"></a>Procedura: Creare e usare un'area di disegno
In questo esempio viene illustrato come creare e utilizzare un'istanza <xref:System.Windows.Controls.Canvas>di.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono posizionati in <xref:System.Windows.Controls.TextBlock> modo esplicito due <xref:System.Windows.Controls.Canvas.SetTop%2A> elementi <xref:System.Windows.Controls.Canvas.SetLeft%2A> usando i <xref:System.Windows.Controls.Canvas>metodi e di. Nell'esempio viene inoltre assegnato un <xref:System.Windows.Controls.Control.Background%2A> `LightSteelBlue` colore a <xref:System.Windows.Controls.Canvas>.  
  
> [!NOTE]
> Quando si utilizza [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per posizionare <xref:System.Windows.Controls.TextBlock> gli elementi, utilizzare <xref:System.Windows.Controls.Canvas.Top%2A> le <xref:System.Windows.Controls.Canvas.Left%2A> proprietà e.  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Procedure relative alle proprietà](canvas-how-to-topics.md)
