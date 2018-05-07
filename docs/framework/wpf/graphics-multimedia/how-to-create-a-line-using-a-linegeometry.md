---
title: 'Procedura: creare una riga utilizzando un oggetto LineGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: 8db33fc5c611dcbcae50c71ada1c6b6f9fd9bd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>Procedura: creare una riga utilizzando un oggetto LineGeometry
In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Media.LineGeometry> classe per descrivere una riga. Oggetto <xref:System.Windows.Media.LineGeometry> è definito per i punti iniziale e finale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.LineGeometry>.  Oggetto <xref:System.Windows.Shapes.Path> elemento viene usato per il rendering della linea.  Poiché una riga non presenta un'area, il <xref:System.Windows.Shapes.Path> dell'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> non è specificato; invece di <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà vengono utilizzate.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto LineGeometry disegnato da (10,20) a (100,130)  
  
 Le altre classi geometry semplice <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.EllipseGeometry>. Le geometrie, come quelle più complesse, possono essere create anche usando un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>. Per ulteriori informazioni, vedere il [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Creare una forma composta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [Creare una forma usando un oggetto PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
