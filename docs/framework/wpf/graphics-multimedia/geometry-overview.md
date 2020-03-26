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
ms.openlocfilehash: ff42e59edd9d98b0b52dc3bdd3ace0c35df60878
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112375"
---
# <a name="geometry-overview"></a>Cenni preliminari sulle classi Geometry
In questa panoramica viene [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> descritto come utilizzare le classi per descrivere le forme. In questo argomento vengono <xref:System.Windows.Media.Geometry> inoltre <xref:System.Windows.Shapes.Shape> confrontate le differenze tra oggetti ed elementi.  

<a name="wcpsdk_graphics_geometry_introduction"></a>
## <a name="what-is-a-geometry"></a>Definizione di Geometry  
 La <xref:System.Windows.Media.Geometry> classe e le classi che <xref:System.Windows.Media.EllipseGeometry>derivano da essa, ad esempio , <xref:System.Windows.Media.PathGeometry>e <xref:System.Windows.Media.CombinedGeometry>, consentono di descrivere la geometria di una forma 2D. Queste descrizioni geometriche hanno molti usi, come la definizione di una forma da disegnare sullo schermo o la definizione di aree di hit test e di ritaglio. È anche possibile usare un oggetto Geometry per definire un tracciato di animazione.  
  
 <xref:System.Windows.Media.Geometry>gli oggetti possono essere semplici, ad esempio rettangoli e cerchi o compositi, creati da due o più oggetti geometrici.  È possibile creare geometrie più <xref:System.Windows.Media.PathGeometry> complesse <xref:System.Windows.Media.StreamGeometry> utilizzando le classi e , che consentono di descrivere archi e curve.  
  
 Poiché <xref:System.Windows.Media.Geometry> un oggetto <xref:System.Windows.Freezable> <xref:System.Windows.Media.Geometry> è un tipo di , gli oggetti forniscono diverse funzionalità speciali: possono essere dichiarati come [risorse](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivisi tra più oggetti, resi di sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per ulteriori informazioni sulle diverse <xref:System.Windows.Freezable> funzionalità fornite dagli oggetti, vedere Cenni preliminari sugli [oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>
## <a name="geometries-vs-shapes"></a>Geometrie e forme  
 Le <xref:System.Windows.Media.Geometry> <xref:System.Windows.Shapes.Shape> classi e sembrano simili in quanto descrivono entrambe le forme 2D (confronto <xref:System.Windows.Media.EllipseGeometry> e <xref:System.Windows.Shapes.Ellipse> per esempio), ma ci sono differenze importanti.  
  
 Per uno, <xref:System.Windows.Media.Geometry> la classe <xref:System.Windows.Freezable> eredita dalla <xref:System.Windows.Shapes.Shape> classe mentre <xref:System.Windows.FrameworkElement>la classe eredita da . Poiché sono <xref:System.Windows.Shapes.Shape> elementi, gli oggetti possono eseguire il <xref:System.Windows.Media.Geometry> rendering di se stessi e partecipare al sistema di layout, mentre gli oggetti non possono.  
  
 Sebbene <xref:System.Windows.Shapes.Shape> gli oggetti <xref:System.Windows.Media.Geometry> siano <xref:System.Windows.Media.Geometry> più facilmente utilizzabili degli oggetti, gli oggetti sono più versatili. Mentre <xref:System.Windows.Shapes.Shape> un oggetto viene utilizzato per <xref:System.Windows.Media.Geometry> eseguire il rendering di elementi grafici 2D, un oggetto può essere utilizzato per definire l'area geometrica per la grafica 2D, definire un'area per il ritaglio o definire un'area per l'hit testing, ad esempio.  
  
### <a name="the-path-shape"></a>Classe Path di Shape  
 Uno <xref:System.Windows.Shapes.Shape>, <xref:System.Windows.Shapes.Path> la classe <xref:System.Windows.Media.Geometry> , utilizza in realtà un per descriverne il contenuto. Impostando la <xref:System.Windows.Shapes.Path.Data%2A> proprietà <xref:System.Windows.Shapes.Path> di <xref:System.Windows.Media.Geometry> con a <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> e impostandone le <xref:System.Windows.Media.Geometry>proprietà , è possibile eseguire il rendering di un oggetto .  
  
<a name="commonproperties"></a>
## <a name="common-properties-that-take-a-geometry"></a>Proprietà comuni che richiedono un oggetto Geometry  
 Come indicato nelle sezioni precedenti, gli oggetti Geometry possono essere usati con altri oggetti per vari scopi, ad esempio il disegno di forme, l'animazione e il ritaglio. Nella tabella seguente sono elencate diverse <xref:System.Windows.Media.Geometry> classi che dispongono di proprietà che accettano un oggetto.  
  
|Type|Proprietà|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>
## <a name="simple-geometry-types"></a>Tipi di oggetti Geometry semplici  
 La classe base per tutte le <xref:System.Windows.Media.Geometry>geometrie è la classe astratta .  Le classi che <xref:System.Windows.Media.Geometry> derivano dalla classe possono essere raggruppate approssimativamente in tre categorie: geometrie semplici, geometrie di percorso e geometrie composite.  
  
 Le classi geometriche <xref:System.Windows.Media.RectangleGeometry>semplici <xref:System.Windows.Media.EllipseGeometry> includono <xref:System.Windows.Media.LineGeometry>, e vengono utilizzate per creare forme geometriche di base, ad esempio linee, rettangoli e cerchi.  
  
- Un <xref:System.Windows.Media.LineGeometry> oggetto viene definito specificando il punto iniziale della linea e il punto finale.  
  
- A <xref:System.Windows.Media.RectangleGeometry> è definito <xref:System.Windows.Rect> con una struttura che specifica la sua posizione relativa e la sua altezza e larghezza. È possibile creare un rettangolo arrotondato impostando le <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> proprietà e <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> .  
  
- Un <xref:System.Windows.Media.EllipseGeometry> è definito da un punto centrale, un raggio x e un raggio y.  Gli esempi seguenti mostrano come creare geometrie semplici per il rendering e per il ritaglio.  
  
 Queste stesse forme, così come forme più complesse, possono essere create utilizzando un <xref:System.Windows.Media.PathGeometry> o combinando oggetti geometrici insieme, ma queste classi forniscono un mezzo più semplice per la produzione di queste forme geometriche di base.  
  
 Nell'esempio riportato di seguito <xref:System.Windows.Media.LineGeometry>viene illustrato come creare ed eseguire il rendering di un oggetto .  Come indicato in <xref:System.Windows.Media.Geometry> precedenza, un oggetto non è <xref:System.Windows.Shapes.Path> in grado di disegnare se stesso, pertanto l'esempio usa una forma per eseguire il rendering della linea.  Poiché una linea non <xref:System.Windows.Shapes.Shape.Fill%2A> ha alcuna area, l'impostazione della proprietà dell'oggetto <xref:System.Windows.Shapes.Path> non avrebbe alcun effetto; al contrario, vengono specificate solo le <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> . L'immagine seguente illustra l'output dell'esempio.  
  
 ![Oggetto LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto LineGeometry disegnato da (10,20) a (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 Nell'esempio seguente viene illustrato <xref:System.Windows.Media.EllipseGeometry>come creare ed eseguire il rendering di un oggetto .  Gli esempi <xref:System.Windows.Media.EllipseGeometry.Center%2A> impostano <xref:System.Windows.Media.EllipseGeometry> l'oggetto `50,50` impostato sul punto e il raggio x e `50`il raggio y sono entrambi impostati su , che crea un cerchio con un diametro di 100.  L'interno dell'ellisse viene disegnato assegnando un valore alla proprietà <xref:System.Windows.Media.Brushes.Gold%2A>Fill dell'elemento Path, in questo caso . L'immagine seguente illustra l'output dell'esempio.  
  
 ![Oggetto EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
Un oggetto EllipseGeometry tracciato a (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 Nell'esempio riportato di seguito <xref:System.Windows.Media.RectangleGeometry>viene illustrato come creare ed eseguire il rendering di un oggetto .  La posizione e le dimensioni del <xref:System.Windows.Rect> rettangolo sono definite da una struttura. La posizione è `50,50` e l'altezza e la larghezza sono entrambe `25`; viene creato un quadrato. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Oggetto RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Un oggetto RectangleGeometry tracciato a 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 L'esempio seguente mostra <xref:System.Windows.Media.EllipseGeometry> come utilizzare un'area di ritaglio per un'immagine.  Un <xref:System.Windows.Controls.Image> oggetto è <xref:System.Windows.FrameworkElement.Width%2A> definito con a <xref:System.Windows.FrameworkElement.Height%2A> di 200 e a di 150.  Un <xref:System.Windows.Media.EllipseGeometry> con <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> un valore di <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> 100, un <xref:System.Windows.Media.EllipseGeometry.Center%2A> valore pari a 75 e un <xref:System.Windows.UIElement.Clip%2A> valore di 100,75 viene impostato sulla proprietà dell'immagine.  Verrà visualizzata solo la parte dell'immagine che è all'interno dell'area dell'ellisse. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Immagine con e senza area di ritaglio](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Oggetto EllipseGeometry usato per ritagliare un controllo Image  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>
## <a name="path-geometries"></a>Geometrie di tracciato  
 La <xref:System.Windows.Media.PathGeometry> classe e il <xref:System.Windows.Media.StreamGeometry> relativo equivalente, la classe , forniscono i mezzi per descrivere più figure complesse composte da archi, curve e linee.  
  
 Il cuore di <xref:System.Windows.Media.PathGeometry> un è <xref:System.Windows.Media.PathFigure> una raccolta di oggetti, così chiamato perché <xref:System.Windows.Media.PathGeometry>ogni figura descrive una forma discreta nel . Ognuno <xref:System.Windows.Media.PathFigure> di essi è <xref:System.Windows.Media.PathSegment> costituito da uno o più oggetti, ognuno dei quali descrive un segmento della figura.  
  
 Esistono diversi tipi di segmenti.  
  
|Tipo di segmento|Descrizione|Esempio|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco ellittico tra due punti.|[Creare un arco ellittico](how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva di Bézier cubica tra due punti.|[Creare una curva di Bézier cubica.](how-to-create-a-cubic-bezier-curve.md)|  
|<xref:System.Windows.Media.LineSegment>|Crea una linea tra due punti.|[Creare un oggetto LineSegment in un oggetto PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie di curve di Bézier cubiche.|Vedere <xref:System.Windows.Media.PolyBezierSegment> la pagina del tipo.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie di linee.|Vedere <xref:System.Windows.Media.PolyLineSegment> la pagina del tipo.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie di curve di Bézier quadratiche.|Vedere <xref:System.Windows.Media.PolyQuadraticBezierSegment> la pagina.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva di Bézier quadratica.|[Create una curva di Bézier quadratica.](how-to-create-a-quadratic-bezier-curve.md)|  
  
 I segmenti all'interno di un <xref:System.Windows.Media.PathFigure> vengono combinati in un'unica forma geometrica con il punto finale di ogni segmento come punto iniziale del segmento successivo. La <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà <xref:System.Windows.Media.PathFigure> di un oggetto specifica il punto da cui viene disegnato il primo segmento. Ogni segmento successivo inizia in corrispondenza del punto finale del segmento precedente. Ad esempio, una `10,50` linea `10,150` verticale da <xref:System.Windows.Media.PathFigure.StartPoint%2A> a `10,50` può essere <xref:System.Windows.Media.LineSegment> definita <xref:System.Windows.Media.LineSegment.Point%2A> impostando `10,150`la proprietà su e creando un'impostazione di proprietà di .  
  
 L'esempio seguente <xref:System.Windows.Media.PathGeometry> crea un semplice <xref:System.Windows.Media.PathFigure> composto <xref:System.Windows.Media.LineSegment> da un <xref:System.Windows.Shapes.Path> singolo con a e lo visualizza utilizzando un elemento. L'oggetto <xref:System.Windows.Media.PathFigure> <xref:System.Windows.Media.PathFigure.StartPoint%2A> è impostato `10,20` su <xref:System.Windows.Media.LineSegment> e a è `100,130`definito con un punto finale di . Nella figura seguente <xref:System.Windows.Media.PathGeometry> viene illustrato il creato da questo esempio.  
  
 ![Oggetto LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto PathGeometry che contiene un singolo oggetto LineSegment  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Vale la pena confrontare questo <xref:System.Windows.Media.LineGeometry> esempio con l'esempio precedente.  La sintassi <xref:System.Windows.Media.PathGeometry> utilizzata per un è molto più <xref:System.Windows.Media.LineGeometry>dettagliata di quella utilizzata per <xref:System.Windows.Media.LineGeometry> un semplice , e può essere più <xref:System.Windows.Media.PathGeometry> sensato utilizzare la classe in questo caso, ma la sintassi dettagliata dell'oggetto consente aree geometriche estremamente complesse e complesse.  
  
 È possibile creare geometrie più complesse <xref:System.Windows.Media.PathSegment> utilizzando una combinazione di oggetti.  
  
 Nell'esempio seguente <xref:System.Windows.Media.BezierSegment>vengono <xref:System.Windows.Media.LineSegment>utilizzati <xref:System.Windows.Media.ArcSegment> , a e un oggetto per creare la forma. L'esempio innanzitutto crea una curva di Bézier cubica consiste nel definire quattro punti: un<xref:System.Windows.Media.BezierSegment.Point3%2A>punto iniziale,<xref:System.Windows.Media.BezierSegment.Point1%2A> <xref:System.Windows.Media.BezierSegment.Point2%2A>ovvero il punto finale del segmento precedente, un punto finale ( ) e due punti di controllo ( e ).  I due punti di controllo di una curva di Beziér cubica si comportano come magneti, ovvero attraggono parti della linea che sarebbe altrimenti una linea retta, producendo una curva. Il primo punto <xref:System.Windows.Media.BezierSegment.Point1%2A>di controllo, , influisce sulla parte iniziale della curva; il secondo punto <xref:System.Windows.Media.BezierSegment.Point2%2A>di controllo, , influisce sulla parte finale della curva.  
  
 Nell'esempio viene <xref:System.Windows.Media.LineSegment>quindi aggiunto un oggetto , che <xref:System.Windows.Media.BezierSegment> viene disegnato tra il punto <xref:System.Windows.Media.LineSegment> finale del precedente che lo ha preceduto fino al punto specificato dalla relativa proprietà.  
  
 Nell'esempio viene <xref:System.Windows.Media.ArcSegment>quindi aggiunto un oggetto , che <xref:System.Windows.Media.LineSegment> viene disegnato dal <xref:System.Windows.Media.ArcSegment.Point%2A> punto finale del precedente al punto specificato dalla relativa proprietà. Nell'esempio vengono inoltre specificati i raggi x e<xref:System.Windows.Media.ArcSegment.Size%2A>y dell'arco ( ), un angolo di rotazione (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A><xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>), un flag che indica l'intensità<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>dell'angolo dell'arco risultante ( ) e un valore che indica in quale direzione viene disegnato l'arco ( ). La figura seguente mostra la forma creata da questo esempio.  
  
 ![PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 È possibile creare geometrie ancora più <xref:System.Windows.Media.PathFigure> complesse <xref:System.Windows.Media.PathGeometry>utilizzando più oggetti all'interno di un oggetto .  
  
 Nell'esempio seguente <xref:System.Windows.Media.PathGeometry> viene <xref:System.Windows.Media.PathFigure> creato un con <xref:System.Windows.Media.PathSegment> due oggetti, ognuno dei quali contiene più oggetti.  Vengono <xref:System.Windows.Media.PathFigure> utilizzati il <xref:System.Windows.Media.PathFigure> dall'esempio precedente e a con a <xref:System.Windows.Media.PolyLineSegment> e a. <xref:System.Windows.Media.QuadraticBezierSegment>  A <xref:System.Windows.Media.PolyLineSegment> viene definito con una <xref:System.Windows.Media.QuadraticBezierSegment> matrice di punti e l'oggetto viene definito con un punto di controllo e un punto finale. La figura seguente mostra la forma creata da questo esempio.  
  
 ![PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
Un oggetto PathGeometry con più figure  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Come <xref:System.Windows.Media.PathGeometry> la classe, un <xref:System.Windows.Media.StreamGeometry> oggetto definisce una forma geometrica complessa che può contenere curve, archi e linee. A <xref:System.Windows.Media.PathGeometry>differenza di un <xref:System.Windows.Media.StreamGeometry> oggetto , il contenuto di un oggetto non supporta l'associazione dati, l'animazione o la modifica. Utilizzare <xref:System.Windows.Media.StreamGeometry> un quando è necessario descrivere una geometria complessa, ma non si desidera l'overhead di supporto dell'associazione dati, animazione o modifica. A causa della <xref:System.Windows.Media.StreamGeometry> sua efficienza, la classe è una buona scelta per descrivere gli strumenti decorativi.  
  
 Per un esempio, vedere [Creare forme tramite un oggetto StreamGeometry](how-to-create-a-shape-using-a-streamgeometry.md).  
  
### <a name="path-markup-syntax"></a>Sintassi di markup del percorso  
 I <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> tipi e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] supportano una sintassi di attributo utilizzando una serie speciale di comandi di spostamento e disegno. Per altre informazioni, vedere [Sintassi di markup del tracciato](path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>
## <a name="composite-geometries"></a>Oggetti Geometry composti  
 Gli oggetti geometrici compositi <xref:System.Windows.Media.CombinedGeometry>possono essere creati <xref:System.Windows.Media.Geometry> utilizzando <xref:System.Windows.Media.Geometry.Combine%2A>un <xref:System.Windows.Media.GeometryGroup>oggetto , un oggetto o chiamando il metodo statico .  
  
- L'oggetto <xref:System.Windows.Media.CombinedGeometry> <xref:System.Windows.Media.Geometry.Combine%2A> e il metodo esegue un'operazione booleana per combinare l'area definita da due geometrie. <xref:System.Windows.Media.Geometry>gli oggetti che non hanno area vengono scartati. Solo <xref:System.Windows.Media.Geometry> due oggetti possono essere combinati (anche se queste due geometrie possono anche essere geometrie composite).  
  
- La <xref:System.Windows.Media.GeometryGroup> classe crea un'unione <xref:System.Windows.Media.Geometry> degli oggetti in essa contenuti senza combinarne l'area. È possibile <xref:System.Windows.Media.Geometry> aggiungere un numero <xref:System.Windows.Media.GeometryGroup>qualsiasi di oggetti a un file . Per un esempio, vedere [Creare una forma composta](how-to-create-a-composite-shape.md).  
  
 Poiché non eseguono un'operazione di combinazione, l'utilizzo <xref:System.Windows.Media.GeometryGroup> di oggetti offre vantaggi in termini di prestazioni rispetto all'utilizzo <xref:System.Windows.Media.CombinedGeometry> di oggetti o del <xref:System.Windows.Media.Geometry.Combine%2A> metodo.  
  
<a name="combindgeometriessection"></a>
## <a name="combined-geometries"></a>Geometrie combinate  
 La sezione precedente <xref:System.Windows.Media.CombinedGeometry> ha menzionato l'oggetto e il <xref:System.Windows.Media.Geometry.Combine%2A> metodo combinano l'area definita dalle geometrie in essi contenute. L'enumerazione <xref:System.Windows.Media.GeometryCombineMode> specifica come vengono combinate le geometrie. I valori possibili <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> per <xref:System.Windows.Media.GeometryCombineMode.Union>la <xref:System.Windows.Media.GeometryCombineMode.Intersect> <xref:System.Windows.Media.GeometryCombineMode.Exclude>proprietà <xref:System.Windows.Media.GeometryCombineMode.Xor>sono: , , , e .  
  
 Nell'esempio seguente, <xref:System.Windows.Media.CombinedGeometry> a viene definito con una modalità di combinazione di Union.In the following example, a is defined with a combine mode of Union.  Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> quelli sono definiti come cerchi dello stesso raggio, ma con centri sfalsati di 50.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Risultati della modalità di combinazione Union](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 Nell'esempio seguente, <xref:System.Windows.Media.CombinedGeometry> a viene definito <xref:System.Windows.Media.GeometryCombineMode.Xor>con una modalità di combinazione di .  Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> quelli sono definiti come cerchi dello stesso raggio, ma con centri sfalsati di 50.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Risultati della modalità di combinazione Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Per altri esempi, vedere [Creare una forma composta](how-to-create-a-composite-shape.md) e [Creare una geometria combinata](how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dalla <xref:System.Windows.Freezable> classe <xref:System.Windows.Media.Geometry> , la classe <xref:System.Windows.Media.Geometry> fornisce diverse funzionalità speciali: gli oggetti possono essere dichiarati come [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivisi tra più oggetti, resi di sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per ulteriori informazioni sulle diverse <xref:System.Windows.Freezable> funzionalità fornite dagli oggetti, vedere Cenni preliminari sugli [oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>
## <a name="other-geometry-features"></a>Altre funzionalità dell'oggetto Geometry  
 La <xref:System.Windows.Media.Geometry> classe fornisce inoltre metodi di utilità utili, ad esempio:  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A>- Ottiene l'area del file <xref:System.Windows.Media.Geometry>.  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A>- Determina se l'oggetto Geometry contiene un altro <xref:System.Windows.Media.Geometry>file .  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A>- Determina se il <xref:System.Windows.Media.Geometry> tratto di un oggetto contiene un punto specificato.  
  
 Vedere <xref:System.Windows.Media.Geometry> la classe per un elenco completo dei relativi metodi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Grafica 2D e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Sintassi di markup del percorso](path-markup-syntax.md)
- [Procedure relative](geometries-how-to-topics.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
