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
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="84bef-102">Procedura: creare una forma composta</span><span class="sxs-lookup"><span data-stu-id="84bef-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="84bef-103">In questo esempio viene illustrato come creare forme composite utilizzando oggetti <xref:System.Windows.Media.Geometry> e visualizzarle utilizzando un elemento <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="84bef-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="84bef-104">Nell'esempio seguente vengono usati una <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>e un <xref:System.Windows.Media.RectangleGeometry> con una <xref:System.Windows.Media.GeometryGroup> per creare una forma composta.</span><span class="sxs-lookup"><span data-stu-id="84bef-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="84bef-105">Le geometrie vengono quindi disegnate utilizzando un elemento <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="84bef-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84bef-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="84bef-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="84bef-107">La figura seguente mostra la forma creata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="84bef-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="84bef-108">![Geometria composta creata utilizzando GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="84bef-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="84bef-109">Geometria composita</span><span class="sxs-lookup"><span data-stu-id="84bef-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="84bef-110">È possibile creare forme più complesse, ad esempio poligoni e forme con segmenti curvi, usando un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="84bef-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="84bef-111">Per un esempio che illustra come creare una forma usando un <xref:System.Windows.Media.PathGeometry>, vedere [creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="84bef-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="84bef-112">Sebbene in questo esempio venga eseguito il rendering di una forma sullo schermo utilizzando un elemento <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Media.Geometry> oggetti possono essere utilizzati anche per descrivere il contenuto di un <xref:System.Windows.Media.GeometryDrawing> o di una <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="84bef-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="84bef-113">Possono anche essere usati per il ritaglio e l'hit testing.</span><span class="sxs-lookup"><span data-stu-id="84bef-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="84bef-114">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="84bef-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>
