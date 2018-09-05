---
title: 'Procedura: creare una forma tramite un oggetto PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: 4c9cd7a1af921a0a547c7dec3afc5f69b29e6aed
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748580"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="03dc7-102">Procedura: creare una forma tramite un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="03dc7-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="03dc7-103">Questo esempio viene illustrato come creare forme tramite il <xref:System.Windows.Media.PathGeometry> classe.</span><span class="sxs-lookup"><span data-stu-id="03dc7-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="03dc7-104"><xref:System.Windows.Media.PathGeometry> gli oggetti sono costituiti da uno o più <xref:System.Windows.Media.PathFigure> oggetti, ognuna delle quali <xref:System.Windows.Media.PathFigure> rappresenta un "importo" diverso o una forma.</span><span class="sxs-lookup"><span data-stu-id="03dc7-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="03dc7-105">Ciascuna <xref:System.Windows.Media.PathFigure> è composto di uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte collegata della figura o forma.</span><span class="sxs-lookup"><span data-stu-id="03dc7-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="03dc7-106">Tipi di segmento comprendono <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, e <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="03dc7-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03dc7-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="03dc7-107">Example</span></span>  
 <span data-ttu-id="03dc7-108">L'esempio seguente usa un <xref:System.Windows.Media.PathGeometry> per creare un triangolo.</span><span class="sxs-lookup"><span data-stu-id="03dc7-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="03dc7-109">Il <xref:System.Windows.Media.PathGeometry> viene visualizzato tramite un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="03dc7-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="03dc7-110">La figura seguente mostra la forma creata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="03dc7-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="03dc7-111">![Un oggetto PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="03dc7-111">![A PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="03dc7-112">Un triangolo creato con un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="03dc7-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="03dc7-113">L'esempio precedente illustra come creare una forma relativamente semplice, un triangolo.</span><span class="sxs-lookup"><span data-stu-id="03dc7-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="03dc7-114">Oggetto <xref:System.Windows.Media.PathGeometry> può anche essere utilizzato per creare forme più complesse, compresi archi e curve.</span><span class="sxs-lookup"><span data-stu-id="03dc7-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="03dc7-115">Per esempi, vedere [creare un arco ellittico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [creare una curva di Bézier cubica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), e [creare una curva di Bézier quadratica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="03dc7-115">For examples, see [Create an Elliptical Arc](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="03dc7-116">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="03dc7-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03dc7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03dc7-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [<span data-ttu-id="03dc7-118">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="03dc7-118">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="03dc7-119">Esempio di geometrie</span><span class="sxs-lookup"><span data-stu-id="03dc7-119">Geometries Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159989)
