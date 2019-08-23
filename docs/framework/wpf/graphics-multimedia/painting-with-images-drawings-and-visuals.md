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
ms.openlocfilehash: e80132a5467f932e5569787f43427044ba2be256
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929601"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Disegnare con oggetti Image, Drawing e Visual
In questo argomento viene descritto come <xref:System.Windows.Media.ImageBrush>utilizzare <xref:System.Windows.Media.DrawingBrush>gli oggetti <xref:System.Windows.Media.VisualBrush> , e per disegnare un'area con un'immagine, <xref:System.Windows.Media.Drawing>un oggetto o <xref:System.Windows.Media.Visual>un oggetto.  

<a name="prereqs"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere i diversi tipi di pennelli forniti da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e le relative funzionalità di base. Per un'introduzione, vedere [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md).  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>Disegnare un'area con un'immagine  
 Disegna un'area con un oggetto <xref:System.Windows.Media.ImageSource>. <xref:System.Windows.Media.ImageBrush> Il tipo più comune di <xref:System.Windows.Media.ImageSource> da utilizzare con un <xref:System.Windows.Media.ImageBrush> è un <xref:System.Windows.Media.Imaging.BitmapImage>oggetto, che descrive un'immagine bitmap. È possibile usare <xref:System.Windows.Media.DrawingImage> un oggetto per disegnare usando <xref:System.Windows.Media.Drawing> un oggetto, ma è più semplice usare invece un <xref:System.Windows.Media.DrawingBrush> oggetto. Per ulteriori informazioni sugli <xref:System.Windows.Media.ImageSource> oggetti, vedere [Cenni preliminari sulla creazione di immagini](imaging-overview.md).  
  
 Per disegnare con un <xref:System.Windows.Media.ImageBrush>oggetto, creare <xref:System.Windows.Media.Imaging.BitmapImage> un oggetto e usarlo per caricare il contenuto della bitmap. Utilizzare <xref:System.Windows.Media.Imaging.BitmapImage> quindi per impostare la <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà dell'oggetto <xref:System.Windows.Media.ImageBrush>. Infine, applicare <xref:System.Windows.Media.ImageBrush> all'oggetto che si desidera disegnare.  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]è anche possibile impostare solo la <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà dell'oggetto <xref:System.Windows.Media.ImageBrush> con il percorso dell'immagine da caricare.  
  
 Come tutti <xref:System.Windows.Media.Brush> gli oggetti, <xref:System.Windows.Media.ImageBrush> un oggetto può essere usato per disegnare oggetti quali forme, pannelli, controlli e testo. Nella figura seguente vengono illustrati alcuni effetti che è possibile ottenere <xref:System.Windows.Media.ImageBrush>con un.  
  
 ![Esempi di output di ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Oggetti disegnati con un oggetto ImageBrush  
  
 Per impostazione predefinita, <xref:System.Windows.Media.ImageBrush> un oggetto estende la propria immagine in modo da riempire completamente l'area disegnata, eventualmente distorcendo l'immagine se l'area disegnata presenta proporzioni diverse rispetto all'immagine. È possibile modificare questo comportamento modificando la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà dal valore predefinito di <xref:System.Windows.Media.Stretch.Fill> a <xref:System.Windows.Media.Stretch.None>, <xref:System.Windows.Media.Stretch.Uniform>o <xref:System.Windows.Media.Stretch.UniformToFill>. Poiché <xref:System.Windows.Media.ImageBrush> è un tipo di <xref:System.Windows.Media.TileBrush>, è possibile specificare esattamente il modo in cui un pennello immagine riempie l'area di output e persino creare modelli. Per ulteriori informazioni sulle funzionalità <xref:System.Windows.Media.TileBrush> avanzate, vedere [Panoramica di TileBrush](tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Esempio: Disegnare un oggetto con un'immagine bitmap  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.ImageBrush> un oggetto per <xref:System.Windows.Controls.Panel.Background%2A> disegnare l' <xref:System.Windows.Controls.Canvas>oggetto di un oggetto.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Inserire un disegno in un'area  
 Un <xref:System.Windows.Media.DrawingBrush> oggetto consente di disegnare un'area con forme, testo, immagini e video. Le forme all'interno di un pennello possono essere disegnate con un colore a tinta unita, una sfumatura, un'immagine o anche un'altra <xref:System.Windows.Media.DrawingBrush>. Nella figura seguente vengono illustrati alcuni utilizzi <xref:System.Windows.Media.DrawingBrush>di un oggetto.  
  
 ![Esempi di output di DrawingBrush](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Oggetti disegnati con un oggetto DrawingBrush  
  
 Disegna un'area con un <xref:System.Windows.Media.Drawing> oggetto. <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.Drawing> Oggetto che descrive il contenuto visibile, ad esempio una forma, una bitmap, un video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
- <xref:System.Windows.Media.GeometryDrawing>: Disegna una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>: Disegna un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>: Disegna il testo.  
  
- <xref:System.Windows.Media.VideoDrawing>: Riproduce un file audio o video.  
  
- <xref:System.Windows.Media.DrawingGroup>: Disegna altri disegni. Usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 Per ulteriori informazioni sugli <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).  
  
 Analogamente <xref:System.Windows.Media.ImageBrush>a un <xref:System.Windows.Media.DrawingBrush> oggetto, un <xref:System.Windows.Media.DrawingBrush.Drawing%2A> oggetto estende per riempire l'area di output. È possibile eseguire l'override di questo comportamento <xref:System.Windows.Media.TileBrush.Stretch%2A> modificando la proprietà dall'impostazione <xref:System.Windows.Media.Stretch.Fill>predefinita di. Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>Esempio: Disegnare un oggetto con un oggetto  
 L'esempio seguente illustra come disegnare un oggetto con un disegno di tre ellissi. Un <xref:System.Windows.Media.GeometryDrawing> oggetto viene utilizzato per descrivere i puntini di sospensione.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>Disegnare un'area con un oggetto Visual  
 Il più versatile e potente di tutti i pennelli, <xref:System.Windows.Media.VisualBrush> disegna un'area con un oggetto <xref:System.Windows.Media.Visual>. Un <xref:System.Windows.Media.Visual> è un tipo grafico di basso livello che funge da predecessore di molti componenti grafici utili. Ad esempio, le <xref:System.Windows.Window>classi <xref:System.Windows.FrameworkElement>, e <xref:System.Windows.Controls.Control> sono tutti tipi di <xref:System.Windows.Media.Visual> oggetti. Utilizzando un <xref:System.Windows.Media.VisualBrush>è possibile disegnare aree con quasi tutti [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gli oggetti grafici.  
  
> [!NOTE]
> Sebbene <xref:System.Windows.Media.VisualBrush> sia un tipo di <xref:System.Windows.Freezable> oggetto, non può essere bloccato (reso di sola lettura) quando la <xref:System.Windows.Media.VisualBrush.Visual%2A> relativa proprietà è impostata su un valore diverso `null`da.  
  
 Esistono due modi per specificare il <xref:System.Windows.Media.VisualBrush.Visual%2A> contenuto di un oggetto. <xref:System.Windows.Media.VisualBrush>  
  
- Creare un nuovo <xref:System.Windows.Media.Visual> oggetto e usarlo per impostare <xref:System.Windows.Media.VisualBrush.Visual%2A> la proprietà dell' <xref:System.Windows.Media.VisualBrush>oggetto. Per un esempio, vedere l' [esempio: Disegnare un oggetto con una sezione](#examplevisualbrush1) visiva che segue.  
  
- Usare un oggetto <xref:System.Windows.Media.Visual>esistente, che crea un'immagine duplicata della <xref:System.Windows.Media.Visual>destinazione. È quindi possibile usare per <xref:System.Windows.Media.VisualBrush> creare effetti interessanti, ad esempio la reflection e l'ingrandimento. Per un esempio, vedere l' [esempio: Creare una sezione](#examplevisualbrush2) di Reflection.  
  
 Quando si definisce un nuovo <xref:System.Windows.Media.VisualBrush.Visual%2A> oggetto per <xref:System.Windows.Media.VisualBrush> un oggetto <xref:System.Windows.Media.Visual> e che <xref:System.Windows.UIElement> è un oggetto (ad esempio un <xref:System.Windows.UIElement> pannello o un controllo), il sistema di layout viene eseguito in e <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> nei relativi elementi figlio `true`quando la proprietà è impostata su. Tuttavia, la radice <xref:System.Windows.UIElement> è essenzialmente isolata dal resto del sistema: gli stili e il layout esterno non può permeare questo limite. Pertanto, è necessario specificare in modo esplicito le dimensioni della <xref:System.Windows.UIElement>radice, poiché l'unico elemento padre <xref:System.Windows.Media.VisualBrush> è e pertanto non può ridimensionarsi automaticamente nell'area da disegnare. Per altre informazioni sul layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], vedere [Layout](../advanced/layout.md).  
  
 Come <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.VisualBrush> e <xref:System.Windows.Media.DrawingBrush>, un oggetto estende il contenuto per riempire l'area di output. È possibile eseguire l'override di questo comportamento <xref:System.Windows.Media.TileBrush.Stretch%2A> modificando la proprietà dall'impostazione <xref:System.Windows.Media.Stretch.Fill>predefinita di. Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>Esempio: Disegnare un oggetto con un oggetto visivo  
 L'esempio seguente usa numerosi controlli e un pannello per disegnare un rettangolo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>Esempio: Creare una reflection  
 Nell'esempio precedente è stato illustrato come creare un <xref:System.Windows.Media.Visual> nuovo oggetto da utilizzare come sfondo. È anche possibile usare un <xref:System.Windows.Media.VisualBrush> oggetto per visualizzare un oggetto visivo esistente. questa funzionalità consente di produrre effetti visivi interessanti, ad esempio reflection e ingrandimento. Nell'esempio seguente viene usato <xref:System.Windows.Media.VisualBrush> un oggetto per creare un riflesso <xref:System.Windows.Controls.Border> di un oggetto che contiene diversi elementi. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Oggetto visivo riflesso](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Oggetto Visual riflesso  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Per altri esempi che illustrano come ingrandire parti dello schermo e come creare reflection, vedere [Esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>Funzionalità degli oggetti TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.TileBrush> e <xref:System.Windows.Media.VisualBrush> sono tipi di oggetti. <xref:System.Windows.Media.TileBrush>gli oggetti forniscono una grande quantità di controllo sulla modalità di disegno di un'area con un'immagine, un disegno o un oggetto visivo. Anziché ad esempio disegnare un'area con una sola immagine estesa, è possibile usare una serie di immagini affiancate che creano un modello.  
  
 Un <xref:System.Windows.Media.TileBrush> oggetto è costituito da tre componenti principali: contenuto, riquadri e area di output.  
  
 ![TileBrush components](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componenti di un oggetto TileBrush con una sola tessera  
  
 ![Componenti di un TileBrush affiancato](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componenti di un oggetto TileBrush con più tessere  
  
 Per ulteriori informazioni sulle funzionalità di affiancamento <xref:System.Windows.Media.TileBrush> degli oggetti, vedere [Cenni preliminari](tilebrush-overview.md)sugli oggetti TileBrush.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Panoramica sugli oggetti TileBrush](tilebrush-overview.md)
- [Panoramica sui pennelli di WPF](wpf-brushes-overview.md)
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Panoramica sulle maschere di opacità](opacity-masks-overview.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
- [Esempio di ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
