---
title: 'Procedura: definire un rettangolo utilizzando RectangleGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 5d2ec6aec1eea8528ea6b43f72f4820b8bc19a37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Procedura: definire un rettangolo utilizzando RectangleGeometry
In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Media.RectangleGeometry> classe per descrivere un rettangolo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.RectangleGeometry>.  La posizione relativa e le dimensioni del rettangolo sono definite da un <xref:System.Windows.Rect> struttura. La posizione relativa è `50,50` e l'altezza e larghezza sono entrambi `25` la creazione di un quadrato. Viene disegnato l'interno del rettangolo con un <xref:System.Windows.Media.Brushes.LemonChiffon%2A> pennello e il relativo profilo viene disegnato con un <xref:System.Windows.Media.Brushes.Black%2A> tratto con uno spessore pari a `1`.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 Sebbene in questo esempio viene utilizzato un <xref:System.Windows.Shapes.Path> elemento per il rendering di <xref:System.Windows.Media.RectangleGeometry>, esistono molti altri modi per utilizzare <xref:System.Windows.Media.RectangleGeometry> oggetti. Ad esempio, un <xref:System.Windows.Media.RectangleGeometry> può essere usato per specificare il <xref:System.Windows.UIElement.Clip%2A> di un <xref:System.Windows.UIElement> o <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> di un <xref:System.Windows.Media.GeometryDrawing>.  
  
 Le altre classi geometry semplice <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.EllipseGeometry>. Le geometrie, come quelle più complesse, possono essere create anche usando un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Creare una forma composta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [Creare una forma usando un oggetto PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
