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
ms.openlocfilehash: bb66c34a847f78f7921ae925d0c3d0640c11aeec
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361323"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Disegnare con oggetti Image, Drawing e Visual
In questo argomento viene descritto come utilizzare <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, e <xref:System.Windows.Media.VisualBrush> oggetti da disegnare un'area con un'immagine, una <xref:System.Windows.Media.Drawing>, o un <xref:System.Windows.Media.Visual>.  
    
  
<a name="prereqs"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere i diversi tipi di pennelli forniti da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e le relative funzionalità di base. Per un'introduzione, vedere [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md).  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>Disegnare un'area con un'immagine  
 Un' <xref:System.Windows.Media.ImageBrush> disegna un'area con un <xref:System.Windows.Media.ImageSource>. Il tipo più comune di <xref:System.Windows.Media.ImageSource> da usare con un' <xref:System.Windows.Media.ImageBrush> è un <xref:System.Windows.Media.Imaging.BitmapImage>, in cui viene descritto un grafico bitmap. È possibile usare una <xref:System.Windows.Media.DrawingImage> per disegnare usando una <xref:System.Windows.Media.Drawing> oggetti, ma è più semplice usare un <xref:System.Windows.Media.DrawingBrush> invece. Per altre informazioni sulle <xref:System.Windows.Media.ImageSource> oggetti, vedere la [Cenni preliminari sulla creazione di immagini](imaging-overview.md).  
  
 Disegnare con un <xref:System.Windows.Media.ImageBrush>, creare un <xref:System.Windows.Media.Imaging.BitmapImage> e usarlo per caricare il contenuto bitmap. Quindi, usare il <xref:System.Windows.Media.Imaging.BitmapImage> per impostare il <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà del <xref:System.Windows.Media.ImageBrush>. Infine, applicare il <xref:System.Windows.Media.ImageBrush> all'oggetto di cui si desidera disegnare.  Nelle [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è anche possibile impostare il <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà del <xref:System.Windows.Media.ImageBrush> con il percorso dell'immagine da caricare.  
  
 Analogamente a tutti i <xref:System.Windows.Media.Brush> oggetti, un <xref:System.Windows.Media.ImageBrush> può essere utilizzato per disegnare oggetti, ad esempio forme, pannelli, controlli e testo. La figura seguente mostra alcuni effetti che possono essere ottenute con un <xref:System.Windows.Media.ImageBrush>.  
  
 ![Esempi di output di ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Oggetti disegnati con un oggetto ImageBrush  
  
 Per impostazione predefinita, un <xref:System.Windows.Media.ImageBrush> occupa completamente la propria immagine per riempire completamente l'area disegnata, eventualmente distorcendo l'immagine se tale area presenta proporzioni diverse rispetto all'immagine. È possibile modificare questo comportamento cambiando il <xref:System.Windows.Media.TileBrush.Stretch%2A> rispetto al valore predefinito della proprietà <xref:System.Windows.Media.Stretch.Fill> al <xref:System.Windows.Media.Stretch.None>, <xref:System.Windows.Media.Stretch.Uniform>, o <xref:System.Windows.Media.Stretch.UniformToFill>. In quanto <xref:System.Windows.Media.ImageBrush> è un tipo di <xref:System.Windows.Media.TileBrush>, è possibile specificare esattamente come un tratto con immagine riempie l'area di output e persino creare dei modelli. Per altre informazioni su advanced <xref:System.Windows.Media.TileBrush> funzionalità, vedere la [Cenni preliminari sugli oggetti TileBrush](tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Esempio: Disegnare un oggetto con un'immagine Bitmap  
 L'esempio seguente usa un' <xref:System.Windows.Media.ImageBrush> per disegnare il <xref:System.Windows.Controls.Panel.Background%2A> di un <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Inserire un disegno in un'area  
 Oggetto <xref:System.Windows.Media.DrawingBrush> consente di disegnare un'area con forme, testo, immagini e video. Forme all'interno di un pennello da disegno potrebbero a loro volta essere disegnate con un colore a tinta unita, sfumature, immagini, o anche un altro <xref:System.Windows.Media.DrawingBrush>. Nella figura seguente mostra alcuni usi di un <xref:System.Windows.Media.DrawingBrush>.  
  
 ![Esempi di output di DrawingBrush](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Oggetti disegnati con un oggetto DrawingBrush  
  
 Oggetto <xref:System.Windows.Media.DrawingBrush> disegna un'area con un <xref:System.Windows.Media.Drawing> oggetto. Oggetto <xref:System.Windows.Media.Drawing> oggetto descrive il contenuto visibile, ad esempio una forma, bitmap, video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
-   <xref:System.Windows.Media.GeometryDrawing> – Consente di disegnare una forma.  
  
-   <xref:System.Windows.Media.ImageDrawing> – Consente di disegnare un'immagine.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> : Crea testo.  
  
-   <xref:System.Windows.Media.VideoDrawing> : Riproduce un file audio o video.  
  
-   <xref:System.Windows.Media.DrawingGroup> : Esegue altri disegni. Usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 Per altre informazioni sulle <xref:System.Windows.Media.Drawing> oggetti, vedere la [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).  
  
 Ad esempio un <xref:System.Windows.Media.ImageBrush>, una <xref:System.Windows.Media.DrawingBrush> estende relativo <xref:System.Windows.Media.DrawingBrush.Drawing%2A> per riempire l'area di output. È possibile eseguire l'override di questo comportamento cambiando il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà dall'impostazione predefinita del <xref:System.Windows.Media.Stretch.Fill>. Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>Esempio: Disegnare un oggetto con un oggetto  
 L'esempio seguente illustra come disegnare un oggetto con un disegno di tre ellissi. Oggetto <xref:System.Windows.Media.GeometryDrawing> viene usato per descrivere i puntini di sospensione.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>Disegnare un'area con un oggetto Visual  
 La più versatile e potente di tutti i pennelli, le <xref:System.Windows.Media.VisualBrush> disegna un'area con un <xref:System.Windows.Media.Visual>. Oggetto <xref:System.Windows.Media.Visual> è un tipo con interfaccia grafico di basso livello che serve da predecessore di molti componenti grafici utili. Ad esempio, il <xref:System.Windows.Window>, <xref:System.Windows.FrameworkElement>, e <xref:System.Windows.Controls.Control> classi vengono tutti i tipi di <xref:System.Windows.Media.Visual> oggetti. Usando un <xref:System.Windows.Media.VisualBrush>, è possibile disegnare aree con quasi tutti [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gli oggetti grafici.  
  
> [!NOTE]
>  Sebbene <xref:System.Windows.Media.VisualBrush> è un tipo di <xref:System.Windows.Freezable> dell'oggetto, non è possibile bloccarlo (impostarlo in sola lettura) quando relativo <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà è impostata su un valore diverso da `null`.  
  
 Esistono due modi per specificare il <xref:System.Windows.Media.VisualBrush.Visual%2A> contenuto di un <xref:System.Windows.Media.VisualBrush>.  
  
-   Creare una nuova <xref:System.Windows.Media.Visual> e usarlo per impostare il <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà del <xref:System.Windows.Media.VisualBrush>. Per un esempio, vedere il [esempio: Disegnare un oggetto con un oggetto visivo](#examplevisualbrush1) sezione che segue.  
  
-   Usare un oggetto esistente <xref:System.Windows.Media.Visual>, che consente di creare un'immagine duplicata della destinazione <xref:System.Windows.Media.Visual>. È quindi possibile usare il <xref:System.Windows.Media.VisualBrush> per creare effetti interessanti, ad esempio reflection e ingrandimento. Per un esempio, vedere il [esempio: Creare una Reflection](#examplevisualbrush2) sezione.  
  
 Quando si definisce una nuova <xref:System.Windows.Media.VisualBrush.Visual%2A> per un <xref:System.Windows.Media.VisualBrush> e che <xref:System.Windows.Media.Visual> è un <xref:System.Windows.UIElement> (ad esempio un pannello o un controllo), viene eseguito il sistema di layout nel <xref:System.Windows.UIElement> e i relativi elementi figlio quando il <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> è impostata su `true`. Tuttavia, la radice <xref:System.Windows.UIElement> viene essenzialmente isolato dal resto del sistema: gli stili e layout esterno non può superare questo limite. Pertanto, è necessario specificare in modo esplicito le dimensioni della radice <xref:System.Windows.UIElement>, in quanto il suo unico elemento padre è il <xref:System.Windows.Media.VisualBrush> e pertanto non può essere ridimensionato automaticamente se stesso per l'area da disegnare. Per altre informazioni sul layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], vedere [Layout](../advanced/layout.md).  
  
 Ad esempio <xref:System.Windows.Media.ImageBrush> e <xref:System.Windows.Media.DrawingBrush>, un <xref:System.Windows.Media.VisualBrush> estende il proprio contenuto per riempire l'area di output. È possibile eseguire l'override di questo comportamento cambiando il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà dall'impostazione predefinita del <xref:System.Windows.Media.Stretch.Fill>. Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>Esempio: Disegnare un oggetto con un oggetto visivo  
 L'esempio seguente usa numerosi controlli e un pannello per disegnare un rettangolo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>Esempio: Creare una reflection  
 Nell'esempio precedente è stato illustrato come creare un nuovo <xref:System.Windows.Media.Visual> da utilizzare come sfondo. È anche possibile usare un <xref:System.Windows.Media.VisualBrush> per visualizzare un elemento visivo esistente; questa funzionalità consente di produrre effetti visivi interessanti, ad esempio reflection e ingrandimento. L'esempio seguente usa un' <xref:System.Windows.Media.VisualBrush> per creare un riflesso di un <xref:System.Windows.Controls.Border> che contiene diversi elementi. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Un oggetto visivo di riflessi](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Oggetto Visual riflesso  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Per altri esempi che illustrano come ingrandire parti dello schermo e come creare reflection, vedere [Esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>Funzionalità degli oggetti TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, e <xref:System.Windows.Media.VisualBrush> sono tipi di <xref:System.Windows.Media.TileBrush> oggetti. <xref:System.Windows.Media.TileBrush> gli oggetti forniscono un elevato livello di controllo sulle modalità di disegno di un'area con un'immagine, drawing o oggetto visivo. Anziché ad esempio disegnare un'area con una sola immagine estesa, è possibile usare una serie di immagini affiancate che creano un modello.  
  
 Oggetto <xref:System.Windows.Media.TileBrush> include tre componenti principali: il contenuto, tessere e area di output.  
  
 ![TileBrush components](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componenti di un oggetto TileBrush con una sola tessera  
  
 ![Componenti di TileBrush affiancato](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componenti di un oggetto TileBrush con più tessere  
  
 Per altre informazioni sulle funzionalità di affiancamento <xref:System.Windows.Media.TileBrush> oggetti, vedere la [Cenni preliminari sugli oggetti TileBrush](tilebrush-overview.md).  
  
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
- [Esempio ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
