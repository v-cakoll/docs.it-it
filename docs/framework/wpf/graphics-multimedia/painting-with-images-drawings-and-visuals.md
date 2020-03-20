---
title: Disegnare con oggetti Image, Drawing e Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
ms.openlocfilehash: e0e5e386b32425c87502d18a24e758193c14a5b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186913"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Disegnare con oggetti Image, Drawing e Visual
In questo argomento viene <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>descritto <xref:System.Windows.Media.VisualBrush> come utilizzare oggetti , e <xref:System.Windows.Media.Drawing>per disegnare <xref:System.Windows.Media.Visual>un'area con un'immagine, un oggetto o un oggetto .  

<a name="prereqs"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere questo argomento, è necessario conoscere i diversi tipi di pennelli forniti da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e le relative funzionalità di base. Per un'introduzione, vedere [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md).  
  
<a name="image"></a>
## <a name="paint-an-area-with-an-image"></a>Disegnare un'area con un'immagine  
 Un <xref:System.Windows.Media.ImageBrush> dipinge un'area con un oggetto <xref:System.Windows.Media.ImageSource>. Il tipo più <xref:System.Windows.Media.ImageSource> comune di <xref:System.Windows.Media.ImageBrush> da <xref:System.Windows.Media.Imaging.BitmapImage>utilizzare con un oggetto è un oggetto , che descrive un'immagine bitmap. È possibile <xref:System.Windows.Media.DrawingImage> utilizzare un <xref:System.Windows.Media.Drawing> per disegnare utilizzando un oggetto, ma è più semplice usare un <xref:System.Windows.Media.DrawingBrush> invece. Per ulteriori <xref:System.Windows.Media.ImageSource> informazioni sugli oggetti, vedere [Cenni preliminari sulla creazione di immagini](imaging-overview.md).  
  
 Per disegnare <xref:System.Windows.Media.ImageBrush>con un <xref:System.Windows.Media.Imaging.BitmapImage> oggetto , creare e utilizzare per caricare il contenuto della bitmap. Quindi, utilizzare <xref:System.Windows.Media.Imaging.BitmapImage> il <xref:System.Windows.Media.ImageBrush.ImageSource%2A> per impostare la proprietà del <xref:System.Windows.Media.ImageBrush>file . Infine, applicare <xref:System.Windows.Media.ImageBrush> l'oggetto all'oggetto che si desidera disegnare.  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è anche <xref:System.Windows.Media.ImageBrush.ImageSource%2A> possibile impostare semplicemente la proprietà di <xref:System.Windows.Media.ImageBrush> con il percorso dell'immagine da caricare.  
  
 Come <xref:System.Windows.Media.Brush> tutti gli <xref:System.Windows.Media.ImageBrush> oggetti, un oggetto può essere utilizzato per disegnare oggetti quali forme, pannelli, controlli e testo. Nella figura seguente vengono illustrati alcuni <xref:System.Windows.Media.ImageBrush>effetti che è possibile ottenere con un oggetto .  
  
 ![Esempi di output di ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Oggetti disegnati con un oggetto ImageBrush  
  
 Per impostazione <xref:System.Windows.Media.ImageBrush> predefinita, un'immagine allunga la propria immagine per riempire completamente l'area disegnata, eventualmente distorcendo l'immagine se l'area disegnata ha proporzioni diverse rispetto all'immagine. È possibile modificare questo <xref:System.Windows.Media.TileBrush.Stretch%2A> comportamento modificando la <xref:System.Windows.Media.Stretch.Fill> proprietà <xref:System.Windows.Media.Stretch.None> <xref:System.Windows.Media.Stretch.Uniform>dal <xref:System.Windows.Media.Stretch.UniformToFill>valore predefinito di a , o . Poiché <xref:System.Windows.Media.ImageBrush> è <xref:System.Windows.Media.TileBrush>un tipo di , è possibile specificare esattamente come un pennello immagine riempie l'area di output e anche creare motivi. Per ulteriori informazioni <xref:System.Windows.Media.TileBrush> sulle funzionalità avanzate, vedere Cenni preliminari su [TileBrush](tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Esempio: disegnare un oggetto con un'immagine bitmap  
 Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.ImageBrush> oggetto per disegnare l'oggetto <xref:System.Windows.Controls.Panel.Background%2A> di un <xref:System.Windows.Controls.Canvas>oggetto .  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>
## <a name="paint-an-area-with-a-drawing"></a>Inserire un disegno in un'area  
 A <xref:System.Windows.Media.DrawingBrush> consente di disegnare un'area con forme, testo, immagini e video. Le forme all'interno di un pennello da disegno possono essere <xref:System.Windows.Media.DrawingBrush>disegnate a loro volta con un colore a tinta unita, una sfumatura, un'immagine o anche un altro oggetto . Nella figura seguente vengono <xref:System.Windows.Media.DrawingBrush>illustrati alcuni utilizzi di un oggetto .  
  
 ![Esempi di output di DrawingBrush](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Oggetti disegnati con un oggetto DrawingBrush  
  
 Un <xref:System.Windows.Media.DrawingBrush> oggetto dipinge <xref:System.Windows.Media.Drawing> un'area con un oggetto. Un <xref:System.Windows.Media.Drawing> oggetto descrive il contenuto visibile, ad esempio una forma, una bitmap, un video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
- <xref:System.Windows.Media.GeometryDrawing>– Disegna una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>– Disegna un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>– Disegna il testo.  
  
- <xref:System.Windows.Media.VideoDrawing>– Riproduce un file audio o video.  
  
- <xref:System.Windows.Media.DrawingGroup>– Disegna altri disegni. È possibile usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 Per ulteriori <xref:System.Windows.Media.Drawing> informazioni sugli oggetti, vedere Cenni preliminari sugli oggetti della [Carta.](drawing-objects-overview.md)  
  
 Come <xref:System.Windows.Media.ImageBrush>un <xref:System.Windows.Media.DrawingBrush> , <xref:System.Windows.Media.DrawingBrush.Drawing%2A> un allunga la sua per riempire la sua area di output. È possibile eseguire l'override di questo comportamento modificando la proprietà dall'impostazione <xref:System.Windows.Media.TileBrush.Stretch%2A> predefinita di <xref:System.Windows.Media.Stretch.Fill>. Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>
## <a name="example-paint-an-object-with-a-drawing"></a>Esempio: disegnare un oggetto con un oggetto Drawing  
 L'esempio seguente illustra come disegnare un oggetto con un disegno di tre ellissi. A <xref:System.Windows.Media.GeometryDrawing> viene utilizzato per descrivere le ellissi.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>
## <a name="paint-an-area-with-a-visual"></a>Disegnare un'area con un oggetto Visual  
 Il più versatile e potente di tutti <xref:System.Windows.Media.VisualBrush> i pennelli, <xref:System.Windows.Media.Visual>il dipinge un'area con un . A <xref:System.Windows.Media.Visual> è un tipo grafico di basso livello che funge da predecessore di molti componenti grafici utili. Ad esempio, <xref:System.Windows.Window> <xref:System.Windows.FrameworkElement>le <xref:System.Windows.Controls.Control> classi , e <xref:System.Windows.Media.Visual> sono tutti tipi di oggetti. Utilizzando <xref:System.Windows.Media.VisualBrush>un oggetto , è [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] possibile disegnare aree con quasi tutti gli oggetti grafici.  
  
> [!NOTE]
> Sebbene <xref:System.Windows.Media.VisualBrush> sia <xref:System.Windows.Freezable> un tipo di oggetto, non può essere <xref:System.Windows.Media.VisualBrush.Visual%2A> bloccato (reso di sola `null`lettura) quando la relativa proprietà è impostata su un valore diverso da .  
  
 Esistono due modi per <xref:System.Windows.Media.VisualBrush.Visual%2A> specificare <xref:System.Windows.Media.VisualBrush>il contenuto di un file .  
  
- Creare un <xref:System.Windows.Media.Visual> nuovo e utilizzarlo per impostare la <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà del <xref:System.Windows.Media.VisualBrush>file . Per un esempio, vedere la sezione [Esempio: disegnare un oggetto con un oggetto Visual](#examplevisualbrush1) seguente.  
  
- Utilizzare un <xref:System.Windows.Media.Visual>oggetto esistente , che <xref:System.Windows.Media.Visual>crea un'immagine duplicata della destinazione. È quindi possibile <xref:System.Windows.Media.VisualBrush> utilizzare il per creare effetti interessanti, come la riflessione e l'ingrandimento. Per un esempio, vedere la sezione [Esempio: creare una reflection](#examplevisualbrush2).  
  
 Quando si definisce un <xref:System.Windows.Media.VisualBrush.Visual%2A> nuovo oggetto e <xref:System.Windows.Media.VisualBrush> che <xref:System.Windows.Media.Visual> è un <xref:System.Windows.UIElement> (ad esempio <xref:System.Windows.UIElement> un pannello o <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> un controllo), il sistema di layout viene eseguito sugli elementi figlio e e quando la proprietà è impostata su `true`. Tuttavia, <xref:System.Windows.UIElement> la radice è essenzialmente isolata dal resto del sistema: gli stili e il layout esterno non può permeare questo limite. Pertanto, è necessario specificare <xref:System.Windows.UIElement>in modo esplicito <xref:System.Windows.Media.VisualBrush> la dimensione della radice , poiché il relativo unico elemento padre è l'oggetto e pertanto non può ridimensionarsi automaticamente nell'area disegnata. Per altre informazioni sul layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], vedere [Layout](../advanced/layout.md).  
  
 Like <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>e <xref:System.Windows.Media.VisualBrush> , un allunga il suo contenuto per riempire la sua area di output. È possibile eseguire l'override di questo comportamento modificando la proprietà dall'impostazione <xref:System.Windows.Media.TileBrush.Stretch%2A> predefinita di <xref:System.Windows.Media.Stretch.Fill>. Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>
## <a name="example-paint-an-object-with-a-visual"></a>Esempio: disegnare un oggetto con un oggetto Visual  
 L'esempio seguente usa numerosi controlli e un pannello per disegnare un rettangolo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>
## <a name="example-create-a-reflection"></a>Esempio: creare una reflection  
 Nell'esempio precedente è stato <xref:System.Windows.Media.Visual> illustrato come creare un nuovo per l'utilizzo come sfondo. È inoltre possibile <xref:System.Windows.Media.VisualBrush> utilizzare un oggetto per visualizzare un oggetto visivo esistente; questa funzionalità consente di produrre effetti visivi interessanti, come riflessi e ingrandimento. Nell'esempio seguente <xref:System.Windows.Media.VisualBrush> viene utilizzato un <xref:System.Windows.Controls.Border> per creare una reflection di un che contiene diversi elementi. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Oggetto Visual riflesso](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Oggetto Visual riflesso  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Per altri esempi che illustrano come ingrandire parti dello schermo e come creare reflection, vedere [Esempio VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).  
  
<a name="tilebrush"></a>
## <a name="tilebrush-features"></a>Funzionalità degli oggetti TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush> e <xref:System.Windows.Media.TileBrush> sono tipi di oggetti. <xref:System.Windows.Media.TileBrush>gli oggetti forniscono un grande controllo sul modo in cui un'area viene disegnata con un'immagine, un disegno o un oggetto visivo. Anziché ad esempio disegnare un'area con una sola immagine estesa, è possibile usare una serie di immagini affiancate che creano un modello.  
  
 A <xref:System.Windows.Media.TileBrush> ha tre componenti principali: contenuto, riquadri e l'area di output.  
  
 ![Componenti di TileBrush](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componenti di un oggetto TileBrush con una sola tessera  
  
 ![Componenti di un oggetto TileBrush affiancato](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componenti di un oggetto TileBrush con più tessere  
  
 Per ulteriori informazioni sulle funzionalità <xref:System.Windows.Media.TileBrush> di affiancamento degli oggetti, vedere Cenni preliminari su [TileBrush](tilebrush-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Panoramica sugli oggetti TileBrush](tilebrush-overview.md)
- [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md)
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sulle maschere di opacità](opacity-masks-overview.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
- [Esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [Esempio VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
