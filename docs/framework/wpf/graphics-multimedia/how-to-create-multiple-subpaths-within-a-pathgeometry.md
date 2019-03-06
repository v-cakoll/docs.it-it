---
title: 'Procedura: Creare più percorsi secondari in un PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 0b57d0441c1aa9d5972af1f1c6b989aacba7f87f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353368"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="bc8f9-102">Procedura: Creare più percorsi secondari in un PathGeometry</span><span class="sxs-lookup"><span data-stu-id="bc8f9-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="bc8f9-103">Questo esempio viene illustrato come creare più percorsi secondari in un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="bc8f9-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="bc8f9-104">Per creare più percorsi secondari, è necessario creare un <xref:System.Windows.Media.PathFigure> per ogni sottopercorso.</span><span class="sxs-lookup"><span data-stu-id="bc8f9-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc8f9-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc8f9-105">Example</span></span>  
 <span data-ttu-id="bc8f9-106">L'esempio seguente crea due percorsi secondari, ognuno di essi un triangolo.</span><span class="sxs-lookup"><span data-stu-id="bc8f9-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="bc8f9-107">Nell'esempio seguente viene illustrato come creare più percorsi secondari usando un <xref:System.Windows.Shapes.Path> e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintassi degli attributi.</span><span class="sxs-lookup"><span data-stu-id="bc8f9-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="bc8f9-108">Ogni `M` crea un nuovo percorso secondario in modo che l'esempio crea due percorsi secondari che ognuno Disegna un triangolo.</span><span class="sxs-lookup"><span data-stu-id="bc8f9-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="bc8f9-109">(Si noti che questa sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di una <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="bc8f9-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="bc8f9-110">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="bc8f9-110">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc8f9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc8f9-111">See also</span></span>
- [<span data-ttu-id="bc8f9-112">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="bc8f9-112">Geometry Overview</span></span>](geometry-overview.md)
