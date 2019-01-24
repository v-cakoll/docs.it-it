---
title: 'Procedura: Creare un oggetto GeometryDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: c3312802b4a623afc10b620dbe2159d2c52a41a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646227"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="11632-102">Procedura: Creare un oggetto GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="11632-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="11632-103">In questo esempio viene illustrato come creare e visualizzare un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="11632-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="11632-104">Oggetto <xref:System.Windows.Media.GeometryDrawing> consente di creare una forma con riempimento e una struttura associando un <xref:System.Windows.Media.Pen> e una <xref:System.Windows.Media.Brush> con un <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="11632-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="11632-105">Il <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> descrive la struttura della forma, il <xref:System.Windows.Media.GeometryDrawing.Brush%2A> descrive il riempimento della forma e il <xref:System.Windows.Media.GeometryDrawing.Pen%2A> descrive la struttura della forma.</span><span class="sxs-lookup"><span data-stu-id="11632-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11632-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="11632-106">Example</span></span>  
 <span data-ttu-id="11632-107">L'esempio seguente usa un <xref:System.Windows.Media.GeometryDrawing> per eseguire il rendering di una forma.</span><span class="sxs-lookup"><span data-stu-id="11632-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="11632-108">La forma è descritta da un <xref:System.Windows.Media.GeometryGroup> e due <xref:System.Windows.Media.EllipseGeometry> oggetti.</span><span class="sxs-lookup"><span data-stu-id="11632-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="11632-109">L'interno della forma viene disegnato con un <xref:System.Windows.Media.LinearGradientBrush> e la struttura viene disegnata con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span><span class="sxs-lookup"><span data-stu-id="11632-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="11632-110">Il <xref:System.Windows.Media.GeometryDrawing> viene visualizzata usando un' <xref:System.Windows.Media.ImageDrawing> e un <xref:System.Windows.Controls.Image> elemento.</span><span class="sxs-lookup"><span data-stu-id="11632-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="11632-111">La figura seguente mostra l'oggetto risultante <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="11632-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="11632-112">![Un oggetto GeometryDrawing di due ellissi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="11632-112">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="11632-113">Per creare disegni più complesse, è possibile combinare più disegni in un unico disegno composto utilizzando un <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="11632-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11632-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11632-114">See also</span></span>
- <xref:System.Windows.Media.DrawingGroup>
- [<span data-ttu-id="11632-115">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="11632-115">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="11632-116">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="11632-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [<span data-ttu-id="11632-117">Creare un disegno composto</span><span class="sxs-lookup"><span data-stu-id="11632-117">Create a Composite Drawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
