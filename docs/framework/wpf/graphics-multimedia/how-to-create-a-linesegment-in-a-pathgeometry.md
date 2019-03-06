---
title: 'Procedura: Creare un oggetto LineSegment in un oggetto PathGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
ms.openlocfilehash: a6862ab02c288f9cfd1fac4a8c22079b0cf91016
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356182"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="e617f-102">Procedura: Creare un oggetto LineSegment in un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="e617f-102">How to: Create a LineSegment in a PathGeometry</span></span>
<span data-ttu-id="e617f-103">Questo esempio illustra come creare un segmento di linea.</span><span class="sxs-lookup"><span data-stu-id="e617f-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="e617f-104">Per creare un segmento di linea, utilizzare il <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.LineSegment> classi.</span><span class="sxs-lookup"><span data-stu-id="e617f-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e617f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e617f-105">Example</span></span>  
 <span data-ttu-id="e617f-106">Gli esempi seguenti disegnano un <xref:System.Windows.Media.LineSegment> da (10, 50) a (200, 70).</span><span class="sxs-lookup"><span data-stu-id="e617f-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="e617f-107">La figura seguente mostra l'oggetto risultante <xref:System.Windows.Media.LineSegment>; è stato aggiunto uno sfondo alla griglia per visualizzare il sistema di coordinate.</span><span class="sxs-lookup"><span data-stu-id="e617f-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>  
  
 <span data-ttu-id="e617f-108">![Un oggetto LineSegment in PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")</span><span class="sxs-lookup"><span data-stu-id="e617f-108">![A LineSegment in a PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")</span></span>  
<span data-ttu-id="e617f-109">Oggetto LineSegment disegnato da (10,50) a (200,70)</span><span class="sxs-lookup"><span data-stu-id="e617f-109">A LineSegment drawn from (10,50) to (200,70)</span></span>  
  
 <span data-ttu-id="e617f-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="e617f-110">[xaml]</span></span>  
  
 <span data-ttu-id="e617f-111">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] è possibile usare la sintassi di attributo per descrivere un tracciato.</span><span class="sxs-lookup"><span data-stu-id="e617f-111">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1"    
  Data="M 10,50 L 200,70" />  
```  
  
 <span data-ttu-id="e617f-112">[xaml]</span><span class="sxs-lookup"><span data-stu-id="e617f-112">[xaml]</span></span>  
  
 <span data-ttu-id="e617f-113">(Si noti che questa sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di una <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="e617f-113">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="e617f-114">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="e617f-114">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="e617f-115">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è anche possibile disegnare un segmento di linea usando la sintassi degli elementi oggetto.</span><span class="sxs-lookup"><span data-stu-id="e617f-115">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="e617f-116">L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="e617f-116">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1">  
  <Path.Data>  
    <PathGeometry>  
      <PathFigure StartPoint="10,50">  
        <LineSegment Point="200,70" />  
      </PathFigure>  
    </PathGeometry>  
  </Path.Data>  
</Path>  
```  
  
```csharp  
PathFigure myPathFigure = new PathFigure();  
myPathFigure.StartPoint = new Point(10, 50);  
  
LineSegment myLineSegment = new LineSegment();  
myLineSegment.Point = new Point(200, 70);  
  
PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();  
myPathSegmentCollection.Add(myLineSegment);  
  
myPathFigure.Segments = myPathSegmentCollection;  
  
PathFigureCollection myPathFigureCollection = new PathFigureCollection();  
myPathFigureCollection.Add(myPathFigure);  
  
PathGeometry myPathGeometry = new PathGeometry();  
myPathGeometry.Figures = myPathFigureCollection;  
  
Path myPath = new Path();  
myPath.Stroke = Brushes.Black;  
myPath.StrokeThickness = 1;  
myPath.Data = myPathGeometry;  
```  
  
```vb  
Dim myPathFigure As New PathFigure()  
            myPathFigure.StartPoint = New Point(10, 50)  
  
            Dim myLineSegment As New LineSegment()  
            myLineSegment.Point = New Point(200, 70)  
  
            Dim myPathSegmentCollection As New PathSegmentCollection()  
            myPathSegmentCollection.Add(myLineSegment)  
  
            myPathFigure.Segments = myPathSegmentCollection  
  
            Dim myPathFigureCollection As New PathFigureCollection()  
            myPathFigureCollection.Add(myPathFigure)  
  
            Dim myPathGeometry As New PathGeometry()  
            myPathGeometry.Figures = myPathFigureCollection  
  
            Dim myPath As New Path()  
            myPath.Stroke = Brushes.Black  
            myPath.StrokeThickness = 1  
            myPath.Data = myPathGeometry  
```  
  
 <span data-ttu-id="e617f-117">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="e617f-117">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e617f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e617f-118">See also</span></span>
- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [<span data-ttu-id="e617f-119">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="e617f-119">Geometry Overview</span></span>](geometry-overview.md)
