---
title: "Procedura: Disegnare una polilinea usando l'elemento poligono"
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: fb5220082989a9d0a22c4998bb79c0a196067e7e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934967"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="52d76-102">Procedura: Disegnare una polilinea usando l'elemento poligono</span><span class="sxs-lookup"><span data-stu-id="52d76-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="52d76-103">Questo esempio illustra come creare una polilinea, ovvero una serie di linee connesse, usando l' <xref:System.Windows.Shapes.Polyline> elemento.</span><span class="sxs-lookup"><span data-stu-id="52d76-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="52d76-104">Per disegnare una polilinea, creare <xref:System.Windows.Shapes.Polyline> un elemento e utilizzare <xref:System.Windows.Shapes.Polyline.Points%2A> la relativa proprietà per specificare i vertici della forma.</span><span class="sxs-lookup"><span data-stu-id="52d76-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="52d76-105">Usare infine le <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> per descrivere il contorno della polilinea perché una linea priva di tratto è invisibile.</span><span class="sxs-lookup"><span data-stu-id="52d76-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52d76-106">Poiché l' <xref:System.Windows.Shapes.Polyline> elemento non è una forma chiusa, la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà non ha alcun effetto, neanche se si chiude intenzionalmente il contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="52d76-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="52d76-107">Per creare una forma chiusa con un <xref:System.Windows.Shapes.Shape.Fill%2A>oggetto, usare <xref:System.Windows.Shapes.Polygon> un elemento.</span><span class="sxs-lookup"><span data-stu-id="52d76-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="52d76-108">Nell'esempio seguente vengono disegnati due <xref:System.Windows.Shapes.Polyline> elementi all'interno di un oggetto. <xref:System.Windows.Controls.Canvas></span><span class="sxs-lookup"><span data-stu-id="52d76-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52d76-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="52d76-109">Example</span></span>  
 <span data-ttu-id="52d76-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]la sintassi valida per i punti è un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="52d76-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="52d76-111">Sebbene in questo esempio venga <xref:System.Windows.Controls.Canvas> utilizzato un oggetto per contenere le polilinee, è possibile utilizzare gli elementi polilinea (e tutti gli altri elementi <xref:System.Windows.Controls.Panel> Shape <xref:System.Windows.Controls.Control> ) con qualsiasi o che supporti contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="52d76-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="52d76-112">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="52d76-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d76-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52d76-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="52d76-114">Esempio di elementi Shape</span><span class="sxs-lookup"><span data-stu-id="52d76-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="52d76-115">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="52d76-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
