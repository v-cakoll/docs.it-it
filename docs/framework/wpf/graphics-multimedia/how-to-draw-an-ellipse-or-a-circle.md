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
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="b9341-102">Procedura: disegnare un'ellisse o un cerchio</span><span class="sxs-lookup"><span data-stu-id="b9341-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="b9341-103">Questo esempio illustra come creare ellissi e cerchi usando l'elemento <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="b9341-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="b9341-104">Per creare un'ellisse, creare un elemento <xref:System.Windows.Shapes.Ellipse> e specificarne <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="b9341-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="b9341-105">Usare la proprietà <xref:System.Windows.Shapes.Shape.Fill%2A> per specificare il <xref:System.Windows.Media.Brush> usato per disegnare l'interno dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="b9341-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="b9341-106">Usare la proprietà <xref:System.Windows.Shapes.Shape.Stroke%2A> per specificare il <xref:System.Windows.Media.Brush> usato per disegnare il contorno dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="b9341-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="b9341-107">La proprietà <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> specifica lo spessore del contorno ellisse.</span><span class="sxs-lookup"><span data-stu-id="b9341-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="b9341-108">Per creare un cerchio, fare in modo che il <xref:System.Windows.FrameworkElement.Width%2A> e il <xref:System.Windows.FrameworkElement.Height%2A> dell'elemento <xref:System.Windows.Shapes.Ellipse> siano uguali tra loro.</span><span class="sxs-lookup"><span data-stu-id="b9341-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="b9341-109">Nell'esempio seguente vengono disegnati quattro <xref:System.Windows.Shapes.Ellipse> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="b9341-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9341-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9341-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="b9341-111">Sebbene in questo esempio venga utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i puntini di sospensione, è possibile utilizzare gli elementi Ellipse (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="b9341-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="b9341-112">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="b9341-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9341-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9341-113">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="b9341-114">Esempio di elementi Shape</span><span class="sxs-lookup"><span data-stu-id="b9341-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
