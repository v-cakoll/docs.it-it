---
title: 'Procedura: creare più percorsi secondari in un PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 5b129b1bacb5dc2cba87376e8df70e115a5ebd72
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559331"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="0e5b8-102">Procedura: creare più percorsi secondari in un PathGeometry</span><span class="sxs-lookup"><span data-stu-id="0e5b8-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="0e5b8-103">In questo esempio viene illustrato come creare più percorsi secondari in un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="0e5b8-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="0e5b8-104">Per creare più percorsi secondari, creare un <xref:System.Windows.Media.PathFigure> per ogni percorso secondario.</span><span class="sxs-lookup"><span data-stu-id="0e5b8-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e5b8-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e5b8-105">Example</span></span>  
 <span data-ttu-id="0e5b8-106">L'esempio seguente crea due percorsi secondari, ognuno un triangolo.</span><span class="sxs-lookup"><span data-stu-id="0e5b8-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="0e5b8-107">Nell'esempio seguente viene illustrato come creare più percorsi secondari utilizzando un <xref:System.Windows.Shapes.Path> e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintassi degli attributi.</span><span class="sxs-lookup"><span data-stu-id="0e5b8-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="0e5b8-108">Ogni `M` crea un nuovo percorso secondario in modo che nell'esempio vengono creati due percorsi secondari che ogni Disegna un triangolo.</span><span class="sxs-lookup"><span data-stu-id="0e5b8-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="0e5b8-109">(Si noti che la sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="0e5b8-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="0e5b8-110">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="0e5b8-110">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5b8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e5b8-111">See Also</span></span>  
 [<span data-ttu-id="0e5b8-112">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="0e5b8-112">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
