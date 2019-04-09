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
ms.openlocfilehash: 4f55ecc206be0ef4947923047e796c36131c70ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59114846"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="23b4c-102">Procedura: Disegnare una polilinea usando l'elemento poligono</span><span class="sxs-lookup"><span data-stu-id="23b4c-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="23b4c-103">Questo esempio illustra come disegnare una polilinea, ovvero una serie di linee collegate, usando il <xref:System.Windows.Shapes.Polyline> elemento.</span><span class="sxs-lookup"><span data-stu-id="23b4c-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="23b4c-104">Per disegnare una polilinea, creare un <xref:System.Windows.Shapes.Polyline> elemento e utilizzo relativi <xref:System.Windows.Shapes.Polyline.Points%2A> proprietà per specificare i vertici della forma.</span><span class="sxs-lookup"><span data-stu-id="23b4c-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="23b4c-105">Infine, usare il <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> definite dalle proprietà che descrivono la polilinea perché non è visibile una riga senza un tratto.</span><span class="sxs-lookup"><span data-stu-id="23b4c-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23b4c-106">Poiché il <xref:System.Windows.Shapes.Polyline> elemento non è una forma chiusa, il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà non ha alcun effetto, anche se si chiude intenzionalmente il contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="23b4c-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="23b4c-107">Per creare una forma chiusa con un <xref:System.Windows.Shapes.Shape.Fill%2A>, usare un <xref:System.Windows.Shapes.Polygon> elemento.</span><span class="sxs-lookup"><span data-stu-id="23b4c-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="23b4c-108">L'esempio seguente disegna due <xref:System.Windows.Shapes.Polyline> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="23b4c-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23b4c-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="23b4c-109">Example</span></span>  
 <span data-ttu-id="23b4c-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], le sintassi valide per i punti di sono un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="23b4c-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="23b4c-111">Sebbene questo esempio Usa un' <xref:System.Windows.Controls.Canvas> per contenere le polilinee, è possibile usare gli elementi polyline (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="23b4c-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="23b4c-112">In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="23b4c-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b4c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23b4c-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="23b4c-114">Esempio di elementi forma</span><span class="sxs-lookup"><span data-stu-id="23b4c-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="23b4c-115">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="23b4c-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
