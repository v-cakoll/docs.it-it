---
title: Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 47df352c3b001f088f34ea057b34698efc4f4b53
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47233296"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF
Questo argomento offre una panoramica di come disegnare con <xref:System.Windows.Shapes.Shape> oggetti. Oggetto <xref:System.Windows.Shapes.Shape> è un tipo di <xref:System.Windows.UIElement> che consente di disegnare una forma sullo schermo. Poiché si tratta di elementi dell'interfaccia utente <xref:System.Windows.Shapes.Shape> oggetti possono essere utilizzati all'interno di <xref:System.Windows.Controls.Panel> elementi e la maggior parte dei controlli.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre diversi livelli di accesso alla grafica e ai servizi di rendering. Al livello superiore, <xref:System.Windows.Shapes.Shape> gli oggetti sono facili da usare e forniscono molte utili funzionalità, quali layout e la partecipazione di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema degli eventi.  
  
  
<a name="shapes"></a>   
## <a name="shape-objects"></a>Oggetti Shape  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce una serie di pronto utilizzo <xref:System.Windows.Shapes.Shape> oggetti.  Tutti gli oggetti shape ereditano dal <xref:System.Windows.Shapes.Shape> classe. Gli oggetti shape disponibili includono <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, e <xref:System.Windows.Shapes.Rectangle>. <xref:System.Windows.Shapes.Shape> gli oggetti condividono le proprietà comuni seguenti.  
  
-   <xref:System.Windows.Shapes.Shape.Stroke%2A>: Descrive come viene disegnata la struttura della forma.  
  
-   <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Descrive lo spessore del contorno della forma.  
  
-   <xref:System.Windows.Shapes.Shape.Fill%2A>: Descrive come viene disegnato l'interno della forma.  
  
