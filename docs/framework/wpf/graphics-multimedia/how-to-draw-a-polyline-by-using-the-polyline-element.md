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
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="13f17-102">Procedura: disegnare una polilinea utilizzando l'elemento polilinea</span><span class="sxs-lookup"><span data-stu-id="13f17-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="13f17-103">Questo esempio illustra come creare una polilinea, ovvero una serie di linee connesse, usando l'elemento <xref:System.Windows.Shapes.Polyline>.</span><span class="sxs-lookup"><span data-stu-id="13f17-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="13f17-104">Per disegnare una polilinea, creare un elemento <xref:System.Windows.Shapes.Polyline> e utilizzare la relativa proprietà <xref:System.Windows.Shapes.Polyline.Points%2A> per specificare i vertici della forma.</span><span class="sxs-lookup"><span data-stu-id="13f17-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="13f17-105">Usare infine le proprietà <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> per descrivere il contorno della polilinea perché una linea priva di un tratto è invisibile.</span><span class="sxs-lookup"><span data-stu-id="13f17-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13f17-106">Poiché l'elemento <xref:System.Windows.Shapes.Polyline> non è una forma chiusa, la proprietà <xref:System.Windows.Shapes.Shape.Fill%2A> non ha alcun effetto, neanche se si chiude intenzionalmente il contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="13f17-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="13f17-107">Per creare una forma chiusa con una <xref:System.Windows.Shapes.Shape.Fill%2A>, utilizzare un elemento <xref:System.Windows.Shapes.Polygon>.</span><span class="sxs-lookup"><span data-stu-id="13f17-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="13f17-108">Nell'esempio seguente vengono disegnati due <xref:System.Windows.Shapes.Polyline> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="13f17-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13f17-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="13f17-109">Example</span></span>  
 <span data-ttu-id="13f17-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]la sintassi valida per i punti è un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="13f17-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="13f17-111">Sebbene in questo esempio venga usato un <xref:System.Windows.Controls.Canvas> per contenere le polilinee, è possibile usare gli elementi polilinea (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="13f17-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="13f17-112">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="13f17-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f17-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13f17-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="13f17-114">Esempio di elementi Shape</span><span class="sxs-lookup"><span data-stu-id="13f17-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="13f17-115">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="13f17-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
