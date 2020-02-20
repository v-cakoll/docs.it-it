---
title: 'Procedura: creare una curva di Bezier cubica'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: c12bd84fcebb3acebb80bef5f4479ad535fd6691
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452110"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="f352d-102">Procedura: creare una curva di Bezier cubica</span><span class="sxs-lookup"><span data-stu-id="f352d-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="f352d-103">Questo esempio illustra come creare una curva di Bezier cubica.</span><span class="sxs-lookup"><span data-stu-id="f352d-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="f352d-104">Per creare una curva di Bezier cubica, usare le classi <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>e <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="f352d-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="f352d-105">Per visualizzare la geometria risultante, usare un elemento <xref:System.Windows.Shapes.Path> o usarlo con una <xref:System.Windows.Media.GeometryDrawing> o un <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="f352d-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="f352d-106">Negli esempi seguenti viene disegnata una curva di Bezier cubica da (10, 100) a (300, 100).</span><span class="sxs-lookup"><span data-stu-id="f352d-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="f352d-107">La curva ha punti di controllo di (100, 0) e (200, 200).</span><span class="sxs-lookup"><span data-stu-id="f352d-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f352d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="f352d-108">Example</span></span>  
 <span data-ttu-id="f352d-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f352d-109">[xaml]</span></span>  
  
 <span data-ttu-id="f352d-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile usare la sintassi di markup abbreviata per descrivere un percorso.</span><span class="sxs-lookup"><span data-stu-id="f352d-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="f352d-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f352d-111">[xaml]</span></span>  
  
 <span data-ttu-id="f352d-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]è anche possibile creare una curva di Bezier cubica usando i tag Object.</span><span class="sxs-lookup"><span data-stu-id="f352d-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="f352d-113">L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="f352d-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="f352d-114">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="f352d-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f352d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f352d-115">See also</span></span>

- [<span data-ttu-id="f352d-116">Creare un arco ellittico</span><span class="sxs-lookup"><span data-stu-id="f352d-116">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="f352d-117">Creare un oggetto LineSegment in un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="f352d-117">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="f352d-118">Creare una curva di Bézier cubica</span><span class="sxs-lookup"><span data-stu-id="f352d-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="f352d-119">Creare una curva di Bézier quadratica</span><span class="sxs-lookup"><span data-stu-id="f352d-119">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
