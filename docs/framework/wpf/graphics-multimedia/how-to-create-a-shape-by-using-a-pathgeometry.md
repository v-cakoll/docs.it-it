---
title: 'Procedura: creare una forma tramite un oggetto PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452045"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="4811d-102">Procedura: creare una forma tramite un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="4811d-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="4811d-103">Questo esempio illustra come creare una forma usando la classe <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="4811d-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="4811d-104"><xref:System.Windows.Media.PathGeometry> oggetti sono costituiti da uno o più oggetti <xref:System.Windows.Media.PathFigure>; ogni <xref:System.Windows.Media.PathFigure> rappresenta una "figura" o una forma diversa.</span><span class="sxs-lookup"><span data-stu-id="4811d-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="4811d-105">Ogni <xref:System.Windows.Media.PathFigure> è costituita da uno o più oggetti <xref:System.Windows.Media.PathSegment>, ciascuno dei quali rappresenta una parte connessa della figura o della forma.</span><span class="sxs-lookup"><span data-stu-id="4811d-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="4811d-106">I tipi di segmento includono <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>e <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="4811d-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4811d-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4811d-107">Example</span></span>  
 <span data-ttu-id="4811d-108">Nell'esempio seguente viene usato un <xref:System.Windows.Media.PathGeometry> per creare un triangolo.</span><span class="sxs-lookup"><span data-stu-id="4811d-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="4811d-109">Il <xref:System.Windows.Media.PathGeometry> viene visualizzato utilizzando un elemento <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="4811d-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="4811d-110">La figura seguente mostra la forma creata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="4811d-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="4811d-111">![Oggetto PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="4811d-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="4811d-112">Triangolo creato con PathGeometry</span><span class="sxs-lookup"><span data-stu-id="4811d-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="4811d-113">Nell'esempio precedente è stato illustrato come creare una forma relativamente semplice, un triangolo.</span><span class="sxs-lookup"><span data-stu-id="4811d-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="4811d-114">È anche possibile usare un <xref:System.Windows.Media.PathGeometry> per creare forme più complesse, tra cui archi e curve.</span><span class="sxs-lookup"><span data-stu-id="4811d-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="4811d-115">Per esempi, vedere [creare un arco ellittico](how-to-create-an-elliptical-arc.md), [creare una curva di Bezier cubica](how-to-create-a-cubic-bezier-curve.md)e [creare una curva di Bézier quadratica](how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="4811d-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="4811d-116">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="4811d-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4811d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4811d-117">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="4811d-118">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="4811d-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="4811d-119">Esempio di geometrie</span><span class="sxs-lookup"><span data-stu-id="4811d-119">Geometries Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
