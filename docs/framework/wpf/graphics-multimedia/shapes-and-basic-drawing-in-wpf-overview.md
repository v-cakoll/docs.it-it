---
title: Panoramica delle forme e dei disegni di base
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
ms.openlocfilehash: 44104bec478f1fbb10acc0e591af43ea95fecdc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141328"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF
In questo argomento viene fornita <xref:System.Windows.Shapes.Shape> una panoramica su come disegnare con gli oggetti. A <xref:System.Windows.Shapes.Shape> è un <xref:System.Windows.UIElement> tipo di che consente di disegnare una forma sullo schermo. Poiché sono elementi <xref:System.Windows.Shapes.Shape> dell'interfaccia <xref:System.Windows.Controls.Panel> utente, gli oggetti possono essere utilizzati all'interno di elementi e la maggior parte dei controlli.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre diversi livelli di accesso alla grafica e ai servizi di rendering. Al livello superiore, <xref:System.Windows.Shapes.Shape> gli oggetti sono facili da usare e forniscono [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] molte funzioni utili, come il layout e la partecipazione al sistema di eventi.  

<a name="shapes"></a>
## <a name="shape-objects"></a>Oggetti Shape  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce una serie di oggetti <xref:System.Windows.Shapes.Shape> pronti all'uso.  Tutti gli oggetti <xref:System.Windows.Shapes.Shape> forma ereditano dalla classe. Gli oggetti <xref:System.Windows.Shapes.Ellipse>forma <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>disponibili <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>includono <xref:System.Windows.Shapes.Rectangle>, , , , e . <xref:System.Windows.Shapes.Shape>gli oggetti condividono le seguenti proprietà comuni.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: descrive come viene disegnato il contorno della forma.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: descrive lo spessore del contorno della forma.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: descrive come viene dipinto l'interno della forma.  
  
