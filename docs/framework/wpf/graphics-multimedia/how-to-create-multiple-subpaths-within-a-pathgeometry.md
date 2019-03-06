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
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Procedura: Creare più percorsi secondari in un PathGeometry
Questo esempio viene illustrato come creare più percorsi secondari in un <xref:System.Windows.Media.PathGeometry>. Per creare più percorsi secondari, è necessario creare un <xref:System.Windows.Media.PathFigure> per ogni sottopercorso.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea due percorsi secondari, ognuno di essi un triangolo.  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 Nell'esempio seguente viene illustrato come creare più percorsi secondari usando un <xref:System.Windows.Shapes.Path> e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintassi degli attributi. Ogni `M` crea un nuovo percorso secondario in modo che l'esempio crea due percorsi secondari che ognuno Disegna un triangolo.  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Si noti che questa sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di una <xref:System.Windows.Media.PathGeometry>. Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
