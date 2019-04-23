---
title: 'Procedura: Disegnare un rettangolo'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 261026b994b432565928b38ff1657115ff7cbe4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217354"
---
# <a name="how-to-draw-a-rectangle"></a>Procedura: Disegnare un rettangolo
Questo esempio illustra come disegnare un rettangolo utilizzando il <xref:System.Windows.Shapes.Rectangle> elemento.  
  
 Per disegnare un rettangolo, creare un <xref:System.Windows.Shapes.Rectangle> elemento e specificare il <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>. Per disegnare l'interno del rettangolo, impostare il <xref:System.Windows.Shapes.Shape.Fill%2A>. Per assegnare il rettangolo a una struttura, usare il <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà.  
  
 Per impostare il rettangolo angoli arrotondati, specificare l'opzione facoltativa <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> proprietà. Il <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> impostate i raggi degli assi x e y dell'ellisse usato per arrotondare gli angoli del rettangolo.  
  
 Nell'esempio seguente, due <xref:System.Windows.Shapes.Rectangle> vengono disegnati gli elementi in un <xref:System.Windows.Controls.Canvas>. Il primo rettangolo ha un <xref:System.Windows.Media.Brushes.Blue%2A> interni. Il secondo rettangolo ha un <xref:System.Windows.Media.Brushes.Blue%2A> interno, un <xref:System.Windows.Media.Brushes.Black%2A> la struttura e angoli arrotondati.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Sebbene questo esempio Usa un' <xref:System.Windows.Controls.Canvas> per contenere i rettangoli, è possibile usare gli elementi rettangolo (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo. Infatti, sono particolarmente utili per fornire gli sfondi delle parti di rettangoli <xref:System.Windows.Controls.Grid> pannelli. Per un esempio, vedere la [panoramica delle tabelle](../advanced/table-overview.md).  
  
 In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Rectangle>
- [Esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni preliminari sull'elemento Table](../advanced/table-overview.md)
