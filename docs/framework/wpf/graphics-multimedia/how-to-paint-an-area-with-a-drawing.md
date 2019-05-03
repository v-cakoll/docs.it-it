---
title: "Procedura: Inserire un disegno in un'area"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010074"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a>Procedura: Inserire un disegno in un'area
Questo esempio spiega come inserire un disegno in un'area. Per disegnare un'area con un disegno, si utilizza un <xref:System.Windows.Media.DrawingBrush> e uno o più <xref:System.Windows.Media.Drawing> oggetti.   L'esempio seguente usa un <xref:System.Windows.Media.DrawingBrush> per disegnare un oggetto con un disegno di due ellissi.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 L'immagine seguente illustra l'output dell'esempio.  
  
 ![Output di DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")  
  
 (Al centro della forma è bianco per i motivi descritti in [controllare il riempimento di una forma composta](how-to-control-the-fill-of-a-composite-shape.md).)  
  
 Impostando un <xref:System.Windows.Media.DrawingBrush> dell'oggetto <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà, è possibile creare un criterio di ripetizione. L'esempio seguente disegna un oggetto con un motivo creato da un disegno di due ellissi.  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 La figura seguente mostra affiancato <xref:System.Windows.Media.DrawingBrush> output.  
  
 ![Output affiancato di DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")  
  
 Per altre informazioni sui pennelli da disegno, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md). Per altre informazioni sulle <xref:System.Windows.Media.Drawing> oggetti, vedere la [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).
