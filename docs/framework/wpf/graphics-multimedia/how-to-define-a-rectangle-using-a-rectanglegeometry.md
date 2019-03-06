---
title: 'Procedura: Definire un rettangolo utilizzando RectangleGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: bd42aca2541d67469173f63655ada18a12eb692c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352503"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="03dea-102">Procedura: Definire un rettangolo utilizzando RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="03dea-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="03dea-103">In questo esempio viene descritto come utilizzare il <xref:System.Windows.Media.RectangleGeometry> classe per descrivere un rettangolo.</span><span class="sxs-lookup"><span data-stu-id="03dea-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03dea-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="03dea-104">Example</span></span>  
 <span data-ttu-id="03dea-105">Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="03dea-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="03dea-106">La posizione relativa e le dimensioni del rettangolo sono definite da un <xref:System.Windows.Rect> struttura.</span><span class="sxs-lookup"><span data-stu-id="03dea-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="03dea-107">È la posizione relativa `50,50` e l'altezza e la larghezza sono entrambe `25` la creazione di un quadrato.</span><span class="sxs-lookup"><span data-stu-id="03dea-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="03dea-108">L'interno del rettangolo viene disegnato con un <xref:System.Windows.Media.Brushes.LemonChiffon%2A> pennello e il relativo profilo viene disegnato con un <xref:System.Windows.Media.Brushes.Black%2A> tratto con uno spessore pari a `1`.</span><span class="sxs-lookup"><span data-stu-id="03dea-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="03dea-109">![Un oggetto RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="03dea-109">![A RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="03dea-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="03dea-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="03dea-111">Anche se in questo esempio viene utilizzato un <xref:System.Windows.Shapes.Path> elemento per il rendering le <xref:System.Windows.Media.RectangleGeometry>, sono disponibili molti altri modi per usare <xref:System.Windows.Media.RectangleGeometry> oggetti.</span><span class="sxs-lookup"><span data-stu-id="03dea-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="03dea-112">Ad esempio, un <xref:System.Windows.Media.RectangleGeometry> può essere utilizzato per specificare il <xref:System.Windows.UIElement.Clip%2A> di un <xref:System.Windows.UIElement> o il <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> di un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="03dea-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="03dea-113">Le altre classi di geometrie semplici includono <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="03dea-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="03dea-114">Questi oggetti Geometry, nonché quelle più complesse, è inoltre possibile creare utilizzando un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="03dea-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03dea-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03dea-115">See also</span></span>
- [<span data-ttu-id="03dea-116">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="03dea-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="03dea-117">Creare una forma composta</span><span class="sxs-lookup"><span data-stu-id="03dea-117">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="03dea-118">Creare una forma usando un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="03dea-118">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
