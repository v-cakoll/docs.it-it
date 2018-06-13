---
title: 'Procedura: disegnare un rettangolo'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 100f1a8062628e892e9a71b988bb2a8754ea6bad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561046"
---
# <a name="how-to-draw-a-rectangle"></a>Procedura: disegnare un rettangolo
In questo esempio viene illustrato come disegnare un rettangolo utilizzando il <xref:System.Windows.Shapes.Rectangle> elemento.  
  
 Per disegnare un rettangolo, creare un <xref:System.Windows.Shapes.Rectangle> elemento e specificare il relativo <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>. Per disegnare l'interno del rettangolo, impostare il relativo <xref:System.Windows.Shapes.Shape.Fill%2A>. Per assegnare il rettangolo di una struttura, utilizzare il relativo <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà.  
  
 Per impostare il rettangolo angoli arrotondati, specificare l'opzione facoltativa <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> proprietà. Il <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> impostano i raggi di assi x e y dell'ellisse utilizzata per arrotondare gli angoli del rettangolo.  
  
 Nell'esempio seguente, due <xref:System.Windows.Shapes.Rectangle> vengono disegnati gli elementi in un <xref:System.Windows.Controls.Canvas>. Il primo rettangolo ha un <xref:System.Windows.Media.Brushes.Blue%2A> interni. Il secondo rettangolo ha un <xref:System.Windows.Media.Brushes.Blue%2A> interno, un <xref:System.Windows.Media.Brushes.Black%2A> struttura e gli angoli arrotondati.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Sebbene questo esempio viene utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i rettangoli, è possibile utilizzare gli elementi rettangolo (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo. Infatti, i rettangoli sono particolarmente utili per fornire gli sfondi delle parti di <xref:System.Windows.Controls.Grid> pannelli. Per un esempio, vedere il [Cenni preliminari su tabella](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Shapes.Rectangle>  
 [Esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Cenni preliminari sull'elemento Table](../../../../docs/framework/wpf/advanced/table-overview.md)
