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
ms.openlocfilehash: 69620d81eb77eb76f21f099b30017b142d818457
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559366"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Procedura: disegnare un'ellisse o un cerchio
In questo esempio viene illustrato come creare i puntini di sospensione e cerchi utilizzando il <xref:System.Windows.Shapes.Ellipse> elemento. Per disegnare un'ellisse, creare un <xref:System.Windows.Shapes.Ellipse> elemento e specificare il relativo <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>. Utilizzare il relativo <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà per specificare il <xref:System.Windows.Media.Brush> che viene usato per colorare l'interno dell'ellisse. Utilizzare il relativo <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà per specificare il <xref:System.Windows.Media.Brush> utilizzato per disegnare il contorno dell'ellisse. Il <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà specifica lo spessore del contorno dell'ellisse.  
  
 Per disegnare un cerchio, impostare il <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> del <xref:System.Windows.Shapes.Ellipse> elemento uguale a altro.  
  
 Nell'esempio seguente disegna quattro <xref:System.Windows.Shapes.Ellipse> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Sebbene questo esempio viene utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i puntini di sospensione, è possibile utilizzare gli elementi di puntini di sospensione (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.  
  
 In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [Esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037)
