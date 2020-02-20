---
title: 'Procedura: creare una curva di Bezier cubica'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: c12bd84fcebb3acebb80bef5f4479ad535fd6691
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452110"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Procedura: creare una curva di Bezier cubica
Questo esempio illustra come creare una curva di Bezier cubica. Per creare una curva di Bezier cubica, usare le classi <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>e <xref:System.Windows.Media.BezierSegment>.  Per visualizzare la geometria risultante, usare un elemento <xref:System.Windows.Shapes.Path> o usarlo con una <xref:System.Windows.Media.GeometryDrawing> o un <xref:System.Windows.Media.DrawingContext>. Negli esempi seguenti viene disegnata una curva di Bezier cubica da (10, 100) a (300, 100). La curva ha punti di controllo di (100, 0) e (200, 200).  
  
## <a name="example"></a>Esempio  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile usare la sintassi di markup abbreviata per descrivere un percorso.  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]è anche possibile creare una curva di Bezier cubica usando i tag Object. L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Vedere anche

- [Creare un arco ellittico](how-to-create-an-elliptical-arc.md)
- [Creare un oggetto LineSegment in un oggetto PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [Creare una curva di Bézier cubica](how-to-create-a-cubic-bezier-curve.md)
- [Creare una curva di Bézier quadratica](how-to-create-a-quadratic-bezier-curve.md)
