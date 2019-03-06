---
title: 'Procedura: Creare un arco ellittico'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: bb4b4d99aab9daef70f446af176bb462b0661d54
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354349"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="ff416-102">Procedura: Creare un arco ellittico</span><span class="sxs-lookup"><span data-stu-id="ff416-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="ff416-103">In questo esempio illustra come disegnare un arco ellittico. Per creare un arco ellittico, usare il <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.ArcSegment> classi.</span><span class="sxs-lookup"><span data-stu-id="ff416-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff416-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff416-104">Example</span></span>  
 <span data-ttu-id="ff416-105">Negli esempi seguenti, viene disegnato un arco ellittico da (10, 100) a (200,100).</span><span class="sxs-lookup"><span data-stu-id="ff416-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="ff416-106">Ha l'arco un <xref:System.Windows.Media.ArcSegment.Size%2A> di 100 per 50 pixel indipendenti dal dispositivo, un <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> di 45 gradi, un <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> impostazione `true`e un <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> di <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="ff416-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="ff416-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="ff416-107">[xaml]</span></span>  
  
 <span data-ttu-id="ff416-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile usare la sintassi degli attributi per descrivere un tracciato.</span><span class="sxs-lookup"><span data-stu-id="ff416-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="ff416-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="ff416-109">[xaml]</span></span>  
  
 <span data-ttu-id="ff416-110">(Si noti che questa sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di una <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="ff416-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="ff416-111">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="ff416-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="ff416-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile disegnare un arco ellittico in modo esplicito usando tag di oggetti.</span><span class="sxs-lookup"><span data-stu-id="ff416-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="ff416-113">Di seguito è equivalente al precedente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span><span class="sxs-lookup"><span data-stu-id="ff416-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="ff416-114">Questo esempio fa parte di un esempio più esaustivo.</span><span class="sxs-lookup"><span data-stu-id="ff416-114">This example is part of a larger sample.</span></span> <span data-ttu-id="ff416-115">Per l'esempio completo, vedere la [esempio di geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="ff416-115">For the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff416-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff416-116">See also</span></span>
- [<span data-ttu-id="ff416-117">Creare una curva di Bézier quadratica</span><span class="sxs-lookup"><span data-stu-id="ff416-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="ff416-118">Creare una curva di Bézier cubica</span><span class="sxs-lookup"><span data-stu-id="ff416-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
