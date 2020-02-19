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
ms.openlocfilehash: 6698141bcaa3b0fd5f5b9cf66bcab1be1f4ea2f0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452961"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Procedura: disegnare una polilinea utilizzando l'elemento polilinea
Questo esempio illustra come creare una polilinea, ovvero una serie di linee connesse, usando l'elemento <xref:System.Windows.Shapes.Polyline>.  
  
 Per disegnare una polilinea, creare un elemento <xref:System.Windows.Shapes.Polyline> e utilizzare la relativa proprietà <xref:System.Windows.Shapes.Polyline.Points%2A> per specificare i vertici della forma. Usare infine le proprietà <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> per descrivere il contorno della polilinea perché una linea priva di un tratto è invisibile.  
  
> [!NOTE]
> Poiché l'elemento <xref:System.Windows.Shapes.Polyline> non è una forma chiusa, la proprietà <xref:System.Windows.Shapes.Shape.Fill%2A> non ha alcun effetto, neanche se si chiude intenzionalmente il contorno della forma. Per creare una forma chiusa con una <xref:System.Windows.Shapes.Shape.Fill%2A>, utilizzare un elemento <xref:System.Windows.Shapes.Polygon>.  
  
 Nell'esempio seguente vengono disegnati due <xref:System.Windows.Shapes.Polyline> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]la sintassi valida per i punti è un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Sebbene in questo esempio venga usato un <xref:System.Windows.Controls.Canvas> per contenere le polilinee, è possibile usare gli elementi polilinea (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [Esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
