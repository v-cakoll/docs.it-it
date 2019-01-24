---
title: 'Procedura: Creare una riga utilizzando un oggetto LineGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: fbf44f627ede0fe3bdf7e629728a1e3b858fd30e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690566"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>Procedura: Creare una riga utilizzando un oggetto LineGeometry
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.LineGeometry> classe per descrivere una riga. Oggetto <xref:System.Windows.Media.LineGeometry> è definito per i punti iniziale e finale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.LineGeometry>.  Oggetto <xref:System.Windows.Shapes.Path> elemento viene usato per il rendering della linea.  Poiché non dispone di una riga un'area, il <xref:System.Windows.Shapes.Path> dell'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> non è specificata; invece di <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà vengono utilizzate.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![Un oggetto LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto LineGeometry disegnato da (10,20) a (100,130)  
  
 Le altre classi di geometrie semplici includono <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.EllipseGeometry>. Questi oggetti Geometry, nonché quelle più complesse, è inoltre possibile creare utilizzando un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>. Per altre informazioni, vedere la [panoramica delle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sulle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [Creare una forma composta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [Creare una forma usando un oggetto PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
