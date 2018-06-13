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
ms.openlocfilehash: abb5733ed54ea430ba161db5ea2dcb33e99298ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566912"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Disegnare con oggetti Image, Drawing e Visual
In questo argomento viene descritto come utilizzare <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, e <xref:System.Windows.Media.VisualBrush> oggetti per disegnare un'area con un'immagine, un <xref:System.Windows.Media.Drawing>, o un <xref:System.Windows.Media.Visual>.  
    
  
<a name="prereqs"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere i diversi tipi di pennelli forniti da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e le relative funzionalità di base. Per un'introduzione, vedere [Cenni preliminari sui pennelli di WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>Disegnare un'area con un'immagine  
 Un <xref:System.Windows.Media.ImageBrush> disegna un'area con un <xref:System.Windows.Media.ImageSource>. Il tipo più comune di <xref:System.Windows.Media.ImageSource> da utilizzare con un <xref:System.Windows.Media.ImageBrush> è un <xref:System.Windows.Media.Imaging.BitmapImage>, che descrive un'immagine bitmap. È possibile utilizzare un <xref:System.Windows.Media.DrawingImage> per disegnare utilizzando un <xref:System.Windows.Media.Drawing> oggetto, ma è più semplice da utilizzare un <xref:System.Windows.Media.DrawingBrush> invece. Per ulteriori informazioni su <xref:System.Windows.Media.ImageSource> degli oggetti, vedere il [Imaging Overview](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
 Per disegnare con un <xref:System.Windows.Media.ImageBrush>, creare un <xref:System.Windows.Media.Imaging.BitmapImage> e utilizzarlo per caricare il contenuto della bitmap. Utilizzare quindi la <xref:System.Windows.Media.Imaging.BitmapImage> per impostare il <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà del <xref:System.Windows.Media.ImageBrush>. Infine, applicare il <xref:System.Windows.Media.ImageBrush> per l'oggetto da disegnare.  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è anche possibile impostare il <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà del <xref:System.Windows.Media.ImageBrush> con il percorso dell'immagine da caricare.  
  
 Come tutti <xref:System.Windows.Media.Brush> oggetti, un <xref:System.Windows.Media.ImageBrush> può essere utilizzato per disegnare oggetti, ad esempio forme, pannelli, controlli e testo. La figura seguente illustra alcuni degli effetti che possono essere ottenuti con un <xref:System.Windows.Media.ImageBrush>.  
  
 ![Esempi di output di ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Oggetti disegnati con un oggetto ImageBrush  
  
 Per impostazione predefinita, un <xref:System.Windows.Media.ImageBrush> occupa l'immagine per riempire completamente l'area da disegnare, probabilmente distorsione dell'immagine se l'area presenta proporzioni diverse rispetto all'immagine. È possibile modificare questo comportamento cambiando il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà rispetto al valore predefinito di <xref:System.Windows.Media.Stretch.Fill> a <xref:System.Windows.Media.Stretch.None>, <xref:System.Windows.Media.Stretch.Uniform>, o <xref:System.Windows.Media.Stretch.UniformToFill>. Poiché <xref:System.Windows.Media.ImageBrush> è un tipo di <xref:System.Windows.Media.TileBrush>, è possibile specificare esattamente come un tratto con immagine riempie l'area di output e persino creare dei modelli. Per ulteriori informazioni su advanced <xref:System.Windows.Media.TileBrush> funzionalità, vedere il [TileBrush Overview](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Esempio: disegnare un oggetto con un'immagine bitmap  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.ImageBrush> per disegnare il <xref:System.Windows.Controls.Panel.Background%2A> di un <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Inserire un disegno in un'area  
 Oggetto <xref:System.Windows.Media.DrawingBrush> consente di disegnare un'area con forme, testo, immagini e video. Forme all'interno di un pennello da disegno possono a loro volta essere disegnate con un colore a tinta unita, sfumatura, immagine, o addirittura altro <xref:System.Windows.Media.DrawingBrush>. La figura seguente illustra alcuni utilizzi di un <xref:System.Windows.Media.DrawingBrush>.  
  
 ![Esempi di output di DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Oggetti disegnati con un oggetto DrawingBrush  
  
 Oggetto <xref:System.Windows.Media.DrawingBrush> disegna un'area con un <xref:System.Windows.Media.Drawing> oggetto. Oggetto <xref:System.Windows.Media.Drawing> descrive il contenuto visibile, ad esempio una forma, bitmap, video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
-   <xref:System.Windows.Media.GeometryDrawing> – Disegna una forma.  
  
-   <xref:System.Windows.Media.ImageDrawing> -Consente di disegnare un'immagine.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> – Disegna un testo.  
  
-   <xref:System.Windows.Media.VideoDrawing> -Consente di riprodurre un file audio o video.  
  
-   <xref:System.Windows.Media.DrawingGroup> : Consente di eseguire altri disegni. Usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 Per ulteriori informazioni su <xref:System.Windows.Media.Drawing> degli oggetti, vedere il [panoramica sugli oggetti disegno](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
 Ad esempio un <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> allunga relativo <xref:System.Windows.Media.DrawingBrush.Drawing%2A> per riempire l'area di output. È possibile eseguire l'override di questo comportamento cambiando il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà dall'impostazione predefinita di <xref:System.Windows.Media.Stretch.Fill>. Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>Esempio: disegnare un oggetto con un oggetto Drawing  
 L'esempio seguente illustra come disegnare un oggetto con un disegno di tre ellissi. Oggetto <xref:System.Windows.Media.GeometryDrawing> viene utilizzato per descrivere i puntini di sospensione.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>Disegnare un'area con un oggetto Visual  
 La più versatile e potente di tutti i pennelli di <xref:System.Windows.Media.VisualBrush> disegna un'area con un <xref:System.Windows.Media.Visual>. Oggetto <xref:System.Windows.Media.Visual> è un tipo di grafico di basso livello che funge dal predecessore di molti componenti grafici utili. Ad esempio, il <xref:System.Windows.Window>, <xref:System.Windows.FrameworkElement>, e <xref:System.Windows.Controls.Control> classi sono tutti i tipi di <xref:System.Windows.Media.Visual> oggetti. Utilizzando un <xref:System.Windows.Media.VisualBrush>, consente di disegnare aree con quasi ogni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] oggetto grafico.  
  
> [!NOTE]
>  Sebbene <xref:System.Windows.Media.VisualBrush> è un tipo di <xref:System.Windows.Freezable> dell'oggetto, non può essere bloccato (in sola lettura) quando il relativo <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà è impostata su un valore diverso da `null`.  
  
 Esistono due modi per specificare il <xref:System.Windows.Media.VisualBrush.Visual%2A> contenuto di un <xref:System.Windows.Media.VisualBrush>.  
  
-   Creare un nuovo <xref:System.Windows.Media.Visual> e utilizzarla per impostare il <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà del <xref:System.Windows.Media.VisualBrush>. Per un esempio, vedere la sezione [Esempio: disegnare un oggetto con un oggetto Visual](#examplevisualbrush1) seguente.  
  
-   Utilizzare un'esistente <xref:System.Windows.Media.Visual>, che consente di creare un'immagine duplicata della destinazione <xref:System.Windows.Media.Visual>. È quindi possibile utilizzare il <xref:System.Windows.Media.VisualBrush> per creare effetti interessanti, ad esempio reflection e ingrandimento. Per un esempio, vedere la sezione [Esempio: creare una reflection](#examplevisualbrush2).  
  
 Quando si definisce un nuovo <xref:System.Windows.Media.VisualBrush.Visual%2A> per un <xref:System.Windows.Media.VisualBrush> e che <xref:System.Windows.Media.Visual> è un <xref:System.Windows.UIElement> (ad esempio un pannello di controllo o), il sistema di layout viene eseguito <xref:System.Windows.UIElement> e i relativi elementi figlio quando il <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> è impostata su `true`. Tuttavia, la radice <xref:System.Windows.UIElement> viene essenzialmente isolato dal resto del sistema: gli stili e layout esterno non può superare questo limite. Pertanto, è necessario specificare in modo esplicito le dimensioni dell'oggetto radice <xref:System.Windows.UIElement>, perché il relativo padre solo è il <xref:System.Windows.Media.VisualBrush> e pertanto non può essere ridimensionato automaticamente se stesso per l'area da disegnare. Per altre informazioni sul layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], vedere [Layout](../../../../docs/framework/wpf/advanced/layout.md).  
  
 Ad esempio <xref:System.Windows.Media.ImageBrush> e <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush> estende il proprio contenuto per riempire l'area di output. È possibile eseguire l'override di questo comportamento cambiando il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà dall'impostazione predefinita di <xref:System.Windows.Media.Stretch.Fill>. Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>Esempio: disegnare un oggetto con un oggetto Visual  
 L'esempio seguente usa numerosi controlli e un pannello per disegnare un rettangolo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>Esempio: creare una reflection  
 Nell'esempio precedente è stato illustrato come creare un nuovo <xref:System.Windows.Media.Visual> da utilizzare come sfondo. È inoltre possibile utilizzare un <xref:System.Windows.Media.VisualBrush> per visualizzare un elemento visivo esistente; questa funzionalità consente di produrre effetti visivi interessanti, ad esempio reflection e ingrandimento. Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.VisualBrush> per creare un riflesso di un <xref:System.Windows.Controls.Border> che contiene diversi elementi. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Oggetto riflesse oggetto visivo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Oggetto Visual riflesso  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Per altri esempi che illustrano come ingrandire parti dello schermo e come creare reflection, vedere [Esempio VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>Funzionalità degli oggetti TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, e <xref:System.Windows.Media.VisualBrush> sono tipi di <xref:System.Windows.Media.TileBrush> oggetti. <xref:System.Windows.Media.TileBrush> gli oggetti forniscono un elevato livello di controllo sulla modalità di disegno di un'area con un'immagine, disegno o di visual. Anziché ad esempio disegnare un'area con una sola immagine estesa, è possibile usare una serie di immagini affiancate che creano un modello.  
  
 Oggetto <xref:System.Windows.Media.TileBrush> costituito da tre componenti principali: il contenuto, sezioni e l'area di output.  
  
 ![Componenti di TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componenti di un oggetto TileBrush con una sola tessera  
  
 ![Componenti di TileBrush affiancato](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componenti di un oggetto TileBrush con più tessere  
  
 Per ulteriori informazioni sulle funzionalità di affiancamento di <xref:System.Windows.Media.TileBrush> degli oggetti, vedere il [TileBrush Overview](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 <xref:System.Windows.Media.TileBrush>  
 [Panoramica sugli oggetti TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [Panoramica sui pennelli di WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)  
 [Cenni preliminari sulla creazione dell'immagine](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Panoramica sulle maschere di opacità](../../../../docs/framework/wpf/graphics-multimedia/opacity-masks-overview.md)  
 [Cenni preliminari sul rendering della grafica WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Esempio ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [Esempio VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049)
