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
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Procedura: creare più percorsi secondari in un PathGeometry
In questo esempio viene illustrato come creare più percorsi secondari in un <xref:System.Windows.Media.PathGeometry>. Per creare più percorsi secondari, creare un <xref:System.Windows.Media.PathFigure> per ogni percorso secondario.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea due percorsi secondari, ognuno un triangolo.  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 Nell'esempio seguente viene illustrato come creare più percorsi secondari utilizzando un <xref:System.Windows.Shapes.Path> e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintassi degli attributi. Ogni `M` crea un nuovo percorso secondario in modo che nell'esempio vengono creati due percorsi secondari che ogni Disegna un triangolo.  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Si noti che la sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di un <xref:System.Windows.Media.PathGeometry>. Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
