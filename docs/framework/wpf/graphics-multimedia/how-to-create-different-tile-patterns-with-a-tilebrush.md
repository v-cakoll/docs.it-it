---
title: 'Procedura: Creare modelli di elementi affiancati differenti con un TileBrush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: 2efd070ac9ad502f2539d100fa450f95bcdddced
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367778"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>Procedura: Creare modelli di elementi affiancati differenti con un TileBrush
Questo esempio illustra come usare il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.TileBrush> per creare un modello.  
  
 Il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà consente di specificare come il contenuto di un <xref:System.Windows.Media.TileBrush> è ripetuto, vale a dire, affiancato per riempire un'area di output. Per creare un modello, si imposta la <xref:System.Windows.Media.TileBrush.TileMode%2A> al <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, o <xref:System.Windows.Media.TileMode.FlipXY>. È necessario impostare anche il <xref:System.Windows.Media.TileBrush.Viewport%2A> del <xref:System.Windows.Media.TileBrush> in modo che sia più piccola dell'area da disegnare; in caso contrario, solo un singolo riquadro viene generato, indipendentemente dal quale <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione utilizzata.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea cinque <xref:System.Windows.Media.DrawingBrush> gli oggetti, viene assegnata a ciascuno un diverso <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione e li utilizza per disegnare cinque rettangoli. Anche se in questo esempio Usa il <xref:System.Windows.Media.DrawingBrush> classe per illustrare <xref:System.Windows.Media.TileBrush.TileMode%2A> comportamento, il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà funziona in modo identico per tutti i i <xref:System.Windows.Media.TileBrush> oggetti, vale a dire, per <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, e <xref:System.Windows.Media.DrawingBrush>.  
  
 L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Output di esempio di affiancamento di TileBrush](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")  
Modelli creati con la proprietà TileMode  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>Vedere anche
- [Impostare la dimensione degli elementi affiancati di un TileBrush](how-to-set-the-tile-size-for-a-tilebrush.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
