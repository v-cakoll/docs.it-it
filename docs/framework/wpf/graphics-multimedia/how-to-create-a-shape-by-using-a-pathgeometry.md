---
title: 'Procedura: creare una forma tramite un oggetto PathGeometry'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 784a8df792ca4dc05e36f5b7e9ec93b02e0e639f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="d2132-102">Procedura: creare una forma tramite un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="d2132-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="d2132-103">In questo esempio viene illustrato come creare una forma utilizzando la <xref:System.Windows.Media.PathGeometry> classe.</span><span class="sxs-lookup"><span data-stu-id="d2132-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="d2132-104"><xref:System.Windows.Media.PathGeometry>gli oggetti sono costituiti da uno o più <xref:System.Windows.Media.PathFigure> oggetti; ogni <xref:System.Windows.Media.PathFigure> rappresenta un "importo" diverso o una forma.</span><span class="sxs-lookup"><span data-stu-id="d2132-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="d2132-105">Ogni <xref:System.Windows.Media.PathFigure> è composto di uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte collegata della figura o forma.</span><span class="sxs-lookup"><span data-stu-id="d2132-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="d2132-106">Tipi di segmento comprendono <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, e <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="d2132-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2132-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="d2132-107">Example</span></span>  
 <span data-ttu-id="d2132-108">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.PathGeometry> per creare un triangolo.</span><span class="sxs-lookup"><span data-stu-id="d2132-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="d2132-109">Il <xref:System.Windows.Media.PathGeometry> viene visualizzato utilizzando un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="d2132-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="d2132-110">La figura seguente mostra la forma creata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="d2132-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="d2132-111">![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="d2132-111">![A PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="d2132-112">Triangolo creato con PathGeometry</span><span class="sxs-lookup"><span data-stu-id="d2132-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="d2132-113">Nell'esempio precedente viene illustrato come creare una forma relativamente semplice, un triangolo.</span><span class="sxs-lookup"><span data-stu-id="d2132-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="d2132-114">Oggetto <xref:System.Windows.Media.PathGeometry> può anche essere utilizzato per creare forme più complesse, tra cui archi e curve.</span><span class="sxs-lookup"><span data-stu-id="d2132-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="d2132-115">Per esempi, vedere [creare un arco ellittico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [crea una curva di Bézier cubica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), e [crea una curva di Bézier quadratica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="d2132-115">For examples, see [Create an Elliptical Arc](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="d2132-116">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="d2132-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2132-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2132-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [<span data-ttu-id="d2132-118">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="d2132-118">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="d2132-119">Esempio di geometrie</span><span class="sxs-lookup"><span data-stu-id="d2132-119">Geometries Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159989)
