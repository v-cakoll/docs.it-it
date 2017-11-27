---
title: 'Procedura: inserire un disegno in un''area'
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
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1db788ae0fabdfd27cf215bfcf466c41df19c637
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-drawing"></a>Procedura: inserire un disegno in un'area
Questo esempio spiega come inserire un disegno in un'area. Per disegnare un'area con un disegno, si utilizza un <xref:System.Windows.Media.DrawingBrush> e uno o più <xref:System.Windows.Media.Drawing> oggetti.   Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.DrawingBrush> per disegnare un oggetto con un disegno di due ellissi.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 L'immagine seguente illustra l'output dell'esempio.  
  
 ![Output di DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")  
  
 (Il centro della forma è bianco per motivi descritti in [controllare il riempimento di una forma composta](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md).)  
  
 Impostando un <xref:System.Windows.Media.DrawingBrush> dell'oggetto <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà, è possibile creare un criterio di ripetizione. L'esempio seguente disegna un oggetto con un motivo creato da un disegno di due ellissi.  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 La figura seguente mostra l'affiancato <xref:System.Windows.Media.DrawingBrush> output.  
  
 ![Output affiancato di DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")  
  
 Per ulteriori informazioni sulla creazione di pennelli, vedere [il disegno di immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md). Per ulteriori informazioni su <xref:System.Windows.Media.Drawing> degli oggetti, vedere il [panoramica sugli oggetti disegno](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).
