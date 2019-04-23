---
title: 'Procedura: Creare un oggetto GeometryDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179790"
---
# <a name="how-to-create-a-geometrydrawing"></a>Procedura: Creare un oggetto GeometryDrawing
In questo esempio viene illustrato come creare e visualizzare un <xref:System.Windows.Media.GeometryDrawing>. Oggetto <xref:System.Windows.Media.GeometryDrawing> consente di creare una forma con riempimento e una struttura associando un <xref:System.Windows.Media.Pen> e una <xref:System.Windows.Media.Brush> con un <xref:System.Windows.Media.Geometry>. Il <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> descrive la struttura della forma, il <xref:System.Windows.Media.GeometryDrawing.Brush%2A> descrive il riempimento della forma e il <xref:System.Windows.Media.GeometryDrawing.Pen%2A> descrive la struttura della forma.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un <xref:System.Windows.Media.GeometryDrawing> per eseguire il rendering di una forma. La forma è descritta da un <xref:System.Windows.Media.GeometryGroup> e due <xref:System.Windows.Media.EllipseGeometry> oggetti. L'interno della forma viene disegnato con un <xref:System.Windows.Media.LinearGradientBrush> e la struttura viene disegnata con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. Il <xref:System.Windows.Media.GeometryDrawing> viene visualizzata usando un' <xref:System.Windows.Media.ImageDrawing> e un <xref:System.Windows.Controls.Image> elemento.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 La figura seguente mostra l'oggetto risultante <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![Un oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 Per creare disegni più complesse, è possibile combinare più disegni in un unico disegno composto utilizzando un <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingGroup>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Creare un disegno composto](how-to-create-a-composite-drawing.md)
