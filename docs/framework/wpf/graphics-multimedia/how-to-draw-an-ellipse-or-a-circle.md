---
title: "Procedura: Disegnare un'ellisse o un cerchio"
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 1393e158c1787dc7d4e44e5e1c90ed2e65666dc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947563"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Procedura: Disegnare un'ellisse o un cerchio
Questo esempio illustra come disegnare cerchi e sui puntini di sospensione tramite il <xref:System.Windows.Shapes.Ellipse> elemento. Per disegnare un'ellisse, creare un <xref:System.Windows.Shapes.Ellipse> elemento e specificare il <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>. Usare la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà per specificare il <xref:System.Windows.Media.Brush> utilizzato per disegnare la parte interna dell'ellisse. Usare la <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà per specificare il <xref:System.Windows.Media.Brush> utilizzato per disegnare il contorno dell'ellisse. Il <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà specifica lo spessore del contorno dell'ellisse.  
  
 Per disegnare un cerchio, effettuare le <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> del <xref:System.Windows.Shapes.Ellipse> elemento uguale a tra loro.  
  
 L'esempio seguente disegna quattro <xref:System.Windows.Shapes.Ellipse> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Sebbene questo esempio Usa un' <xref:System.Windows.Controls.Canvas> per contenere i puntini di sospensione, è possibile usare gli elementi di puntini di sospensione (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.  
  
 In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037)
