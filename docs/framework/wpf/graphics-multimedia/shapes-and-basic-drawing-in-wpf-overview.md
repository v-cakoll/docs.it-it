---
title: Cenni preliminari sulla progettazione di forme e di base
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
ms.openlocfilehash: dfdbf67d35cbb13e80d0c5184f165b0cc660e2ef
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731618"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF
Questo argomento fornisce una panoramica di come creare oggetti con <xref:System.Windows.Shapes.Shape>. Un <xref:System.Windows.Shapes.Shape> è un tipo di <xref:System.Windows.UIElement> che consente di disegnare una forma sullo schermo. Poiché si tratta di elementi dell'interfaccia utente, <xref:System.Windows.Shapes.Shape> gli oggetti possono essere utilizzati all'interno di <xref:System.Windows.Controls.Panel> elementi e la maggior parte dei controlli.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre diversi livelli di accesso alla grafica e ai servizi di rendering. Al livello superiore, gli oggetti <xref:System.Windows.Shapes.Shape> sono facili da usare e offrono numerose funzionalità utili, ad esempio il layout e la partecipazione al sistema di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] eventi.  

<a name="shapes"></a>   
## <a name="shape-objects"></a>Oggetti Shape  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce una serie di oggetti <xref:System.Windows.Shapes.Shape> pronti per l'uso.  Tutti gli oggetti Shape ereditano dalla classe <xref:System.Windows.Shapes.Shape>. Gli oggetti Shape disponibili includono <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>e <xref:System.Windows.Shapes.Rectangle>. gli oggetti <xref:System.Windows.Shapes.Shape> condividono le seguenti proprietà comuni.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: descrive il modo in cui viene disegnato il contorno della forma.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: descrive lo spessore del contorno della forma.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: descrive il modo in cui viene disegnata l'area interna della forma.  
  
