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
# <a name="how-to-create-a-quadratic-bezier-curve"></a>Procedura: creare una curva di Bezier quadratica
Questo esempio illustra come creare una curva di Bézier quadratica.  Per creare una curva di Bézier quadratica, usare le classi <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>e <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti viene disegnata una curva di Bézier quadratica da (10.100) a (300.100). La curva dispone di un punto di controllo di (200.200).  
  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile usare la sintassi degli attributi per descrivere un percorso.  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 [xaml]  
  
 Si noti che questa sintassi di attributo crea effettivamente un <xref:System.Windows.Media.StreamGeometry>, una versione più leggera di un <xref:System.Windows.Media.PathGeometry>. Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile creare una curva di Bézier quadratica usando la sintassi dell'elemento oggetto. L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Vedere anche

- [Creare un arco ellittico](how-to-create-an-elliptical-arc.md)
- [Creare una curva di Bézier cubica](how-to-create-a-cubic-bezier-curve.md)
