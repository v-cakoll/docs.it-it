---
title: 'Procedura: creare un arco ellittico'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eeb93cefd2e55e80f27922feab788698653f405e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-elliptical-arc"></a>Procedura: creare un arco ellittico
In questo esempio viene illustrato come disegnare un arco ellittico. Per creare un arco ellittico, utilizzare il <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.ArcSegment> classi.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti, un arco ellittico viene tracciato dal (10, 100) a (200,100). L'arco ha un <xref:System.Windows.Media.ArcSegment.Size%2A> di 100 per 50 pixel indipendenti dal dispositivo, un <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> di 45 gradi, un <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> l'impostazione di `true`e un <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> di <xref:System.Windows.Media.SweepDirection.Counterclockwise>.  
  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile utilizzare la sintassi degli attributi per descrivere un percorso.  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (Si noti che la sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di un <xref:System.Windows.Media.PathGeometry>. Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile creare un arco ellittico anche in modo esplicito con il tag object. Di seguito è equivalente alla precedente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere il [geometrie esempio](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Vedere anche  
 [Creare una curva di Bézier quadratica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [Creare una curva di Bézier cubica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
