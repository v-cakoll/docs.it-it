---
title: Cenni preliminari sulla progettazione di forme e di base
description: Migliorare l'interfaccia utente con forme pronte per l'uso e diversi livelli di servizi di rendering in Windows Presentation Foundation (WPF).
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
ms.openlocfilehash: 41d8f2b87232740c8945bd6a6099aa86dbe77bc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853689"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF
Questo argomento fornisce una panoramica di come creare <xref:System.Windows.Shapes.Shape> oggetti. Un <xref:System.Windows.Shapes.Shape> è un tipo di <xref:System.Windows.UIElement> che consente di disegnare una forma sullo schermo. Poiché si tratta di elementi dell'interfaccia utente, <xref:System.Windows.Shapes.Shape> gli oggetti possono essere utilizzati all'interno <xref:System.Windows.Controls.Panel> di elementi e la maggior parte dei controlli  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre diversi livelli di accesso alla grafica e ai servizi di rendering. Al livello superiore, <xref:System.Windows.Shapes.Shape> gli oggetti sono facili da usare e offrono numerose funzionalità utili, ad esempio il layout e la partecipazione al [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema di eventi.  

<a name="shapes"></a>
## <a name="shape-objects"></a>Oggetti Shape  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce una serie di oggetti pronti per l'utilizzo <xref:System.Windows.Shapes.Shape> .  Tutti gli oggetti Shape ereditano dalla <xref:System.Windows.Shapes.Shape> classe. Gli oggetti Shape disponibili includono <xref:System.Windows.Shapes.Ellipse> ,, <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path> , <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> e <xref:System.Windows.Shapes.Rectangle> . <xref:System.Windows.Shapes.Shape>gli oggetti condividono le seguenti proprietà comuni.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: Descrive il modo in cui viene disegnato il contorno della forma.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Descrive lo spessore del contorno della forma.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: Descrive il modo in cui viene disegnata l'area interna della forma.  
  
- Proprietà dei dati per specificare coordinate e vertici, misurati in pixel indipendenti dal dispositivo.  
  
 Poiché derivano da <xref:System.Windows.UIElement> , gli oggetti Shape possono essere utilizzati all'interno di pannelli e la maggior parte dei controlli. Il <xref:System.Windows.Controls.Canvas> pannello è una scelta particolarmente utile per la creazione di disegni complessi, perché supporta il posizionamento assoluto dei relativi oggetti figlio.  
  
 La <xref:System.Windows.Shapes.Line> classe consente di creare una linea tra due punti. L'esempio seguente illustra molti modi per specificare le coordinate della riga e le proprietà del tratto.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 Nell'immagine seguente viene illustrato il rendering <xref:System.Windows.Shapes.Line> .  
  
 ![Illustrazione di Line](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Sebbene la <xref:System.Windows.Shapes.Line> classe fornisca una <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà, l'impostazione non ha alcun effetto perché un oggetto <xref:System.Windows.Shapes.Line> non dispone di un'area.  
  
 Un'altra forma comune è <xref:System.Windows.Shapes.Ellipse> .  Creare un oggetto <xref:System.Windows.Shapes.Ellipse> definendo le <xref:System.Windows.FrameworkElement.Width%2A> proprietà e della forma <xref:System.Windows.FrameworkElement.Height%2A> . Per creare un cerchio, specificare <xref:System.Windows.Shapes.Ellipse> i cui <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> valori e sono uguali.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 La figura seguente mostra un esempio di un oggetto di cui è stato eseguito il rendering <xref:System.Windows.Shapes.Ellipse> .  
  
 ![Illustrazione di Ellipse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a>Utilizzo di tracciati e geometrie  
 La <xref:System.Windows.Shapes.Path> classe consente di creare curve e forme complesse. Queste curve e forme vengono descritte utilizzando <xref:System.Windows.Media.Geometry> gli oggetti. Per utilizzare un <xref:System.Windows.Shapes.Path> oggetto, è necessario creare un <xref:System.Windows.Media.Geometry> oggetto e utilizzarlo per impostare la <xref:System.Windows.Shapes.Path> proprietà dell'oggetto <xref:System.Windows.Shapes.Path.Data%2A> .  
  
 È possibile <xref:System.Windows.Media.Geometry> scegliere tra diversi oggetti. Le <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry> classi, e <xref:System.Windows.Media.EllipseGeometry> descrivono forme relativamente semplici. Per creare forme più complesse o creare curve, usare un oggetto <xref:System.Windows.Media.PathGeometry> .  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry e PathSegments  
 <xref:System.Windows.Media.PathGeometry>gli oggetti sono costituiti da uno o più <xref:System.Windows.Media.PathFigure> oggetti, ognuno dei quali <xref:System.Windows.Media.PathFigure> rappresenta una "figura" o una forma diversa. Ognuno <xref:System.Windows.Media.PathFigure> è costituito da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte connessa della figura o della forma. I tipi di segmenti includono i seguenti: <xref:System.Windows.Media.LineSegment> , <xref:System.Windows.Media.BezierSegment> e <xref:System.Windows.Media.ArcSegment> .  
  
 Nell'esempio seguente <xref:System.Windows.Shapes.Path> viene usato un oggetto per creare una curva di Bézier quadratica.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 L'immagine seguente illustra la forma sottoposta a rendering.  
  
 ![Illustrazione di Path](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Per ulteriori informazioni su <xref:System.Windows.Media.PathGeometry> e sulle altre <xref:System.Windows.Media.Geometry> classi, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a>Sintassi abbreviata XAML  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] è anche possibile usare una speciale sintassi abbreviata per descrivere un <xref:System.Windows.Shapes.Path> . Nell'esempio seguente viene usata la sintassi abbreviata per disegnare una forma complessa.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 Nell'immagine seguente viene illustrato un oggetto sottoposto a rendering <xref:System.Windows.Shapes.Path> .  
  
 ![Illustrazione di Path](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 La <xref:System.Windows.Shapes.Path.Data%2A> stringa dell'attributo inizia con il comando "MoveTo", indicato da M, che stabilisce un punto iniziale per il percorso nel sistema di coordinate di <xref:System.Windows.Controls.Canvas> . <xref:System.Windows.Shapes.Path>i parametri dati fanno distinzione tra maiuscole e minuscole. Il valore letterale M indica una posizione assoluta per il nuovo punto corrente. Una lettera m minuscola indica le coordinate relative. Il primo segmento è una curva di Bézier cubica che inizia in corrispondenza del punto (100,200) e termina in corrispondenza del punto (400,175) e viene disegnata usando i due punti di controllo (100,25) e (400,350). Questo segmento è indicato dal comando C nella stringa dell' <xref:System.Windows.Shapes.Path.Data%2A> attributo. Anche in questo caso la lettera C maiuscola indica un percorso assoluto, mentre la lettera c minuscola indica un percorso relativo.  
  
 Il secondo segmento inizia con un comando orizzontale assoluto "lineto" H, che specifica una riga disegnata dal punto finale del sottopercorso precedente (400,175) a un nuovo punto finale (280,175). Poiché si tratta di un comando "lineto" orizzontale, il valore specificato è una coordinata *x*.  
  
 Per la sintassi del percorso completo, vedere il <xref:System.Windows.Shapes.Path.Data%2A> riferimento e [creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a>Disegno di oggetti Shape  
 <xref:System.Windows.Media.Brush>gli oggetti vengono utilizzati per disegnare le forme <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.Fill%2A> . Nell'esempio seguente vengono specificati il tratto e il riempimento di un oggetto <xref:System.Windows.Shapes.Ellipse> . Si noti che un input valido per le proprietà del pennello può essere rappresentato da una parola chiave o da un valore di colore esadecimale. Per ulteriori informazioni sulle parole chiave dei colori disponibili, vedere Proprietà della <xref:System.Windows.Media.Colors> classe nello <xref:System.Windows.Media> spazio dei nomi.  
  
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
  
 Nell'immagine seguente viene illustrato il rendering <xref:System.Windows.Shapes.Ellipse> .  
  
 ![Ellisse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 In alternativa, è possibile utilizzare la sintassi dell'elemento proprietà per creare in modo esplicito un <xref:System.Windows.Media.SolidColorBrush> oggetto per disegnare la forma con un colore a tinta unita.  
  
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
 <xref:System.Windows.Shapes.Line>Tutte le <xref:System.Windows.Shapes.Path> classi,, <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> e <xref:System.Windows.Shapes.Rectangle> dispongono di una <xref:System.Windows.Shapes.Shape.Stretch%2A> Proprietà. Questa proprietà determina il modo in cui il contenuto di un <xref:System.Windows.Shapes.Shape> oggetto (la forma da disegnare) viene allungato per riempire lo <xref:System.Windows.Shapes.Shape> spazio del layout dell'oggetto. Lo <xref:System.Windows.Shapes.Shape> spazio del layout di un oggetto corrisponde alla quantità di spazio <xref:System.Windows.Shapes.Shape> allocata dal sistema di layout, a causa di un' <xref:System.Windows.FrameworkElement.Width%2A> impostazione esplicita e o a <xref:System.Windows.FrameworkElement.Height%2A> causa delle <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Impostazioni e. Per altre informazioni sul layout in Windows Presentation Foundation, vedere Cenni preliminari sul [layout](../advanced/layout.md) .  
  
 La proprietà Stretch accetta uno dei valori seguenti:  
  
- <xref:System.Windows.Media.Stretch.None>: Il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto non viene allungato.  
  
- <xref:System.Windows.Media.Stretch.Fill>: Il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato per riempire lo spazio del layout.  Le proporzioni non vengono mantenute.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: Il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato il più possibile per riempire lo spazio del layout mantenendo le proporzioni originali.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: Il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato per riempire completamente lo spazio del layout mantenendo le proporzioni originali.  
  
 Si noti che, quando il <xref:System.Windows.Shapes.Shape> contenuto di un oggetto viene allungato, il <xref:System.Windows.Shapes.Shape> contorno dell'oggetto viene disegnato dopo l'estensione.  
  
 Nell'esempio seguente <xref:System.Windows.Shapes.Polygon> viene usato un oggetto per creare un triangolo molto piccolo da (0, 0) a (0, 1) a (1,1). <xref:System.Windows.Shapes.Polygon>Gli oggetti <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> sono impostati su 100 e la relativa proprietà Stretch è impostata su Fill. Di conseguenza, il <xref:System.Windows.Shapes.Polygon> contenuto dell'oggetto (il triangolo) viene allungato per riempire lo spazio più grande.  
  
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
 La <xref:System.Windows.Media.Transform> classe fornisce i mezzi per trasformare le forme in un piano bidimensionale.  I diversi tipi di trasformazione includono rotazione ( <xref:System.Windows.Media.RotateTransform> ), scala ( <xref:System.Windows.Media.ScaleTransform> ), inclinazione ( <xref:System.Windows.Media.SkewTransform> ) e conversione ( <xref:System.Windows.Media.TranslateTransform> ).  
  
 Una trasformazione comune da applicare a una forma è una rotazione.  Per ruotare una forma, creare un oggetto <xref:System.Windows.Media.RotateTransform> e specificarne il <xref:System.Windows.Media.RotateTransform.Angle%2A> . Un <xref:System.Windows.Media.RotateTransform.Angle%2A> di 45 ruota l'elemento 45 gradi in senso orario; un angolo di 90 ruota l'elemento 90 gradi in senso orario e così via. Impostare le <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e se si desidera controllare il punto in cui viene ruotato l'elemento. Questi valori di proprietà sono espressi nello spazio delle coordinate dell'elemento trasformato. <xref:System.Windows.Media.RotateTransform.CenterX%2A>e <xref:System.Windows.Media.RotateTransform.CenterY%2A> hanno valori predefiniti pari a zero. Infine, applicare all' <xref:System.Windows.Media.RotateTransform> elemento. Se non si desidera che la trasformazione influisca sul layout, impostare la <xref:System.Windows.UIElement.RenderTransform%2A> proprietà della forma.  
  
 Nell'esempio seguente <xref:System.Windows.Media.RotateTransform> viene usato un oggetto per ruotare una forma 45 gradi sull'angolo superiore sinistro della forma (0,0).  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 Nell'esempio successivo un'altra forma viene ruotata di 45 gradi, ma in questo caso rispetto al punto (25,50).  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 L'immagine seguente illustra i risultati dell'applicazione delle due trasformazioni.  
  
 ![Rotazioni di 45 gradi con punti centrali diversi](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 Negli esempi precedenti è stata applicata una sola trasformazione a ogni oggetto Shape. Per applicare più trasformazioni a una forma (o a qualsiasi altro elemento dell'interfaccia utente), usare un oggetto <xref:System.Windows.Media.TransformGroup> .  
  
## <a name="see-also"></a>Vedere anche

- [Grafica 2D e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
