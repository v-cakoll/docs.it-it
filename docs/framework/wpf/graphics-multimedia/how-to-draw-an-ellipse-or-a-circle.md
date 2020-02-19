---
title: "Procedura: disegnare un'ellisse o un cerchio"
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452922"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Procedura: disegnare un'ellisse o un cerchio
Questo esempio illustra come creare ellissi e cerchi usando l'elemento <xref:System.Windows.Shapes.Ellipse>. Per creare un'ellisse, creare un elemento <xref:System.Windows.Shapes.Ellipse> e specificarne <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>. Usare la proprietà <xref:System.Windows.Shapes.Shape.Fill%2A> per specificare il <xref:System.Windows.Media.Brush> usato per disegnare l'interno dell'ellisse. Usare la proprietà <xref:System.Windows.Shapes.Shape.Stroke%2A> per specificare il <xref:System.Windows.Media.Brush> usato per disegnare il contorno dell'ellisse. La proprietà <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> specifica lo spessore del contorno ellisse.  
  
 Per creare un cerchio, fare in modo che il <xref:System.Windows.FrameworkElement.Width%2A> e il <xref:System.Windows.FrameworkElement.Height%2A> dell'elemento <xref:System.Windows.Shapes.Ellipse> siano uguali tra loro.  
  
 Nell'esempio seguente vengono disegnati quattro <xref:System.Windows.Shapes.Ellipse> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Sebbene in questo esempio venga utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i puntini di sospensione, è possibile utilizzare gli elementi Ellipse (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
