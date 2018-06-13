---
title: 'Procedura: creare un oggetto GeometryDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: 713cecd10bfa62494c50c96cb8cbece69f7e5660
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560660"
---
# <a name="how-to-create-a-geometrydrawing"></a>Procedura: creare un oggetto GeometryDrawing
In questo esempio viene illustrato come creare e visualizzare un <xref:System.Windows.Media.GeometryDrawing>. Oggetto <xref:System.Windows.Media.GeometryDrawing> consente di creare una forma con riempimento e una struttura associando un <xref:System.Windows.Media.Pen> e <xref:System.Windows.Media.Brush> con un <xref:System.Windows.Media.Geometry>. Il <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> descrive la struttura della forma, il <xref:System.Windows.Media.GeometryDrawing.Brush%2A> descrive il riempimento e <xref:System.Windows.Media.GeometryDrawing.Pen%2A> descrive la struttura della forma.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.GeometryDrawing> per eseguire il rendering di una forma. La forma è descritta da un <xref:System.Windows.Media.GeometryGroup> e due <xref:System.Windows.Media.EllipseGeometry> oggetti. Viene disegnato l'interno della forma con un <xref:System.Windows.Media.LinearGradientBrush> e la struttura con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. Il <xref:System.Windows.Media.GeometryDrawing> viene visualizzato utilizzando un <xref:System.Windows.Media.ImageDrawing> e <xref:System.Windows.Controls.Image> elemento.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 La figura seguente mostra il valore risultante <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing di due ellissi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 Per creare disegni più complessi, è possibile combinare più oggetti in un unico disegno composto utilizzando un <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.DrawingGroup>  
 [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Cenni preliminari sulle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Creare un disegno composto](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
