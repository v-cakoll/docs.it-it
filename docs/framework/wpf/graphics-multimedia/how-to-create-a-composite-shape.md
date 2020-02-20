---
title: 'Procedura: creare una forma composta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452097"
---
# <a name="how-to-create-a-composite-shape"></a>Procedura: creare una forma composta
In questo esempio viene illustrato come creare forme composite utilizzando oggetti <xref:System.Windows.Media.Geometry> e visualizzarle utilizzando un elemento <xref:System.Windows.Shapes.Path>. Nell'esempio seguente vengono usati una <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>e un <xref:System.Windows.Media.RectangleGeometry> con una <xref:System.Windows.Media.GeometryGroup> per creare una forma composta. Le geometrie vengono quindi disegnate utilizzando un elemento <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 La figura seguente mostra la forma creata nell'esempio precedente.  
  
 ![Geometria composta creata utilizzando GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Geometria composita  
  
 È possibile creare forme più complesse, ad esempio poligoni e forme con segmenti curvi, usando un <xref:System.Windows.Media.PathGeometry>. Per un esempio che illustra come creare una forma usando un <xref:System.Windows.Media.PathGeometry>, vedere [creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  Sebbene in questo esempio venga eseguito il rendering di una forma sullo schermo utilizzando un elemento <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Media.Geometry> oggetti possono essere utilizzati anche per descrivere il contenuto di un <xref:System.Windows.Media.GeometryDrawing> o di una <xref:System.Windows.Media.DrawingContext>. Possono anche essere usati per il ritaglio e l'hit testing.  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).
