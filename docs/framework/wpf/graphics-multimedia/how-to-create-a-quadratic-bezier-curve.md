---
title: 'Procedura: creare una curva di Bezier quadratica'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: caaf967b7cb5447d86dd031beeb16195413b0393
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452071"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="e84c5-102">Procedura: creare una curva di Bezier quadratica</span><span class="sxs-lookup"><span data-stu-id="e84c5-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="e84c5-103">Questo esempio illustra come creare una curva di Bézier quadratica.</span><span class="sxs-lookup"><span data-stu-id="e84c5-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="e84c5-104">Per creare una curva di Bézier quadratica, usare le classi <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>e <xref:System.Windows.Media.QuadraticBezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="e84c5-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e84c5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e84c5-105">Example</span></span>  
 <span data-ttu-id="e84c5-106">Negli esempi seguenti viene disegnata una curva di Bézier quadratica da (10.100) a (300.100).</span><span class="sxs-lookup"><span data-stu-id="e84c5-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="e84c5-107">La curva dispone di un punto di controllo di (200.200).</span><span class="sxs-lookup"><span data-stu-id="e84c5-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="e84c5-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="e84c5-108">[xaml]</span></span>  
  
 <span data-ttu-id="e84c5-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile usare la sintassi degli attributi per descrivere un percorso.</span><span class="sxs-lookup"><span data-stu-id="e84c5-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="e84c5-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="e84c5-110">[xaml]</span></span>  
  
 <span data-ttu-id="e84c5-111">Si noti che questa sintassi di attributo crea effettivamente un <xref:System.Windows.Media.StreamGeometry>, una versione più leggera di un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="e84c5-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="e84c5-112">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="e84c5-112">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="e84c5-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile creare una curva di Bézier quadratica usando la sintassi dell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="e84c5-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="e84c5-114">L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="e84c5-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="e84c5-115">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="e84c5-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84c5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e84c5-116">See also</span></span>

- [<span data-ttu-id="e84c5-117">Creare un arco ellittico</span><span class="sxs-lookup"><span data-stu-id="e84c5-117">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="e84c5-118">Creare una curva di Bézier cubica</span><span class="sxs-lookup"><span data-stu-id="e84c5-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
