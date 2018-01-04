---
title: "Procedura: creare più percorsi secondari in un PathGeometry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7945728386c01d6137cbc422f0d7fb410a18d57e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="d4dd7-102">Procedura: creare più percorsi secondari in un PathGeometry</span><span class="sxs-lookup"><span data-stu-id="d4dd7-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="d4dd7-103">In questo esempio viene illustrato come creare più percorsi secondari in un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d4dd7-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="d4dd7-104">Per creare più percorsi secondari, creare un <xref:System.Windows.Media.PathFigure> per ogni percorso secondario.</span><span class="sxs-lookup"><span data-stu-id="d4dd7-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4dd7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4dd7-105">Example</span></span>  
 <span data-ttu-id="d4dd7-106">L'esempio seguente crea due percorsi secondari, ognuno un triangolo.</span><span class="sxs-lookup"><span data-stu-id="d4dd7-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="d4dd7-107">Nell'esempio seguente viene illustrato come creare più percorsi secondari utilizzando un <xref:System.Windows.Shapes.Path> e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintassi degli attributi.</span><span class="sxs-lookup"><span data-stu-id="d4dd7-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="d4dd7-108">Ogni `M` crea un nuovo percorso secondario in modo che nell'esempio vengono creati due percorsi secondari che ogni Disegna un triangolo.</span><span class="sxs-lookup"><span data-stu-id="d4dd7-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="d4dd7-109">(Si noti che la sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d4dd7-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="d4dd7-110">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="d4dd7-110">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4dd7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4dd7-111">See Also</span></span>  
 [<span data-ttu-id="d4dd7-112">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="d4dd7-112">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
