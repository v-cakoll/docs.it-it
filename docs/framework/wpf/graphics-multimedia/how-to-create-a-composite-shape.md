---
title: 'Procedura: Creare una forma composta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: de9f7972c7a51ea623c3630fe62bb48f6109317e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353491"
---
# <a name="how-to-create-a-composite-shape"></a>Procedura: Creare una forma composta
Questo esempio viene illustrato come creare forme composte tramite <xref:System.Windows.Media.Geometry> degli oggetti e visualizzarli tramite un <xref:System.Windows.Shapes.Path> elemento. Nell'esempio seguente, un <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>e una <xref:System.Windows.Media.RectangleGeometry> vengono usati con un <xref:System.Windows.Media.GeometryGroup> per creare una forma composta. Quindi vengono tracciate le geometrie utilizzando un <xref:System.Windows.Shapes.Path> elemento.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 La figura seguente mostra la forma creata nell'esempio precedente.  
  
 ![Geometria composta creata con GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Geometria composta  
  
 Forme più complesse, ad esempio i poligoni e le forme con segmenti curvi, possono essere create tramite un <xref:System.Windows.Media.PathGeometry>. Per un esempio che illustra come creare forme tramite un <xref:System.Windows.Media.PathGeometry>, vedere [creare una forma utilizzando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  Sebbene questo esempio viene eseguito il rendering di una forma sullo schermo utilizzando un <xref:System.Windows.Shapes.Path> elemento <xref:System.Windows.Media.Geometry> oggetti possono essere usati anche per descrivere il contenuto di un <xref:System.Windows.Media.GeometryDrawing> o un <xref:System.Windows.Media.DrawingContext>. Si può anche essere usati per ritagliare e hit testing.  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://go.microsoft.com/fwlink/?LinkID=159989).
