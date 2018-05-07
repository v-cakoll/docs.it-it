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
ms.openlocfilehash: 01c460ae18c489a21c860c6d2b10f551e6e68242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="geometry-overview"></a>Cenni preliminari sulle classi Geometry
Questa panoramica viene descritto come utilizzare il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> classi per descrivere le forme. In questo argomento vengono confrontate le differenze tra <xref:System.Windows.Media.Geometry> oggetti e <xref:System.Windows.Shapes.Shape> elementi.  
  
  
<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>Definizione di Geometry  
 Il <xref:System.Windows.Media.Geometry> classe e le classi che derivano da essa, ad esempio <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry>, e <xref:System.Windows.Media.CombinedGeometry>, consentono di descrivere la geometria di una forma 2D. Queste descrizioni geometriche hanno molti usi, come la definizione di una forma da disegnare sullo schermo o la definizione di aree di hit test e di ritaglio. È anche possibile usare un oggetto Geometry per definire un tracciato di animazione.  
  
 <xref:System.Windows.Media.Geometry> gli oggetti possono essere semplici, quali rettangoli e cerchi o composita, creato da due o più oggetti di geometria.  Geometrie più complesse possono essere create utilizzando il <xref:System.Windows.Media.PathGeometry> e <xref:System.Windows.Media.StreamGeometry> classi, che consentono di descrivere archi e curve.  
  
 Poiché un <xref:System.Windows.Media.Geometry> è un tipo di <xref:System.Windows.Freezable>, <xref:System.Windows.Media.Geometry> oggetti forniscono diverse funzionalità speciali: possono essere dichiarate come [risorse](../../../../docs/framework/wpf/advanced/xaml-resources.md)condiviso tra più oggetti, in sola lettura per migliorare le prestazioni, duplicata, e resi thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite da <xref:System.Windows.Freezable> degli oggetti, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>Confronto tra oggetti Geometry e Forme  
 Il <xref:System.Windows.Media.Geometry> e <xref:System.Windows.Shapes.Shape> classi simili che descrivono entrambe le forme 2D (confrontare <xref:System.Windows.Media.EllipseGeometry> e <xref:System.Windows.Shapes.Ellipse> ad esempio), ma esistono alcune differenze importanti.  
  
 Per uno, il <xref:System.Windows.Media.Geometry> classe eredita il <xref:System.Windows.Freezable> classe durante il <xref:System.Windows.Shapes.Shape> classe eredita da <xref:System.Windows.FrameworkElement>. Poiché si tratta di elementi <xref:System.Windows.Shapes.Shape> oggetti è possono eseguire il rendering di se stessi e fanno parte del sistema di layout, mentre <xref:System.Windows.Media.Geometry> non gli oggetti.  
  
 Sebbene <xref:System.Windows.Shapes.Shape> gli oggetti sono più facilmente utilizzabili più <xref:System.Windows.Media.Geometry> oggetti, <xref:System.Windows.Media.Geometry> gli oggetti sono più versatili. Mentre un <xref:System.Windows.Shapes.Shape> oggetto viene utilizzato per il rendering della grafica 2D, un <xref:System.Windows.Media.Geometry> oggetto può essere utilizzato per definire l'area geometrica per grafici 2D, definire un'area di ritaglio o definire un'area per l'hit test, ad esempio.  
  
### <a name="the-path-shape"></a>Classe Path di Shape  
 Un <xref:System.Windows.Shapes.Shape>, <xref:System.Windows.Shapes.Path> utilizzato dalla classe, in realtà un <xref:System.Windows.Media.Geometry> per descriverne il contenuto. Impostando il <xref:System.Windows.Shapes.Path.Data%2A> proprietà del <xref:System.Windows.Shapes.Path> con un <xref:System.Windows.Media.Geometry> e l'impostazione relativa <xref:System.Windows.Shapes.Shape.Fill%2A> e <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà, è possibile eseguire il rendering un <xref:System.Windows.Media.Geometry>.  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>Proprietà comuni che richiedono un oggetto Geometry  
 Come indicato nelle sezioni precedenti, gli oggetti Geometry possono essere usati con altri oggetti per vari scopi, ad esempio il disegno di forme, l'animazione e il ritaglio. Nella tabella seguente sono elencate diverse classi che dispongono di proprietà che accettano un <xref:System.Windows.Media.Geometry> oggetto.  
  
