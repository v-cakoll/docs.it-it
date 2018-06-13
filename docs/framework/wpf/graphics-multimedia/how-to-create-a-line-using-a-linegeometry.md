---
title: 'Procedura: creare una riga utilizzando un oggetto LineGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: 8db33fc5c611dcbcae50c71ada1c6b6f9fd9bd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560469"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="77b2f-102">Procedura: creare una riga utilizzando un oggetto LineGeometry</span><span class="sxs-lookup"><span data-stu-id="77b2f-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="77b2f-103">In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Media.LineGeometry> classe per descrivere una riga.</span><span class="sxs-lookup"><span data-stu-id="77b2f-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="77b2f-104">Oggetto <xref:System.Windows.Media.LineGeometry> è definito per i punti iniziale e finale.</span><span class="sxs-lookup"><span data-stu-id="77b2f-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77b2f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="77b2f-105">Example</span></span>  
 <span data-ttu-id="77b2f-106">Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.LineGeometry>.</span><span class="sxs-lookup"><span data-stu-id="77b2f-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="77b2f-107">Oggetto <xref:System.Windows.Shapes.Path> elemento viene usato per il rendering della linea.</span><span class="sxs-lookup"><span data-stu-id="77b2f-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="77b2f-108">Poiché una riga non presenta un'area, il <xref:System.Windows.Shapes.Path> dell'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> non è specificato; invece di <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà vengono utilizzate.</span><span class="sxs-lookup"><span data-stu-id="77b2f-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="77b2f-109">![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="77b2f-109">![A LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="77b2f-110">Un oggetto LineGeometry disegnato da (10,20) a (100,130)</span><span class="sxs-lookup"><span data-stu-id="77b2f-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="77b2f-111">Le altre classi geometry semplice <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="77b2f-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="77b2f-112">Le geometrie, come quelle più complesse, possono essere create anche usando un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="77b2f-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="77b2f-113">Per ulteriori informazioni, vedere il [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="77b2f-113">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b2f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77b2f-114">See Also</span></span>  
 [<span data-ttu-id="77b2f-115">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="77b2f-115">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="77b2f-116">Creare una forma composta</span><span class="sxs-lookup"><span data-stu-id="77b2f-116">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="77b2f-117">Creare una forma usando un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="77b2f-117">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
