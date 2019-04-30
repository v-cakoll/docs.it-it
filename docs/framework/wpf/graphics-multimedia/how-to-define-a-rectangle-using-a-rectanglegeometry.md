---
title: 'Procedura: Definire un rettangolo usando un oggetto RectangleGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 146ca7017ee38ad5c1065e59662ac441e7bfbfe2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965412"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Procedura: Definire un rettangolo usando un oggetto RectangleGeometry
In questo esempio viene descritto come utilizzare il <xref:System.Windows.Media.RectangleGeometry> classe per descrivere un rettangolo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.RectangleGeometry>.  La posizione relativa e le dimensioni del rettangolo sono definite da un <xref:System.Windows.Rect> struttura. È la posizione relativa `50,50` e l'altezza e la larghezza sono entrambe `25` la creazione di un quadrato. L'interno del rettangolo viene disegnato con un <xref:System.Windows.Media.Brushes.LemonChiffon%2A> pennello e il relativo profilo viene disegnato con un <xref:System.Windows.Media.Brushes.Black%2A> tratto con uno spessore pari a `1`.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![Un oggetto RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 Anche se in questo esempio viene utilizzato un <xref:System.Windows.Shapes.Path> elemento per il rendering le <xref:System.Windows.Media.RectangleGeometry>, sono disponibili molti altri modi per usare <xref:System.Windows.Media.RectangleGeometry> oggetti. Ad esempio, un <xref:System.Windows.Media.RectangleGeometry> può essere utilizzato per specificare il <xref:System.Windows.UIElement.Clip%2A> di un <xref:System.Windows.UIElement> o il <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> di un <xref:System.Windows.Media.GeometryDrawing>.  
  
 Le altre classi di geometrie semplici includono <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.EllipseGeometry>. Questi oggetti Geometry, nonché quelle più complesse, è inoltre possibile creare utilizzando un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Creare una forma composta](how-to-create-a-composite-shape.md)
- [Creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