- Proprietà dei dati per specificare coordinate e vertici, misurati in pixel indipendenti dal dispositivo.  
  
 Poiché derivano da <xref:System.Windows.UIElement>, gli oggetti Shape possono essere utilizzati nei pannelli e nella maggior parte dei controlli. Il pannello <xref:System.Windows.Controls.Canvas> rappresenta una scelta particolarmente utile per la creazione di disegni complessi, perché supporta il posizionamento assoluto dei relativi oggetti figlio.  
  
 La classe <xref:System.Windows.Shapes.Line> consente di creare una linea tra due punti. L'esempio seguente illustra molti modi per specificare le coordinate della riga e le proprietà del tratto.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 Nell'immagine seguente viene illustrata la <xref:System.Windows.Shapes.Line>sottoposta a rendering.  
  
 ![Illustrazione linea](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Sebbene la classe <xref:System.Windows.Shapes.Line> fornisca una proprietà <xref:System.Windows.Shapes.Shape.Fill%2A>, l'impostazione non produce alcun effetto perché una <xref:System.Windows.Shapes.Line> non ha alcuna area.  
  
 Un'altra forma comune è la <xref:System.Windows.Shapes.Ellipse>.  Creare una <xref:System.Windows.Shapes.Ellipse> definendo le proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> della forma. Per creare un cerchio, specificare un <xref:System.Windows.Shapes.Ellipse> i cui valori di <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> siano uguali.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 Nell'immagine seguente viene illustrato un esempio di un <xref:System.Windows.Shapes.Ellipse>sottoposto a rendering.  
  
 ![Illustrazione ellisse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a>Utilizzo di tracciati e geometrie  
 La classe <xref:System.Windows.Shapes.Path> consente di creare curve e forme complesse. Queste curve e forme vengono descritte utilizzando <xref:System.Windows.Media.Geometry> oggetti. Per utilizzare una <xref:System.Windows.Shapes.Path>, è necessario creare un <xref:System.Windows.Media.Geometry> e utilizzarlo per impostare la proprietà <xref:System.Windows.Shapes.Path.Data%2A> dell'oggetto <xref:System.Windows.Shapes.Path>.  
  
 È possibile scegliere tra diversi oggetti <xref:System.Windows.Media.Geometry>. Le classi <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>e <xref:System.Windows.Media.EllipseGeometry> descrivono forme relativamente semplici. Per creare forme più complesse o creare curve, usare un <xref:System.Windows.Media.PathGeometry>.  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry e PathSegments  
 <xref:System.Windows.Media.PathGeometry> oggetti sono costituiti da uno o più oggetti <xref:System.Windows.Media.PathFigure>; ogni <xref:System.Windows.Media.PathFigure> rappresenta una "figura" o una forma diversa. Ogni <xref:System.Windows.Media.PathFigure> è costituita da uno o più oggetti <xref:System.Windows.Media.PathSegment>, ciascuno dei quali rappresenta una parte connessa della figura o della forma. I tipi di segmento includono i seguenti: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>e <xref:System.Windows.Media.ArcSegment>.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Shapes.Path> per creare una curva di Bézier quadratica.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 L'immagine seguente illustra la forma sottoposta a rendering.  
  
 ![Illustrazione del percorso](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Per ulteriori informazioni su <xref:System.Windows.Media.PathGeometry> e sulle altre classi <xref:System.Windows.Media.Geometry>, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a>Sintassi abbreviata XAML  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è anche possibile usare una speciale sintassi abbreviata per descrivere una <xref:System.Windows.Shapes.Path>. Nell'esempio seguente viene usata la sintassi abbreviata per disegnare una forma complessa.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 Nell'immagine seguente viene illustrata una <xref:System.Windows.Shapes.Path>sottoposta a rendering.  
  
 ![Illustrazione del percorso](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 La stringa dell'attributo <xref:System.Windows.Shapes.Path.Data%2A> inizia con il comando "MoveTo", indicato da M, che stabilisce un punto iniziale per il percorso nel sistema di coordinate del <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.Shapes.Path> i parametri dei dati fanno distinzione tra maiuscole e minuscole. Il valore letterale M indica una posizione assoluta per il nuovo punto corrente. Una lettera m minuscola indica le coordinate relative. Il primo segmento è una curva di Bézier cubica che inizia in corrispondenza del punto (100,200) e termina in corrispondenza del punto (400,175) e viene disegnata usando i due punti di controllo (100,25) e (400,350). Questo segmento è indicato dal comando C nella stringa dell'attributo <xref:System.Windows.Shapes.Path.Data%2A>. Anche in questo caso la lettera C maiuscola indica un percorso assoluto, mentre la lettera c minuscola indica un percorso relativo.  
  
 Il secondo segmento inizia con un comando orizzontale assoluto "lineto" H, che specifica una riga disegnata dal punto finale del sottopercorso precedente (400,175) a un nuovo punto finale (280,175). Poiché si tratta di un comando "lineto" orizzontale, il valore specificato è una coordinata *x*.  
  
 Per la sintassi del percorso completo, vedere il riferimento <xref:System.Windows.Shapes.Path.Data%2A> e [creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a>Disegno di oggetti Shape  
 gli oggetti <xref:System.Windows.Media.Brush> vengono utilizzati per disegnare <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.Fill%2A>di una forma. Nell'esempio seguente vengono specificati il tratto e il riempimento di un <xref:System.Windows.Shapes.Ellipse>. Si noti che un input valido per le proprietà del pennello può essere rappresentato da una parola chiave o da un valore di colore esadecimale. Per ulteriori informazioni sulle parole chiave dei colori disponibili, vedere Proprietà della classe <xref:System.Windows.Media.Colors> nello spazio dei nomi <xref:System.Windows.Media>.  
  
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
  
 Nell'immagine seguente viene illustrata la <xref:System.Windows.Shapes.Ellipse>sottoposta a rendering.  
  
 ![Ellisse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 In alternativa, è possibile utilizzare la sintassi dell'elemento proprietà per creare in modo esplicito un oggetto <xref:System.Windows.Media.SolidColorBrush> per disegnare la forma con un colore a tinta unita.  
  
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
  
 ![Illustrazione di SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 È anche possibile disegnare il tratto o il riempimento di una forma con sfumature, immagini, motivi e così via. Per ulteriori informazioni, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a>Oggetti Shape allungabili  
 Le classi <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>e <xref:System.Windows.Shapes.Rectangle> dispongono tutti di una proprietà <xref:System.Windows.Shapes.Shape.Stretch%2A>. Questa proprietà determina il modo in cui il contenuto di un oggetto <xref:System.Windows.Shapes.Shape> (la forma da disegnare) viene allungato per riempire lo spazio del layout dell'oggetto <xref:System.Windows.Shapes.Shape>. Lo spazio di layout di un oggetto <xref:System.Windows.Shapes.Shape> è la quantità di spazio che il <xref:System.Windows.Shapes.Shape> alloca dal sistema di layout, a causa di un'impostazione esplicita di <xref:System.Windows.FrameworkElement.Width%2A> e di <xref:System.Windows.FrameworkElement.Height%2A> oppure a causa delle impostazioni <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>. Per altre informazioni sul layout in Windows Presentation Foundation, vedere Cenni preliminari sul [layout](../advanced/layout.md) .  
  
 La proprietà Stretch accetta uno dei valori seguenti:  
  
- <xref:System.Windows.Media.Stretch.None>: il contenuto dell'oggetto <xref:System.Windows.Shapes.Shape> non viene allungato.  
  
- <xref:System.Windows.Media.Stretch.Fill>: il contenuto dell'oggetto <xref:System.Windows.Shapes.Shape> viene allungato per riempire lo spazio del layout.  Le proporzioni non vengono mantenute.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: il contenuto dell'oggetto <xref:System.Windows.Shapes.Shape> viene allungato il più possibile per riempire lo spazio del layout mantenendo le proporzioni originali.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: il contenuto dell'oggetto <xref:System.Windows.Shapes.Shape> viene allungato per riempire completamente lo spazio del layout mantenendo le proporzioni originali.  
  
 Si noti che, quando il contenuto di un oggetto <xref:System.Windows.Shapes.Shape> viene allungato, il contorno dell'oggetto <xref:System.Windows.Shapes.Shape> viene disegnato dopo l'estensione.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Shapes.Polygon> per creare un triangolo molto piccolo da (0,0) a (0, 1) a (1,1). Il <xref:System.Windows.FrameworkElement.Width%2A> e la <xref:System.Windows.FrameworkElement.Height%2A> dell'oggetto <xref:System.Windows.Shapes.Polygon> sono impostati su 100 e la relativa proprietà Stretch è impostata su Fill. Di conseguenza, il contenuto dell'oggetto <xref:System.Windows.Shapes.Polygon> (il triangolo) viene allungato per riempire lo spazio più grande.  
  
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
 La classe <xref:System.Windows.Media.Transform> fornisce i mezzi per trasformare le forme in un piano bidimensionale.  I diversi tipi di trasformazione includono Rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), asimmetria (<xref:System.Windows.Media.SkewTransform>) e Translation (<xref:System.Windows.Media.TranslateTransform>).  
  
 Una trasformazione comune da applicare a una forma è una rotazione.  Per ruotare una forma, creare una <xref:System.Windows.Media.RotateTransform> e specificarne la <xref:System.Windows.Media.RotateTransform.Angle%2A>. Un <xref:System.Windows.Media.RotateTransform.Angle%2A> di 45 ruota l'elemento 45 gradi in senso orario; un angolo di 90 ruota l'elemento 90 gradi in senso orario; E così via. Impostare le proprietà <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> se si desidera controllare il punto in cui viene ruotato l'elemento. Questi valori di proprietà sono espressi nello spazio delle coordinate dell'elemento trasformato. <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> hanno valori predefiniti pari a zero. Infine, applicare la <xref:System.Windows.Media.RotateTransform> all'elemento. Se non si desidera che la trasformazione influisca sul layout, impostare la proprietà <xref:System.Windows.UIElement.RenderTransform%2A> della forma.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.RotateTransform> per ruotare una forma 45 gradi sull'angolo superiore sinistro della forma (0,0).  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 Nell'esempio successivo un'altra forma viene ruotata di 45 gradi, ma in questo caso rispetto al punto (25,50).  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 L'immagine seguente illustra i risultati dell'applicazione delle due trasformazioni.  
  
 ![Rotazioni di 45 gradi con punti centrali diversi](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 Negli esempi precedenti è stata applicata una sola trasformazione a ogni oggetto Shape. Per applicare più trasformazioni a una forma (o a qualsiasi altro elemento dell'interfaccia utente), usare un <xref:System.Windows.Media.TransformGroup>.  
  
## <a name="see-also"></a>Vedere anche

- [Grafica bidimensionale e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