-   Proprietà dei dati per specificare coordinate e vertici, misurati in pixel indipendenti dal dispositivo.  
  
 Dal momento che derivano da <xref:System.Windows.UIElement>, gli oggetti shape possono essere usati nei pannelli e nella maggior parte dei controlli. Il <xref:System.Windows.Controls.Canvas> pannello è particolarmente indicato per la creazione di disegni complessi poiché supporta il posizionamento assoluto dei relativi oggetti figlio.  
  
 Il <xref:System.Windows.Shapes.Line> classe consente di disegnare una linea tra due punti. L'esempio seguente illustra molti modi per specificare le coordinate della riga e le proprietà del tratto.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 L'immagine seguente illustra il rendering <xref:System.Windows.Shapes.Line>.  
  
 ![Line illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Anche se il <xref:System.Windows.Shapes.Line> forniscono un <xref:System.Windows.Shapes.Shape.Fill%2A> impostazione delle proprietà, si ha alcun effetto perché un <xref:System.Windows.Shapes.Line> non ha un'area.  
  
 Un'altra forma comune è la <xref:System.Windows.Shapes.Ellipse>.  Creare un <xref:System.Windows.Shapes.Ellipse> mediante la definizione della forma <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà. Per disegnare un cerchio, specificare un <xref:System.Windows.Shapes.Ellipse> la cui <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> valori sono uguali.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 L'immagine seguente mostra un esempio di un rendering <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Ellipse illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a>Utilizzo di tracciati e geometrie  
 Il <xref:System.Windows.Shapes.Path> classe consente di disegnare curve e forme complesse. Queste curve e forme vengono descritte usando <xref:System.Windows.Media.Geometry> oggetti. Usare un <xref:System.Windows.Shapes.Path>, si crea un' <xref:System.Windows.Media.Geometry> e usarlo per impostare il <xref:System.Windows.Shapes.Path> dell'oggetto <xref:System.Windows.Shapes.Path.Data%2A> proprietà.  
  
 Esistono svariati <xref:System.Windows.Media.Geometry> gli oggetti cui scegliere. Il <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, e <xref:System.Windows.Media.EllipseGeometry> le classi descrivono forme relativamente semplici. Per creare forme più complesse o curve, usare un <xref:System.Windows.Media.PathGeometry>.  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry e PathSegments  
 <xref:System.Windows.Media.PathGeometry> gli oggetti sono costituiti da uno o più <xref:System.Windows.Media.PathFigure> oggetti, ognuna delle quali <xref:System.Windows.Media.PathFigure> rappresenta un "importo" diverso o una forma. Ciascuna <xref:System.Windows.Media.PathFigure> è a sua volta composto da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte collegata della figura o forma. Tipi di segmento comprendono quanto segue: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, e <xref:System.Windows.Media.ArcSegment>.  
  
 Nell'esempio seguente, un <xref:System.Windows.Shapes.Path> utilizzato per disegnare una curva di Bézier quadratica.  
  
 [!code-xaml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 L'immagine seguente illustra la forma sottoposta a rendering.  
  
 ![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Per altre informazioni sulle <xref:System.Windows.Media.PathGeometry> e l'altra <xref:System.Windows.Media.Geometry> le classi, vedere la [panoramica delle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a>Sintassi abbreviata XAML  
 Nelle [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è anche possibile usare una sintassi abbreviata speciale per descrivere un <xref:System.Windows.Shapes.Path>. Nell'esempio seguente viene usata la sintassi abbreviata per disegnare una forma complessa.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 L'immagine seguente mostra un rendering <xref:System.Windows.Shapes.Path>.  
  
 ![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")  
  
 Il <xref:System.Windows.Shapes.Path.Data%2A> stringa di attributo inizia con il comando "moveto", indicato da M, che stabilisce un punto di partenza per il percorso nel sistema di coordinate del <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.Shapes.Path> i parametri di dati sono tra maiuscole e minuscole. La lettera M maiuscola indica un percorso assoluto per il nuovo punto corrente. Una lettera m minuscola indica le coordinate relative. Il primo segmento è una curva di Bézier cubica che inizia in corrispondenza del punto (100,200) e termina in corrispondenza del punto (400,175) e viene disegnata usando i due punti di controllo (100,25) e (400,350). Questo segmento è indicato dal comando C nella <xref:System.Windows.Shapes.Path.Data%2A> stringa dell'attributo. Anche in questo caso la lettera C maiuscola indica un percorso assoluto, mentre la lettera c minuscola indica un percorso relativo.  
  
 Il secondo segmento inizia con un comando orizzontale assoluto "lineto" H, che specifica una riga disegnata dal punto finale del sottopercorso precedente (400,175) a un nuovo punto finale (280,175). Poiché si tratta di un comando orizzontale "lineto", il valore specificato è un *x*-coordinare.  
  
 Per la sintassi del percorso completo, vedere la <xref:System.Windows.Shapes.Path.Data%2A> riferimento e [creare una forma utilizzando un oggetto PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a>Disegno di oggetti Shape  
 <xref:System.Windows.Media.Brush> gli oggetti vengono utilizzati per disegnare una forma <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.Fill%2A>. Nell'esempio seguente, il tratto e riempimento di un <xref:System.Windows.Shapes.Ellipse> specificati. Si noti che un input valido per le proprietà del pennello può essere rappresentato da una parola chiave o da un valore di colore esadecimale. Per altre informazioni sulle parole chiave di colore disponibili, vedere le proprietà del <xref:System.Windows.Media.Colors> classe di <xref:System.Windows.Media> dello spazio dei nomi.  
  
```xaml
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 L'immagine seguente illustra il rendering <xref:System.Windows.Shapes.Ellipse>.  
  
 ![An ellipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 In alternativa, è possibile usare la sintassi degli elementi per creare in modo esplicito un <xref:System.Windows.Media.SolidColorBrush> oggetto per disegnare una forma con un colore a tinta unita.  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 La figura seguente mostra la forma sottoposta a rendering.  
  
 ![SolidColorBrush illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 È anche possibile disegnare il tratto o il riempimento di una forma con sfumature, immagini, motivi e così via. Per altre informazioni, vedere la [disegno con colori a tinta unita e sfumature Panoramica](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a>Oggetti Shape allungabili  
 Il <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, e <xref:System.Windows.Shapes.Rectangle> classi tutti hanno un <xref:System.Windows.Shapes.Shape.Stretch%2A> proprietà. Questa proprietà determina il modo in cui un <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto (la forma da disegnare) viene allungato per riempire il <xref:System.Windows.Shapes.Shape> spazio del layout dell'oggetto. Oggetto <xref:System.Windows.Shapes.Shape> spazio del layout dell'oggetto è la quantità di spazio il <xref:System.Windows.Shapes.Shape> allocato dal sistema di layout, a causa di una esplicita <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> impostazione o a causa di relativo <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> impostazioni. Per altre informazioni sul layout in Windows Presentation Foundation, vedere [Layout](../../../../docs/framework/wpf/advanced/layout.md) Panoramica.  
  
 La proprietà Stretch accetta uno dei valori seguenti:  
  
-   <xref:System.Windows.Media.Stretch.None>: il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto non viene allungato.  
  
-   <xref:System.Windows.Media.Stretch.Fill>: il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato per riempire lo spazio del layout.  Le proporzioni non vengono mantenute.  
  
-   <xref:System.Windows.Media.Stretch.Uniform>: il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato il più possibile per riempire lo spazio del layout mantenendo le proporzioni originali.  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill>: il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato per riempire completamente lo spazio del layout mantenendo le proporzioni originali.  
  
 Si noti che, quando un <xref:System.Windows.Shapes.Shape> contenuto di un oggetto viene allungato, la <xref:System.Windows.Shapes.Shape> struttura dell'oggetto viene disegnata dopo l'allungamento.  
  
 Nell'esempio seguente, un <xref:System.Windows.Shapes.Polygon> utilizzato per disegnare un triangolo molto piccolo da (0,0) a (0,1) a (1,1). Il <xref:System.Windows.Shapes.Polygon> dell'oggetto <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> sono impostate su 100 e la proprietà stretch viene impostata su Fill. Di conseguenza, il <xref:System.Windows.Shapes.Polygon> contenuto dell'oggetto (triangolo) viene allungato per riempire lo spazio più ampio.  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>   
## <a name="transforming-shapes"></a>Trasformazione degli oggetti Shape  
 Il <xref:System.Windows.Media.Transform> classe fornisce i mezzi per trasformare le forme in un piano bidimensionale.  I diversi tipi di trasformazione includono rotazione (<xref:System.Windows.Media.RotateTransform>), scala (<xref:System.Windows.Media.ScaleTransform>), inclinazione (<xref:System.Windows.Media.SkewTransform>) e la conversione (<xref:System.Windows.Media.TranslateTransform>).  
  
 Una trasformazione comune da applicare a una forma è una rotazione.  Per ruotare una forma, creare un <xref:System.Windows.Media.RotateTransform> e specificare il <xref:System.Windows.Media.RotateTransform.Angle%2A>. Un <xref:System.Windows.Media.RotateTransform.Angle%2A> pari a 45 consente di ruotare l'elemento di 45 gradi in senso antiorario; un angolo di 90 l'elemento viene ruotato di 90 gradi in senso orario; e così via. Impostare il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà se si desidera controllare il punto in cui viene ruotato l'elemento. Questi valori di proprietà sono espressi nello spazio delle coordinate dell'elemento trasformato. <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> hanno valori predefiniti pari a zero. Infine, applicare il <xref:System.Windows.Media.RotateTransform> all'elemento. Se non si desidera la trasformazione influisca sul layout, impostare la forma <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.RotateTransform> viene utilizzato per ruotare una forma di 45 gradi rispetto alto a sinistra della forma (0,0).  
  
 [!code-xaml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 Nell'esempio successivo un'altra forma viene ruotata di 45 gradi, ma in questo caso rispetto al punto (25,50).  
  
 [!code-xaml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 L'immagine seguente illustra i risultati dell'applicazione delle due trasformazioni.  
  
 ![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 Negli esempi precedenti è stata applicata una sola trasformazione a ogni oggetto Shape. Per applicare più trasformazioni a una forma (o qualsiasi altro elemento dell'interfaccia utente), usare un <xref:System.Windows.Media.TransformGroup>.  
  
## <a name="see-also"></a>Vedere anche  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Cenni sul disegno con colori a tinta unita e sfumature](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Cenni preliminari sulle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Procedura dettagliata: Prima applicazione desktop WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
