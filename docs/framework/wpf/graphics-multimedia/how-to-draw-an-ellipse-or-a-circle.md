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
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="321db-102">Procedura: disegnare un'ellisse o un cerchio</span><span class="sxs-lookup"><span data-stu-id="321db-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="321db-103">In questo esempio viene illustrato come creare i puntini di sospensione e cerchi utilizzando il <xref:System.Windows.Shapes.Ellipse> elemento.</span><span class="sxs-lookup"><span data-stu-id="321db-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="321db-104">Per disegnare un'ellisse, creare un <xref:System.Windows.Shapes.Ellipse> elemento e specificare il relativo <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="321db-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="321db-105">Utilizzare il relativo <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà per specificare il <xref:System.Windows.Media.Brush> che viene usato per colorare l'interno dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="321db-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="321db-106">Utilizzare il relativo <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà per specificare il <xref:System.Windows.Media.Brush> utilizzato per disegnare il contorno dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="321db-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="321db-107">Il <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà specifica lo spessore del contorno dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="321db-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="321db-108">Per disegnare un cerchio, impostare il <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> del <xref:System.Windows.Shapes.Ellipse> elemento uguale a altro.</span><span class="sxs-lookup"><span data-stu-id="321db-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="321db-109">Nell'esempio seguente disegna quattro <xref:System.Windows.Shapes.Ellipse> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="321db-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="321db-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="321db-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="321db-111">Sebbene questo esempio viene utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i puntini di sospensione, è possibile utilizzare gli elementi di puntini di sospensione (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="321db-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="321db-112">In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="321db-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="321db-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="321db-113">See Also</span></span>  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [<span data-ttu-id="321db-114">Esempio di elementi forma</span><span class="sxs-lookup"><span data-stu-id="321db-114">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)
