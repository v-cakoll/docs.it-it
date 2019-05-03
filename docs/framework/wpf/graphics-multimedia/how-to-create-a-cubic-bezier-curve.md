---
title: 'Procedura: Creare una curva di Bézier cubica'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: 36544abc774b7fe82c2ff47483cfedd6fb13e344
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054627"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Procedura: Creare una curva di Bézier cubica
In questo esempio viene illustrato come creare una curva di Bézier cubica. Per creare una curva di Bézier cubica continua, usare il <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.BezierSegment> classi.  Per visualizzare la geometria risulta, usare una <xref:System.Windows.Shapes.Path> elemento, o usarlo con un <xref:System.Windows.Media.GeometryDrawing> o un <xref:System.Windows.Media.DrawingContext>. Negli esempi seguenti, una curva di Bézier cubica viene disegnata da (10, 100) a (300, 100). La curva ha punti di controllo di (100, 0) e (200, 200).  
  
## <a name="example"></a>Esempio  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile utilizzare la sintassi di markup abbreviato per descrivere un tracciato.  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile disegnare una curva di Bézier cubica con il tag object. L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Vedere anche

- [Creare un arco ellittico](how-to-create-an-elliptical-arc.md)
- [Creare un oggetto LineSegment in un oggetto PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [Creare una curva di Bézier cubica](how-to-create-a-cubic-bezier-curve.md)
- [Creare una curva di Bézier quadratica](how-to-create-a-quadratic-bezier-curve.md)
