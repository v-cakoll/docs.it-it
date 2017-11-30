---
title: 'Procedura: creare una curva di Bezier quadratica'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8320889f931e4482091b15bd9295c77a36d6d1e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="5e483-102">Procedura: creare una curva di Bezier quadratica</span><span class="sxs-lookup"><span data-stu-id="5e483-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="5e483-103">In questo esempio viene illustrato come creare una curva di Bézier quadratica.</span><span class="sxs-lookup"><span data-stu-id="5e483-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="5e483-104">Per creare una curva di Bézier quadratica, utilizzare il <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.QuadraticBezierSegment> classi.</span><span class="sxs-lookup"><span data-stu-id="5e483-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e483-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e483-105">Example</span></span>  
 <span data-ttu-id="5e483-106">Negli esempi seguenti, una curva di Bézier quadratica viene disegnata da (10, 100) a (300, 100).</span><span class="sxs-lookup"><span data-stu-id="5e483-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="5e483-107">La curva presenta un punto di controllo di valore (200, 200).</span><span class="sxs-lookup"><span data-stu-id="5e483-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="5e483-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="5e483-108">[xaml]</span></span>  
  
 <span data-ttu-id="5e483-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile utilizzare la sintassi degli attributi per descrivere un percorso.</span><span class="sxs-lookup"><span data-stu-id="5e483-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="5e483-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="5e483-110">[xaml]</span></span>  
  
 <span data-ttu-id="5e483-111">(Si noti che la sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="5e483-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="5e483-112">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="5e483-112">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="5e483-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile disegnare una curva di Bézier quadratica sintassi dell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="5e483-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="5e483-114">L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="5e483-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="5e483-115">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="5e483-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e483-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e483-116">See Also</span></span>  
 [<span data-ttu-id="5e483-117">Creare un arco ellittico</span><span class="sxs-lookup"><span data-stu-id="5e483-117">Create an Elliptical Arc</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [<span data-ttu-id="5e483-118">Creare una curva di Bézier cubica</span><span class="sxs-lookup"><span data-stu-id="5e483-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
