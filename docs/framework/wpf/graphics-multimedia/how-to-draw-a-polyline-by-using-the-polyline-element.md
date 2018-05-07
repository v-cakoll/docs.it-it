---
title: "Procedura: disegnare una polilinea utilizzando l'elemento polilinea"
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 2abfa29f7aca4bfc8c5f91e36fd974093a98a9e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Procedura: disegnare una polilinea utilizzando l'elemento polilinea
In questo esempio viene illustrato come disegnare una polilinea, ovvero una serie di linee collegate, utilizzando il <xref:System.Windows.Shapes.Polyline> elemento.  
  
 Per disegnare una polilinea, creare un <xref:System.Windows.Shapes.Polyline> elemento e utilizzare il relativo <xref:System.Windows.Shapes.Polyline.Points%2A> proprietà per specificare i vertici della forma. Infine, utilizzare il <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> per descrivere la polilinea spiegare perché una riga senza tratto è invisibile.  
  
> [!NOTE]
>  Poiché il <xref:System.Windows.Shapes.Polyline> l'elemento non è una forma chiusa, la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà ha effetto, anche se si chiude intenzionalmente il contorno della forma. Per creare una forma chiusa con un <xref:System.Windows.Shapes.Shape.Fill%2A>, utilizzare un <xref:System.Windows.Shapes.Polygon> elemento.  
  
 Nell'esempio seguente disegna due <xref:System.Windows.Shapes.Polyline> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintassi valida per i punti di è un elenco delimitato da virgole di coppie di coordinate x e y separate da virgole.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Sebbene questo esempio viene utilizzato un <xref:System.Windows.Controls.Canvas> per contenere la polilinea, è possibile utilizzare elementi polilinea (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.  
  
 In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
