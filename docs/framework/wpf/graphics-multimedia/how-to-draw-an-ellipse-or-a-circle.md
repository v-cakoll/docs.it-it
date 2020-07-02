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
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="ff13b-103">Procedura: disegnare un'ellisse o un cerchio</span><span class="sxs-lookup"><span data-stu-id="ff13b-103">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="ff13b-104">Questo esempio illustra come creare ellissi e cerchi usando l' <xref:System.Windows.Shapes.Ellipse> elemento.</span><span class="sxs-lookup"><span data-stu-id="ff13b-104">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="ff13b-105">Per creare un'ellisse, creare un <xref:System.Windows.Shapes.Ellipse> elemento e specificare i relativi <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="ff13b-105">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="ff13b-106">Utilizzare la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà per specificare l'oggetto <xref:System.Windows.Media.Brush> utilizzato per disegnare l'interno dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="ff13b-106">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="ff13b-107">Utilizzare la <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà per specificare l'oggetto <xref:System.Windows.Media.Brush> utilizzato per disegnare il contorno dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="ff13b-107">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="ff13b-108">La <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà specifica lo spessore del contorno ellisse.</span><span class="sxs-lookup"><span data-stu-id="ff13b-108">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="ff13b-109">Per creare un cerchio, rendere gli <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> elementi e dell' <xref:System.Windows.Shapes.Ellipse> elemento uguali.</span><span class="sxs-lookup"><span data-stu-id="ff13b-109">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="ff13b-110">Nell'esempio seguente vengono disegnati quattro <xref:System.Windows.Shapes.Ellipse> elementi all'interno di un oggetto <xref:System.Windows.Controls.Canvas> .</span><span class="sxs-lookup"><span data-stu-id="ff13b-110">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff13b-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff13b-111">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="ff13b-112">Sebbene in questo esempio venga utilizzato un oggetto <xref:System.Windows.Controls.Canvas> per contenere i puntini di sospensione, è possibile utilizzare gli elementi ellisse (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="ff13b-112">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="ff13b-113">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="ff13b-113">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff13b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff13b-114">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="ff13b-115">Esempio di elementi Shape</span><span class="sxs-lookup"><span data-stu-id="ff13b-115">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