|Tipo|Proprietà|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>Tipi di oggetti Geometry semplici  
 La classe base per tutti gli oggetti Geometry è la classe astratta <xref:System.Windows.Media.Geometry>.  Le classi che derivano dalla <xref:System.Windows.Media.Geometry> classe può essere raggruppata approssimativamente in tre categorie: geometrie semplici, geometrie di percorso e geometrie composte.  
  
 Le classi di geometrie semplici includono <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, e <xref:System.Windows.Media.EllipseGeometry> e vengono utilizzati per creare forme geometriche di base, ad esempio linee, rettangoli e cerchi.  
  
-   Oggetto <xref:System.Windows.Media.LineGeometry> viene definito specificando il punto di inizio della riga e il punto finale.  
  
-   Oggetto <xref:System.Windows.Media.RectangleGeometry> viene definito con un <xref:System.Windows.Rect> struttura che specifica la posizione relativa e l'altezza e larghezza. È possibile creare un rettangolo arrotondato impostando il <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> e <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> proprietà.  
  
-   Un <xref:System.Windows.Media.EllipseGeometry> è definita da un punto centrale, un raggio x e un raggio y.  Gli esempi seguenti mostrano come creare geometrie semplici per il rendering e per il ritaglio.  
  
 Queste stesse forme, come forme più complesse, possono essere create usando un <xref:System.Windows.Media.PathGeometry> o combinando oggetti geometry, ma queste classi forniscono un modo più semplice per creare queste forme geometriche base.  
  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.LineGeometry>.  Come indicato in precedenza, un <xref:System.Windows.Media.Geometry> oggetto non è in grado di disegnarsi, pertanto l'esempio utilizza un <xref:System.Windows.Shapes.Path> forma per il rendering della linea.  Poiché una riga non presenta un'area, se si imposta la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà del <xref:System.Windows.Shapes.Path> non avrà effetto; invece, solo il <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> sono specificate proprietà. L'immagine seguente illustra l'output dell'esempio.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto LineGeometry disegnato da (10,20) a (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 L'esempio successivo mostra come creare ed eseguire il rendering di un <xref:System.Windows.Media.EllipseGeometry>.  I set di esempi di <xref:System.Windows.Media.EllipseGeometry.Center%2A> del <xref:System.Windows.Media.EllipseGeometry> è impostato per il punto di `50,50` e il raggio x e il raggio y sono entrambe impostate su `50`, che consente di creare un cerchio con diametro pari a 100.  Assegnando un valore alla proprietà di riempimento dell'elemento Path, in questo caso viene disegnato l'interno dell'ellisse <xref:System.Windows.Media.Brushes.Gold%2A>. L'immagine seguente illustra l'output dell'esempio.  
  
 ![EllipseGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
Un oggetto EllipseGeometry tracciato a (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un <xref:System.Windows.Media.RectangleGeometry>.  La posizione e le dimensioni del rettangolo sono definite da un <xref:System.Windows.Rect> struttura. La posizione è `50,50` e l'altezza e la larghezza sono entrambe `25`; viene creato un quadrato. L'immagine seguente illustra l'output dell'esempio.  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Un oggetto RectangleGeometry tracciato a 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Media.EllipseGeometry> come area di ritaglio per un'immagine.  Un <xref:System.Windows.Controls.Image> oggetto viene definito con un <xref:System.Windows.FrameworkElement.Width%2A> pari a 200 e un <xref:System.Windows.FrameworkElement.Height%2A> pari a 150.  Un <xref:System.Windows.Media.EllipseGeometry> con un <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> valore pari a 100, un <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> valore pari a 75 e un <xref:System.Windows.Media.EllipseGeometry.Center%2A> valore pari a 100,75 è impostato sul <xref:System.Windows.UIElement.Clip%2A> proprietà dell'immagine.  Verrà visualizzata solo la parte dell'immagine che è all'interno dell'area dell'ellisse. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Un'immagine con e senza ritaglio](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Oggetto EllipseGeometry usato per ritagliare un controllo Image  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>Geometrie di tracciato  
 Il <xref:System.Windows.Media.PathGeometry> classe ed equivalente leggera la <xref:System.Windows.Media.StreamGeometry> classe, forniscono i mezzi per descrivere figure più complesse costituite da archi, curve e linee.  
  
 Il fulcro di un <xref:System.Windows.Media.PathGeometry> è una raccolta di <xref:System.Windows.Media.PathFigure> oggetti, così definiti perché ogni figura descrive una forma discreta nel <xref:System.Windows.Media.PathGeometry>. Ogni <xref:System.Windows.Media.PathFigure> è a sua volta composto da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali descrive un segmento della figura.  
  
 Esistono diversi tipi di segmenti.  
  
|Tipo di segmento|Descrizione|Esempio|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco ellittico tra due punti.|[Creare un arco ellittico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva di Bézier cubica tra due punti.|[Creare una curva di Bézier cubica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Crea una linea tra due punti.|[Creare un oggetto LineSegment in un oggetto PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie di curve di Bézier cubiche.|Vedere il <xref:System.Windows.Media.PolyBezierSegment> pagina di tipo.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie di linee.|Vedere il <xref:System.Windows.Media.PolyLineSegment> pagina di tipo.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie di curve di Bézier quadratiche.|Vedere il <xref:System.Windows.Media.PolyQuadraticBezierSegment> pagina.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva di Bézier quadratica.|[Creare una curva di Bézier quadratica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).|  
  
 I segmenti all'interno di un <xref:System.Windows.Media.PathFigure> vengono combinate in una singola forma geometrica con il punto finale di ogni segmento che è il punto di inizio del segmento successivo. Il <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà di un <xref:System.Windows.Media.PathFigure> specifica il punto da cui viene disegnato il primo segmento. Ogni segmento successivo inizia in corrispondenza del punto finale del segmento precedente. Ad esempio, una linea verticale da `10,50` per `10,150` possono essere definite tramite l'impostazione di <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà `10,50` e la creazione di un <xref:System.Windows.Media.LineSegment> con un <xref:System.Windows.Media.LineSegment.Point%2A> impostazione della proprietà `10,150`.  
  
 Nell'esempio seguente viene creato un semplice <xref:System.Windows.Media.PathGeometry> costituita da un singolo <xref:System.Windows.Media.PathFigure> con un <xref:System.Windows.Media.LineSegment> e viene visualizzata mediante un <xref:System.Windows.Shapes.Path> elemento. Il <xref:System.Windows.Media.PathFigure> dell'oggetto <xref:System.Windows.Media.PathFigure.StartPoint%2A> è impostato su `10,20` e <xref:System.Windows.Media.LineSegment> viene definito con un punto finale di `100,130`. La figura seguente mostra il <xref:System.Windows.Media.PathGeometry> creato da questo esempio.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto PathGeometry che contiene un singolo oggetto LineSegment  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 È utile confrontare questo esempio con il precedente <xref:System.Windows.Media.LineGeometry> esempio.  La sintassi utilizzata per un <xref:System.Windows.Media.PathGeometry> è molto più dettagliato rispetto a quello utilizzato per una semplice <xref:System.Windows.Media.LineGeometry>, e potrebbe essere più vantaggioso utilizzare il <xref:System.Windows.Media.LineGeometry> classe in questo caso, ma la sintassi dettagliata del <xref:System.Windows.Media.PathGeometry> consente estremamente complesso e complesse aree geometriche.  
  
 Geometrie più complesse possono essere create utilizzando una combinazione di <xref:System.Windows.Media.PathSegment> oggetti.  
  
 Nell'esempio successivo viene utilizzato un <xref:System.Windows.Media.BezierSegment>, <xref:System.Windows.Media.LineSegment>e un <xref:System.Windows.Media.ArcSegment> per creare la forma. Nell'esempio viene creata una curva di Bezier cubica definendo quattro punti: un punto iniziale, ovvero il punto di fine del segmento precedente, un punto finale (<xref:System.Windows.Media.BezierSegment.Point3%2A>), e due punti di controllo (<xref:System.Windows.Media.BezierSegment.Point1%2A> e <xref:System.Windows.Media.BezierSegment.Point2%2A>).  I due punti di controllo di una curva di Beziér cubica si comportano come magneti, ovvero attraggono parti della linea che sarebbe altrimenti una linea retta, producendo una curva. Il primo punto di controllo, <xref:System.Windows.Media.BezierSegment.Point1%2A>, influisce su inizio parte della curva; il secondo punto di controllo, <xref:System.Windows.Media.BezierSegment.Point2%2A>, influisce sulla parte finale della curva.  
  
 L'esempio aggiunge quindi un <xref:System.Windows.Media.LineSegment>, che viene disegnato tra il punto finale dell'oggetto precedente <xref:System.Windows.Media.BezierSegment> che hanno preceduto al punto specificato dal relativo <xref:System.Windows.Media.LineSegment> proprietà.  
  
 Viene quindi aggiunto un <xref:System.Windows.Media.ArcSegment>, che viene disegnato dal punto di fine dell'oggetto precedente <xref:System.Windows.Media.LineSegment> al punto specificato dal relativo <xref:System.Windows.Media.ArcSegment.Point%2A> proprietà. Nell'esempio viene inoltre specificato raggi dell'arco x e y-(<xref:System.Windows.Media.ArcSegment.Size%2A>), un angolo di rotazione (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>), un flag che indica l'angolo dell'arco risultante deve essere (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>) e un valore che indica la direzione in cui viene disegnata l'arco (<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>). La figura seguente mostra la forma creata da questo esempio.  
  
 ![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path2.gif "graphicsmm_path2")  
PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Geometrie ancora più complesse possono essere create usando più <xref:System.Windows.Media.PathFigure> oggetti all'interno di un <xref:System.Windows.Media.PathGeometry>.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Media.PathGeometry> con due <xref:System.Windows.Media.PathFigure> oggetti, ognuno dei quali contiene più <xref:System.Windows.Media.PathSegment> oggetti.  Il <xref:System.Windows.Media.PathFigure> dall'esempio precedente e un <xref:System.Windows.Media.PathFigure> con un <xref:System.Windows.Media.PolyLineSegment> e <xref:System.Windows.Media.QuadraticBezierSegment> vengono utilizzati.  Oggetto <xref:System.Windows.Media.PolyLineSegment> viene definito con una matrice di punti e <xref:System.Windows.Media.QuadraticBezierSegment> viene definito con un punto di controllo e un punto finale. La figura seguente mostra la forma creata da questo esempio.  
  
 ![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path.gif "graphicsmm_path")  
Un oggetto PathGeometry con più figure  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Ad esempio il <xref:System.Windows.Media.PathGeometry> (classe), un <xref:System.Windows.Media.StreamGeometry> definisce una forma geometrica complessa che potrebbe contenere curve, archi e righe. A differenza di un <xref:System.Windows.Media.PathGeometry>, il contenuto di un <xref:System.Windows.Media.StreamGeometry> non supportano l'associazione dati, l'animazione o la modifica. Utilizzare un <xref:System.Windows.Media.StreamGeometry> quando è necessario descrivere una geometria complessa, ma non si desidera che l'overhead di supportare data binding, animazione o la modifica. Grazie alla sua efficienza, il <xref:System.Windows.Media.StreamGeometry> classe è una buona scelta per descrivere gli strumenti decorativi.  
  
 Per un esempio, vedere [Creare forme tramite un oggetto StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
### <a name="path-markup-syntax"></a>Sintassi di markup del percorso  
 Il <xref:System.Windows.Media.PathGeometry> e <xref:System.Windows.Media.StreamGeometry> tipi supportano un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintassi mediante una serie speciale di spostamento dell'attributo e comandi di disegno. Per altre informazioni, vedere [Sintassi di markup del tracciato](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>Oggetti Geometry composti  
 È possibile creare oggetti di geometria composta utilizzando un <xref:System.Windows.Media.GeometryGroup>, un <xref:System.Windows.Media.CombinedGeometry>, o chiamando il metodo statico <xref:System.Windows.Media.Geometry> metodo <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
-   Il <xref:System.Windows.Media.CombinedGeometry> oggetto e <xref:System.Windows.Media.Geometry.Combine%2A> metodo esegue un'operazione booleana per combinare l'area definita da due geometrie. <xref:System.Windows.Media.Geometry> gli oggetti che dispongono di alcuna area vengono ignorati. Solo due <xref:System.Windows.Media.Geometry> oggetti possono essere combinati (anche se queste due geometrie possono anche essere composte).  
  
-   Il <xref:System.Windows.Media.GeometryGroup> classe consente di creare una combinazione del <xref:System.Windows.Media.Geometry> gli oggetti in esso contenuti senza combinarne l'area. Un numero qualsiasi di <xref:System.Windows.Media.Geometry> oggetti possono essere aggiunti a un <xref:System.Windows.Media.GeometryGroup>. Per un esempio, vedere [Creare una forma composta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md).  
  
 Poiché viene eseguita un'operazione di combinazione, utilizzando <xref:System.Windows.Media.GeometryGroup> oggetti offre vantaggi nelle prestazioni rispetto all'uso <xref:System.Windows.Media.CombinedGeometry> oggetti o <xref:System.Windows.Media.Geometry.Combine%2A> metodo.  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>Geometrie combinate  
 Indicato nella sezione precedente di <xref:System.Windows.Media.CombinedGeometry> oggetto e <xref:System.Windows.Media.Geometry.Combine%2A> metodo combinare l'area definita dalle geometrie contengono. Il <xref:System.Windows.Media.GeometryCombineMode> enumerazione specifica come vengono combinate le geometrie. I valori possibili per il <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> proprietà sono: <xref:System.Windows.Media.GeometryCombineMode.Union>, <xref:System.Windows.Media.GeometryCombineMode.Intersect>, <xref:System.Windows.Media.GeometryCombineMode.Exclude>, e <xref:System.Windows.Media.GeometryCombineMode.Xor>.  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> è definito con una modalità di combinazione di unione.  Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Risultati della modalità di combinazione unione](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione <xref:System.Windows.Media.GeometryCombineMode.Xor>.  Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Risultati della modalità di combinazione Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Per altri esempi, vedere [Creare una forma composta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md) e [Creare una geometria combinata](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Funzionalità di Freezable  
 Perché eredita dal <xref:System.Windows.Freezable> (classe), il <xref:System.Windows.Media.Geometry> classe fornisce diverse funzionalità speciali: <xref:System.Windows.Media.Geometry> gli oggetti possono essere dichiarati come [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)condiviso tra più oggetti, in sola lettura per migliorare prestazioni, duplicati e resi thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite da <xref:System.Windows.Freezable> degli oggetti, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>Altre funzionalità dell'oggetto Geometry  
 La <xref:System.Windows.Media.Geometry> classe fornisce anche metodi di utilità, ad esempio le operazioni seguenti:  
  
-   <xref:System.Windows.Media.Geometry.GetArea%2A> -Ottiene l'area di <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.FillContains%2A> -Determina se la geometria contiene un altro <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.StrokeContains%2A> -Consente di determinare se il tratto di un <xref:System.Windows.Media.Geometry> contiene un punto specificato.  
  
 Vedere la <xref:System.Windows.Media.Geometry> classe per un elenco completo dei relativi metodi.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Geometry>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Sintassi di markup del percorso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
