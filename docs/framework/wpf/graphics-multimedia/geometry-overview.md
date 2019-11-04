---
title: Cenni preliminari sulle classi Geometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometry classes [WPF]
- graphics [WPF], geometry classes
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
ms.openlocfilehash: f45c13e1af9bc2d1f75da11b13a2c03936b136c1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455018"
---
# <a name="geometry-overview"></a>Cenni preliminari sulle classi Geometry
In questa panoramica viene descritto come utilizzare le classi <xref:System.Windows.Media.Geometry> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] per descrivere le forme. Questo argomento contrasta anche le differenze tra <xref:System.Windows.Media.Geometry> oggetti e <xref:System.Windows.Shapes.Shape> elementi.  

<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>Definizione di Geometry  
 La classe <xref:System.Windows.Media.Geometry> e le classi che derivano da essa, ad esempio <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry>e <xref:System.Windows.Media.CombinedGeometry>, consentono di descrivere la geometria di una forma 2D. Queste descrizioni geometriche hanno molti usi, come la definizione di una forma da disegnare sullo schermo o la definizione di aree di hit test e di ritaglio. È anche possibile usare un oggetto Geometry per definire un tracciato di animazione.  
  
 <xref:System.Windows.Media.Geometry> oggetti possono essere semplici, ad esempio rettangoli e cerchi, o composti, creati da due o più oggetti Geometry.  È possibile creare geometrie più complesse usando le classi <xref:System.Windows.Media.PathGeometry> e <xref:System.Windows.Media.StreamGeometry>, che consentono di descrivere archi e curve.  
  
 Poiché un <xref:System.Windows.Media.Geometry> è un tipo di <xref:System.Windows.Freezable>, <xref:System.Windows.Media.Geometry> oggetti forniscono diverse funzionalità speciali: possono essere dichiarate come [risorse](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivise tra più oggetti, rese di sola lettura per migliorare le prestazioni, clonate e rese thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite dagli oggetti <xref:System.Windows.Freezable>, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>Geometrie e forme  
 Le classi <xref:System.Windows.Media.Geometry> e <xref:System.Windows.Shapes.Shape> sembrano simili in quanto entrambe descrivono forme 2D (confrontare <xref:System.Windows.Media.EllipseGeometry> e <xref:System.Windows.Shapes.Ellipse> ad esempio), ma esistono differenze importanti.  
  
 Per uno, la classe <xref:System.Windows.Media.Geometry> eredita dalla classe <xref:System.Windows.Freezable> mentre la classe <xref:System.Windows.Shapes.Shape> eredita da <xref:System.Windows.FrameworkElement>. Poiché si tratta di elementi, <xref:System.Windows.Shapes.Shape> gli oggetti possono eseguire il rendering e partecipare al sistema di layout, mentre <xref:System.Windows.Media.Geometry> oggetti non possono.  
  
 Sebbene <xref:System.Windows.Shapes.Shape> oggetti siano più facilmente utilizzabili rispetto agli oggetti <xref:System.Windows.Media.Geometry>, <xref:System.Windows.Media.Geometry> oggetti sono più versatili. Mentre un oggetto <xref:System.Windows.Shapes.Shape> viene usato per eseguire il rendering della grafica 2D, un oggetto <xref:System.Windows.Media.Geometry> può essere usato per definire l'area geometrica per la grafica 2D, definire un'area per il ritaglio o definire un'area per l'hit testing, ad esempio.  
  
### <a name="the-path-shape"></a>Classe Path di Shape  
 Una <xref:System.Windows.Shapes.Shape>, la classe <xref:System.Windows.Shapes.Path>, USA effettivamente un <xref:System.Windows.Media.Geometry> per descrivere il contenuto. Impostando la proprietà <xref:System.Windows.Shapes.Path.Data%2A> della <xref:System.Windows.Shapes.Path> con un <xref:System.Windows.Media.Geometry> e impostando le proprietà <xref:System.Windows.Shapes.Shape.Fill%2A> e <xref:System.Windows.Shapes.Shape.Stroke%2A>, è possibile eseguire il rendering di un <xref:System.Windows.Media.Geometry>.  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>Proprietà comuni che richiedono un oggetto Geometry  
 Come indicato nelle sezioni precedenti, gli oggetti Geometry possono essere usati con altri oggetti per vari scopi, ad esempio il disegno di forme, l'animazione e il ritaglio. Nella tabella seguente sono elencate diverse classi con proprietà che accettano un oggetto <xref:System.Windows.Media.Geometry>.  
  
|Digitare|proprietà|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>Tipi di oggetti Geometry semplici  
 La classe base per tutte le geometrie è la classe astratta <xref:System.Windows.Media.Geometry>.  Le classi che derivano dalla classe <xref:System.Windows.Media.Geometry> possono essere raggruppate approssimativamente in tre categorie: geometrie semplici, geometrie di percorso e geometrie composite.  
  
 Le classi Geometry semplici includono <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>e <xref:System.Windows.Media.EllipseGeometry> e vengono usate per creare forme geometriche di base, ad esempio linee, rettangoli e cerchi.  
  
- Un <xref:System.Windows.Media.LineGeometry> viene definito specificando il punto iniziale della riga e il punto finale.  
  
- Un <xref:System.Windows.Media.RectangleGeometry> viene definito con una struttura <xref:System.Windows.Rect> che specifica la posizione relativa e l'altezza e la larghezza. È possibile creare un rettangolo arrotondato impostando le proprietà <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> e <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>.  
  
- Una <xref:System.Windows.Media.EllipseGeometry> è definita da un punto centrale, un raggio x e un raggio y.  Gli esempi seguenti mostrano come creare geometrie semplici per il rendering e per il ritaglio.  
  
 Queste stesse forme, oltre a forme più complesse, possono essere create usando un <xref:System.Windows.Media.PathGeometry> o combinando oggetti Geometry, ma queste classi forniscono un mezzo più semplice per la produzione di queste forme geometriche di base.  
  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.LineGeometry>.  Come indicato in precedenza, un oggetto <xref:System.Windows.Media.Geometry> non è in grado di disegnare se stesso, quindi nell'esempio viene utilizzata una forma <xref:System.Windows.Shapes.Path> per eseguire il rendering della riga.  Poiché una riga non ha area, l'impostazione della proprietà <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Path> non avrà alcun effetto; vengono invece specificate solo le proprietà <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Oggetto LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto LineGeometry disegnato da (10,20) a (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.EllipseGeometry>.  Negli esempi viene impostato il <xref:System.Windows.Media.EllipseGeometry.Center%2A> della <xref:System.Windows.Media.EllipseGeometry> è impostato sul punto `50,50` e il raggio x e il raggio y sono entrambi impostati su `50`, che crea un cerchio con un diametro di 100.  L'interno dell'ellisse viene disegnato assegnando un valore alla proprietà Fill dell'elemento Path, in questo caso <xref:System.Windows.Media.Brushes.Gold%2A>. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Oggetto EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
Un oggetto EllipseGeometry tracciato a (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.RectangleGeometry>.  La posizione e le dimensioni del rettangolo sono definite da una struttura <xref:System.Windows.Rect>. La posizione è `50,50` e l'altezza e la larghezza sono entrambe `25`; viene creato un quadrato. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Oggetto RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Un oggetto RectangleGeometry tracciato a 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Media.EllipseGeometry> come area di ritaglio per un'immagine.  Un oggetto <xref:System.Windows.Controls.Image> viene definito con una <xref:System.Windows.FrameworkElement.Width%2A> di 200 e un <xref:System.Windows.FrameworkElement.Height%2A> di 150.  Un <xref:System.Windows.Media.EllipseGeometry> con un valore <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> 100, un valore <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> 75 e un valore <xref:System.Windows.Media.EllipseGeometry.Center%2A> pari a 100, 75 viene impostato sulla proprietà <xref:System.Windows.UIElement.Clip%2A> dell'immagine.  Verrà visualizzata solo la parte dell'immagine che è all'interno dell'area dell'ellisse. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Immagine con e senza area di ritaglio](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Oggetto EllipseGeometry usato per ritagliare un controllo Image  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>Geometrie di tracciato  
 La classe <xref:System.Windows.Media.PathGeometry> e l'equivalente leggero, ovvero la classe <xref:System.Windows.Media.StreamGeometry>, forniscono i mezzi per descrivere più figure complesse costituite da archi, curve e linee.  
  
 Il fulcro di un <xref:System.Windows.Media.PathGeometry> è costituito da una raccolta di oggetti <xref:System.Windows.Media.PathFigure>, denominati perché ogni figura descrive una forma discreta nell'<xref:System.Windows.Media.PathGeometry>. Ogni <xref:System.Windows.Media.PathFigure> è costituita da uno o più oggetti <xref:System.Windows.Media.PathSegment>, ciascuno dei quali descrive un segmento della figura.  
  
 Esistono diversi tipi di segmenti.  
  
|Tipo di segmento|Descrizione|Esempio|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco ellittico tra due punti.|[Creare un arco ellittico](how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva di Bézier cubica tra due punti.|[Creare una curva di Bézier cubica](how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Crea una linea tra due punti.|[Creare un oggetto LineSegment in un oggetto PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie di curve di Bézier cubiche.|Vedere la pagina relativa al tipo di <xref:System.Windows.Media.PolyBezierSegment>.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie di linee.|Vedere la pagina relativa al tipo di <xref:System.Windows.Media.PolyLineSegment>.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie di curve di Bézier quadratiche.|Vedere la pagina <xref:System.Windows.Media.PolyQuadraticBezierSegment>.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva di Bézier quadratica.|[Creare una curva di Bézier quadratica](how-to-create-a-quadratic-bezier-curve.md).|  
  
 I segmenti all'interno di un <xref:System.Windows.Media.PathFigure> vengono combinati in una singola forma geometrica con il punto finale di ogni segmento che è il punto iniziale del segmento successivo. La proprietà <xref:System.Windows.Media.PathFigure.StartPoint%2A> di un <xref:System.Windows.Media.PathFigure> specifica il punto da cui viene disegnato il primo segmento. Ogni segmento successivo inizia in corrispondenza del punto finale del segmento precedente. È possibile, ad esempio, definire una linea verticale da `10,50` a `10,150` impostando la proprietà <xref:System.Windows.Media.PathFigure.StartPoint%2A> su `10,50` e creando un <xref:System.Windows.Media.LineSegment> con un'impostazione della proprietà <xref:System.Windows.Media.LineSegment.Point%2A> di `10,150`.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Media.PathGeometry> semplice costituito da un singolo <xref:System.Windows.Media.PathFigure> con un <xref:System.Windows.Media.LineSegment> e viene visualizzato utilizzando un <xref:System.Windows.Shapes.Path> elemento. Il <xref:System.Windows.Media.PathFigure.StartPoint%2A> dell'oggetto <xref:System.Windows.Media.PathFigure> è impostato su `10,20` e viene definito un <xref:System.Windows.Media.LineSegment> con un punto finale di `100,130`. Nella figura seguente viene illustrato il <xref:System.Windows.Media.PathGeometry> creato in questo esempio.  
  
 ![Oggetto LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto PathGeometry che contiene un singolo oggetto LineSegment  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Vale la pena contrastare questo esempio con l'esempio precedente <xref:System.Windows.Media.LineGeometry>.  La sintassi utilizzata per un <xref:System.Windows.Media.PathGeometry> è molto più dettagliata rispetto a quella usata per un <xref:System.Windows.Media.LineGeometry>semplice e può essere utile usare la classe <xref:System.Windows.Media.LineGeometry> in questo caso, ma la sintassi dettagliata del <xref:System.Windows.Media.PathGeometry> consente aree geometriche estremamente complesse e complesse.  
  
 È possibile creare geometrie più complesse utilizzando una combinazione di oggetti <xref:System.Windows.Media.PathSegment>.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.BezierSegment>, un <xref:System.Windows.Media.LineSegment>e un <xref:System.Windows.Media.ArcSegment> per creare la forma. Nell'esempio viene innanzitutto creata una curva di Bezier cubica definendo quattro punti, ovvero un punto iniziale, ovvero il punto finale del segmento precedente, un punto finale (<xref:System.Windows.Media.BezierSegment.Point3%2A>) e due punti di controllo (<xref:System.Windows.Media.BezierSegment.Point1%2A> e <xref:System.Windows.Media.BezierSegment.Point2%2A>).  I due punti di controllo di una curva di Beziér cubica si comportano come magneti, ovvero attraggono parti della linea che sarebbe altrimenti una linea retta, producendo una curva. Il primo punto di controllo, <xref:System.Windows.Media.BezierSegment.Point1%2A>, influiscono sulla parte iniziale della curva; il secondo punto di controllo, <xref:System.Windows.Media.BezierSegment.Point2%2A>, influiscono sulla parte finale della curva.  
  
 Viene quindi aggiunto un <xref:System.Windows.Media.LineSegment>, che viene tracciato tra il punto finale del <xref:System.Windows.Media.BezierSegment> precedente che lo precedeva fino al punto specificato dalla relativa proprietà <xref:System.Windows.Media.LineSegment>.  
  
 Viene quindi aggiunto un <xref:System.Windows.Media.ArcSegment>, che viene disegnato dal punto finale del <xref:System.Windows.Media.LineSegment> precedente al punto specificato dalla relativa proprietà <xref:System.Windows.Media.ArcSegment.Point%2A>. Nell'esempio vengono specificati anche il raggio x e y (<xref:System.Windows.Media.ArcSegment.Size%2A>) dell'arco, un angolo di rotazione (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>), un flag che indica la dimensione dell'angolo dell'arco risultante (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>) e un valore che indica la direzione in cui viene disegnato l'arco (<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>). La figura seguente mostra la forma creata da questo esempio.  
  
 ![Oggetto PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 È possibile creare geometrie ancora più complesse usando più <xref:System.Windows.Media.PathFigure> oggetti all'interno di un <xref:System.Windows.Media.PathGeometry>.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Media.PathGeometry> con due oggetti <xref:System.Windows.Media.PathFigure>, ognuno dei quali contiene più oggetti <xref:System.Windows.Media.PathSegment>.  Vengono usati i <xref:System.Windows.Media.PathFigure> dell'esempio precedente e una <xref:System.Windows.Media.PathFigure> con una <xref:System.Windows.Media.PolyLineSegment> e una <xref:System.Windows.Media.QuadraticBezierSegment>.  Un <xref:System.Windows.Media.PolyLineSegment> viene definito con una matrice di punti e il <xref:System.Windows.Media.QuadraticBezierSegment> viene definito con un punto di controllo e un punto finale. La figura seguente mostra la forma creata da questo esempio.  
  
 ![Oggetto PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
Un oggetto PathGeometry con più figure  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Analogamente alla classe <xref:System.Windows.Media.PathGeometry>, un <xref:System.Windows.Media.StreamGeometry> definisce una forma geometrica complessa che può contenere curve, archi e linee. A differenza di un <xref:System.Windows.Media.PathGeometry>, il contenuto di un <xref:System.Windows.Media.StreamGeometry> non supporta data binding, l'animazione o la modifica. Usare un <xref:System.Windows.Media.StreamGeometry> quando è necessario descrivere una geometria complessa, ma non si desidera il sovraccarico del supporto di data binding, animazioni o modifiche. Grazie alla relativa efficienza, la classe <xref:System.Windows.Media.StreamGeometry> rappresenta una scelta ottimale per la descrizione degli Adorner.  
  
 Per un esempio, vedere [Creare forme tramite un oggetto StreamGeometry](how-to-create-a-shape-using-a-streamgeometry.md).  
  
### <a name="path-markup-syntax"></a>Sintassi di markup del percorso  
 I tipi <xref:System.Windows.Media.PathGeometry> e <xref:System.Windows.Media.StreamGeometry> supportano la sintassi degli attributi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] usando una serie speciale di comandi di spostamento e di progetto. Per altre informazioni, vedere [Sintassi di markup del tracciato](path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>Oggetti Geometry composti  
 È possibile creare oggetti Geometry compositi utilizzando un <xref:System.Windows.Media.GeometryGroup>, un <xref:System.Windows.Media.CombinedGeometry>o chiamando il metodo di <xref:System.Windows.Media.Geometry> statico <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
- L'oggetto <xref:System.Windows.Media.CombinedGeometry> e il metodo <xref:System.Windows.Media.Geometry.Combine%2A> eseguono un'operazione booleana per combinare l'area definita da due geometrie. <xref:System.Windows.Media.Geometry> oggetti senza area vengono eliminati. È possibile combinare solo due oggetti <xref:System.Windows.Media.Geometry> (anche se queste due geometrie possono essere anche geometrie composite).  
  
- La classe <xref:System.Windows.Media.GeometryGroup> crea una combinazione degli oggetti <xref:System.Windows.Media.Geometry> che contiene senza combinare la relativa area. È possibile aggiungere un numero qualsiasi di oggetti <xref:System.Windows.Media.Geometry> a un <xref:System.Windows.Media.GeometryGroup>. Per un esempio, vedere [Creare una forma composta](how-to-create-a-composite-shape.md).  
  
 Poiché non eseguono un'operazione di combinazione, l'utilizzo di <xref:System.Windows.Media.GeometryGroup> oggetti fornisce vantaggi in merito alle prestazioni rispetto all'utilizzo di <xref:System.Windows.Media.CombinedGeometry> oggetti o del metodo <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>Geometrie combinate  
 La sezione precedente ha indicato l'oggetto <xref:System.Windows.Media.CombinedGeometry> e il metodo <xref:System.Windows.Media.Geometry.Combine%2A> combinano l'area definita dalle geometrie che contengono. L'enumerazione <xref:System.Windows.Media.GeometryCombineMode> specifica il modo in cui vengono combinate le geometrie. I valori possibili per la proprietà <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> sono: <xref:System.Windows.Media.GeometryCombineMode.Union>, <xref:System.Windows.Media.GeometryCombineMode.Intersect>, <xref:System.Windows.Media.GeometryCombineMode.Exclude>e <xref:System.Windows.Media.GeometryCombineMode.Xor>.  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione Unione.  Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che i <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con un offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Risultati della modalità di combinazione Unione](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di <xref:System.Windows.Media.GeometryCombineMode.Xor>.  Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che i <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con un offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Risultati della modalità di combinazione Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Per altri esempi, vedere [Creare una forma composta](how-to-create-a-composite-shape.md) e [Creare una geometria combinata](how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dalla classe <xref:System.Windows.Freezable>, la classe <xref:System.Windows.Media.Geometry> fornisce diverse funzionalità speciali: <xref:System.Windows.Media.Geometry> oggetti possono essere dichiarati come [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivisi tra più oggetti, resi di sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite dagli oggetti <xref:System.Windows.Freezable>, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>Altre funzionalità dell'oggetto Geometry  
 La classe <xref:System.Windows.Media.Geometry> fornisce anche metodi di utilità utili, come i seguenti:  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A>: Ottiene l'area del <xref:System.Windows.Media.Geometry>.  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A>: determina se la geometria contiene un'altra <xref:System.Windows.Media.Geometry>.  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A>: determina se il tratto di un <xref:System.Windows.Media.Geometry> contiene un punto specificato.  
  
 Per un elenco completo dei metodi, vedere la classe <xref:System.Windows.Media.Geometry>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Grafica bidimensionale e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Sintassi di markup del percorso](path-markup-syntax.md)
- [Procedure relative alle proprietà](geometries-how-to-topics.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
