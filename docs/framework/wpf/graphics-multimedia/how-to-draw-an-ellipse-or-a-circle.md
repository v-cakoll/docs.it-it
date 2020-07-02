---
title: "Procedura: disegnare un'ellisse o un cerchio"
description: Informazioni su come disegnare un'ellisse o un cerchio con scelte per lo spessore del contorno e il colore interno in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: afa0e7d2af42aaee39dca164f23b1a1cacf430ca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853559"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Procedura: disegnare un'ellisse o un cerchio
Questo esempio illustra come creare ellissi e cerchi usando l' <xref:System.Windows.Shapes.Ellipse> elemento. Per creare un'ellisse, creare un <xref:System.Windows.Shapes.Ellipse> elemento e specificare i relativi <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> . Utilizzare la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà per specificare l'oggetto <xref:System.Windows.Media.Brush> utilizzato per disegnare l'interno dell'ellisse. Utilizzare la <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà per specificare l'oggetto <xref:System.Windows.Media.Brush> utilizzato per disegnare il contorno dell'ellisse. La <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà specifica lo spessore del contorno ellisse.  
  
 Per creare un cerchio, rendere gli <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> elementi e dell' <xref:System.Windows.Shapes.Ellipse> elemento uguali.  
  
 Nell'esempio seguente vengono disegnati quattro <xref:System.Windows.Shapes.Ellipse> elementi all'interno di un oggetto <xref:System.Windows.Controls.Canvas> .  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Sebbene in questo esempio venga utilizzato un oggetto <xref:System.Windows.Controls.Canvas> per contenere i puntini di sospensione, è possibile utilizzare gli elementi ellisse (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