- Proprietà dei dati per specificare coordinate e vertici, misurati in pixel indipendenti dal dispositivo.  
  
 Poiché derivano da <xref:System.Windows.UIElement>, gli oggetti forma possono essere utilizzati all'interno di pannelli e la maggior parte dei controlli. Il <xref:System.Windows.Controls.Canvas> pannello è una scelta particolarmente buona per la creazione di disegni complessi perché supporta il posizionamento assoluto dei relativi oggetti figlio.  
  
 La <xref:System.Windows.Shapes.Line> classe consente di disegnare una linea tra due punti. L'esempio seguente illustra molti modi per specificare le coordinate della riga e le proprietà del tratto.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 L'immagine seguente <xref:System.Windows.Shapes.Line>mostra l'oggetto renderizzato .  
  
 ![Illustrazione di Line](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Anche <xref:System.Windows.Shapes.Line> se la <xref:System.Windows.Shapes.Shape.Fill%2A> classe fornisce una proprietà, <xref:System.Windows.Shapes.Line> l'impostazione non ha alcun effetto perché un oggetto non ha alcuna area.  
  
 Un'altra forma <xref:System.Windows.Shapes.Ellipse>comune è la .  Creare <xref:System.Windows.Shapes.Ellipse> un oggetto definendo <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> la forma e le proprietà. Per disegnare un cerchio, <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> specificare un <xref:System.Windows.Shapes.Ellipse> i cui valori sono uguali.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 L'immagine seguente mostra un <xref:System.Windows.Shapes.Ellipse>esempio di un oggetto renderizzato .  
  
 ![Illustrazione di Ellipse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a>Utilizzo di tracciati e geometrie  
 La <xref:System.Windows.Shapes.Path> classe consente di disegnare curve e forme complesse. Queste curve e forme <xref:System.Windows.Media.Geometry> vengono descritte utilizzando gli oggetti. Per utilizzare <xref:System.Windows.Shapes.Path>un oggetto <xref:System.Windows.Media.Geometry> , creare un <xref:System.Windows.Shapes.Path> oggetto <xref:System.Windows.Shapes.Path.Data%2A> e utilizzarlo per impostare la proprietà dell'oggetto.  
  
 Ci sono una <xref:System.Windows.Media.Geometry> varietà di oggetti tra cui scegliere. Le <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry>classi <xref:System.Windows.Media.EllipseGeometry> , e descrivono forme relativamente semplici. Per creare forme più complesse o <xref:System.Windows.Media.PathGeometry>curve, utilizzare un file .  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry e PathSegments  
 <xref:System.Windows.Media.PathGeometry>gli oggetti sono costituiti <xref:System.Windows.Media.PathFigure> da uno o più oggetti; ognuna rappresenta una "figura" o una <xref:System.Windows.Media.PathFigure> forma diversa. Ciascuno <xref:System.Windows.Media.PathFigure> di essi è costituito da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte connessa della figura o della forma. I tipi di <xref:System.Windows.Media.LineSegment>segmento includono quanto segue: , <xref:System.Windows.Media.BezierSegment>, e <xref:System.Windows.Media.ArcSegment>.  
  
 Nell'esempio seguente, <xref:System.Windows.Shapes.Path> a viene utilizzato per disegnare una curva di Bézier quadratica.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 L'immagine seguente illustra la forma sottoposta a rendering.  
  
 ![Illustrazione di Path](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Per ulteriori <xref:System.Windows.Media.PathGeometry> informazioni su <xref:System.Windows.Media.Geometry> e sulle altre classi, vedere [Cenni preliminari](geometry-overview.md)sulla geometria .  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a>Sintassi abbreviata XAML  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è inoltre possibile utilizzare una <xref:System.Windows.Shapes.Path>sintassi abbreviata speciale per descrivere un oggetto . Nell'esempio seguente viene usata la sintassi abbreviata per disegnare una forma complessa.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 L'immagine seguente <xref:System.Windows.Shapes.Path>mostra un rendering .  
  
 ![Illustrazione di Path](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 La <xref:System.Windows.Shapes.Path.Data%2A> stringa di attributo inizia con il comando "moveto", indicato da M, che stabilisce un punto iniziale per il percorso nel sistema di coordinate dell'oggetto <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.Shapes.Path>parametri di dati fanno distinzione tra maiuscole e minuscole. La M maiuscola indica una posizione assoluta per il nuovo punto corrente. Una lettera m minuscola indica le coordinate relative. Il primo segmento è una curva di Bézier cubica che inizia in corrispondenza del punto (100,200) e termina in corrispondenza del punto (400,175) e viene disegnata usando i due punti di controllo (100,25) e (400,350). Questo segmento è indicato dal <xref:System.Windows.Shapes.Path.Data%2A> comando C nella stringa di attributo. Anche in questo caso la lettera C maiuscola indica un percorso assoluto, mentre la lettera c minuscola indica un percorso relativo.  
  
 Il secondo segmento inizia con un comando orizzontale assoluto "lineto" H, che specifica una riga disegnata dal punto finale del sottopercorso precedente (400,175) a un nuovo punto finale (280,175). Poiché è un comando "lineto" orizzontale, il valore specificato è una coordinata *x.*  
  
 Per la sintassi del <xref:System.Windows.Shapes.Path.Data%2A> percorso completo, vedere il riferimento e [Creare una forma utilizzando un PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a>Disegno di oggetti Shape  
 <xref:System.Windows.Media.Brush>gli oggetti vengono utilizzati <xref:System.Windows.Shapes.Shape.Stroke%2A> per <xref:System.Windows.Shapes.Shape.Fill%2A>disegnare una forma e . Nell'esempio seguente vengono specificati il <xref:System.Windows.Shapes.Ellipse> tratto e il riempimento di un oggetto . Si noti che un input valido per le proprietà del pennello può essere rappresentato da una parola chiave o da un valore di colore esadecimale. Per altre informazioni sulle parole chiave <xref:System.Windows.Media.Colors> di colore <xref:System.Windows.Media> disponibili, vedere proprietà della classe nello spazio dei nomi .  
  
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
  
 L'immagine seguente <xref:System.Windows.Shapes.Ellipse>mostra l'oggetto renderizzato .  
  
 ![Ellisse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 In alternativa, è possibile utilizzare la <xref:System.Windows.Media.SolidColorBrush> sintassi degli elementi proprietà per creare in modo esplicito un oggetto per disegnare la forma con un colore a tinta unita.  
  
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
  
 È anche possibile disegnare il tratto o il riempimento di una forma con sfumature, immagini, motivi e così via. Per ulteriori informazioni, vedere [Cenni preliminari sul disegno con colori a tinta unita e gradienti](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a>Oggetti Shape allungabili  
 Le <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>classi <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>, <xref:System.Windows.Shapes.Rectangle> , , <xref:System.Windows.Shapes.Shape.Stretch%2A> e dispongono tutte di una proprietà . Questa proprietà determina <xref:System.Windows.Shapes.Shape> il modo in cui il contenuto di un <xref:System.Windows.Shapes.Shape> oggetto (la forma da disegnare) viene allungato per riempire lo spazio di layout dell'oggetto. Lo <xref:System.Windows.Shapes.Shape> spazio di layout di un <xref:System.Windows.Shapes.Shape> oggetto è la quantità di spazio <xref:System.Windows.FrameworkElement.Width%2A> che <xref:System.Windows.FrameworkElement.Height%2A> viene allocata dal sistema di layout, a causa di un esplicito e dell'impostazione o a causa delle sue <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> impostazioni e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> . Per ulteriori informazioni sul layout in Windows Presentation Foundation, vedere [Panoramica del layout.](../advanced/layout.md)  
  
 La proprietà Stretch accetta uno dei valori seguenti:  
  
- <xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto non viene allungato.  
  
- <xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto viene allungato per riempire lo spazio di layout.  Le proporzioni non vengono mantenute.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto viene allungato il più possibile per riempire lo spazio di layout mantenendo le proporzioni originali.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto viene allungato per riempire completamente lo spazio di layout mantenendo le proporzioni originali.  
  
 Si noti <xref:System.Windows.Shapes.Shape> che, quando il contenuto <xref:System.Windows.Shapes.Shape> di un oggetto viene allungato, il contorno dell'oggetto viene disegnato dopo l'allungamento.  
  
 Nell'esempio seguente, <xref:System.Windows.Shapes.Polygon> a viene usato per disegnare un triangolo molto piccolo da (0,0) a (0,1) a (1,1). L'oggetto <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> sono impostati su 100 e la relativa proprietà stretch è impostata su Fill. Di conseguenza, <xref:System.Windows.Shapes.Polygon> il contenuto dell'oggetto (il triangolo) viene allungato per riempire lo spazio più grande.  
  
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
 La <xref:System.Windows.Media.Transform> classe fornisce i mezzi per trasformare le forme in un piano bidimensionale.  I diversi tipi di<xref:System.Windows.Media.RotateTransform>trasformazione<xref:System.Windows.Media.ScaleTransform>includono la<xref:System.Windows.Media.SkewTransform>rotazione (<xref:System.Windows.Media.TranslateTransform>), la scala ( ), l'inclinazione ( ) e la traslazione ( ).  
  
 Una trasformazione comune da applicare a una forma è una rotazione.  Per ruotare una <xref:System.Windows.Media.RotateTransform> forma, <xref:System.Windows.Media.RotateTransform.Angle%2A>creare a e specificarne il file . Un <xref:System.Windows.Media.RotateTransform.Angle%2A> di 45 ruota l'elemento di 45 gradi in senso orario; un angolo di 90 ruota l'elemento di 90 gradi in senso orario; E così via. Impostare <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> le proprietà e se si desidera controllare il punto attorno al quale viene ruotato l'elemento. Questi valori di proprietà sono espressi nello spazio delle coordinate dell'elemento trasformato. <xref:System.Windows.Media.RotateTransform.CenterX%2A>e <xref:System.Windows.Media.RotateTransform.CenterY%2A> hanno valori predefiniti pari a zero. Infine, applicare <xref:System.Windows.Media.RotateTransform> l'oggetto all'elemento. Se non si desidera che la trasformazione influisca <xref:System.Windows.UIElement.RenderTransform%2A> sul layout, impostare la proprietà della forma.  
  
 Nell'esempio seguente, <xref:System.Windows.Media.RotateTransform> a viene utilizzato per ruotare una forma di 45 gradi intorno all'angolo superiore sinistro della forma (0,0).  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 Nell'esempio successivo un'altra forma viene ruotata di 45 gradi, ma in questo caso rispetto al punto (25,50).  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 L'immagine seguente illustra i risultati dell'applicazione delle due trasformazioni.  
  
 ![Rotazioni di 45 gradi con punti centrali diversi](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 Negli esempi precedenti è stata applicata una sola trasformazione a ogni oggetto Shape. Per applicare più trasformazioni a una forma (o <xref:System.Windows.Media.TransformGroup>a qualsiasi altro elemento dell'interfaccia utente), utilizzare un' estensione .  
  
## <a name="see-also"></a>Vedere anche

- [Grafica 2D e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
