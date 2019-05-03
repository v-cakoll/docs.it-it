---
title: Cenni preliminari sugli oggetti Drawing
ms.date: 03/30/2017
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
ms.openlocfilehash: c065b06e7542913ae7fb495a0f69ff09dc4238b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020484"
---
# <a name="drawing-objects-overview"></a>Cenni preliminari sugli oggetti Drawing
Questo argomento vengono presentate <xref:System.Windows.Media.Drawing> oggetti e viene spiegato come usarle per creare in modo efficace le forme, bitmap, testo e supporti. Usare <xref:System.Windows.Media.Drawing> gli oggetti quando si crea ClipArt, disegnare con un <xref:System.Windows.Media.DrawingBrush>, oppure usare <xref:System.Windows.Media.Visual> oggetti.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Definizione di oggetto Drawing  
 Oggetto <xref:System.Windows.Media.Drawing> oggetto descrive il contenuto visibile, ad esempio una forma, bitmap, video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
- <xref:System.Windows.Media.GeometryDrawing> – Consente di disegnare una forma.  
  
- <xref:System.Windows.Media.ImageDrawing> – Consente di disegnare un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing> : Crea testo.  
  
- <xref:System.Windows.Media.VideoDrawing> : Riproduce un file audio o video.  
  
- <xref:System.Windows.Media.DrawingGroup> : Esegue altri disegni. Usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 <xref:System.Windows.Media.Drawing> gli oggetti sono versatili. Esistono molti modi, è possibile usare un <xref:System.Windows.Media.Drawing> oggetto.  
  
- È possibile visualizzare come un'immagine utilizzando un <xref:System.Windows.Media.DrawingImage> e un <xref:System.Windows.Controls.Image> controllo.  
  
- È possibile usarlo con un <xref:System.Windows.Media.DrawingBrush> disegnare un oggetto, ad esempio il <xref:System.Windows.Controls.Page.Background%2A> di un <xref:System.Windows.Controls.Page>.  
  
- È possibile usarlo per descrivere l'aspetto di un <xref:System.Windows.Media.DrawingVisual>.  
  
- È possibile usarlo per enumerare il contenuto di un <xref:System.Windows.Media.Visual>.  
  
 WPF fornisce altri tipi di oggetti che consentono di disegnare forme, bitmap, testo e contenuti multimediali. Ad esempio, è possibile usare anche <xref:System.Windows.Shapes.Shape> gli oggetti per disegnare forme e il <xref:System.Windows.Controls.MediaElement> controllo offre un altro modo per aggiungere video all'applicazione. Pertanto, quando è necessario usare <xref:System.Windows.Media.Drawing> oggetti? Quando è possibile sacrificare le funzionalità a livello di framework per migliorare le prestazioni o quando è necessario <xref:System.Windows.Freezable> funzionalità. Poiché <xref:System.Windows.Media.Drawing> mancano del supporto per gli oggetti [Layout](../advanced/layout.md), l'input e concentrare l'attenzione, offrono i vantaggi delle prestazioni che li rendono ideali per descrivere sfondi, ClipArt e per il disegno di basso livello con <xref:System.Windows.Media.Visual> oggetti.  
  
 Perché sono un tipo <xref:System.Windows.Freezable> oggetto, <xref:System.Windows.Media.Drawing> gli oggetti ottengono diverse funzionalità speciali, ad esempio: possono essere dichiarati come [risorse](../advanced/xaml-resources.md)condiviso tra più oggetti, sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per altre informazioni sulle diverse funzionalità fornita da <xref:System.Windows.Freezable> oggetti, vedere la [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Disegnare una forma  
 Per disegnare una forma, si utilizza un <xref:System.Windows.Media.GeometryDrawing>. Del disegno della geometria <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> proprietà descrive la forma da disegnare, relativi <xref:System.Windows.Media.GeometryDrawing.Brush%2A> proprietà descrive modo deve essere disegnato l'interno della forma e il relativo <xref:System.Windows.Media.GeometryDrawing.Pen%2A> proprietà descrive come deve essere disegnato il contorno.  
  
 L'esempio seguente usa un <xref:System.Windows.Media.GeometryDrawing> per disegnare una forma. La forma è descritta da un <xref:System.Windows.Media.GeometryGroup> e due <xref:System.Windows.Media.EllipseGeometry> oggetti. L'interno della forma viene disegnato con un <xref:System.Windows.Media.LinearGradientBrush> e la struttura viene disegnata con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.  
  
 In questo esempio vengono creati i seguenti <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![Un oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Per un esempio completo, vedere [Procedura: Creare un oggetto GeometryDrawing](how-to-create-a-geometrydrawing.md).  
  
 Altri <xref:System.Windows.Media.Geometry> classi, ad esempio <xref:System.Windows.Media.PathGeometry> consentono di creare forme più complesse mediante la creazione di curve e archi. Per altre informazioni sulle <xref:System.Windows.Media.Geometry> oggetti, vedere la [panoramica delle classi Geometry](geometry-overview.md).  
  
 Per altre informazioni su altri modi per disegnare forme che non utilizzano <xref:System.Windows.Media.Drawing> oggetti, vedere [forme e disegno di base di WPF Panoramica](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Disegnare un'immagine  
 Per disegnare un'immagine, si utilizza un <xref:System.Windows.Media.ImageDrawing>. Un' <xref:System.Windows.Media.ImageDrawing> dell'oggetto <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> proprietà descrive l'immagine da disegnare e il relativo <xref:System.Windows.Media.ImageDrawing.Rect%2A> proprietà definisce l'area in cui viene disegnata l'immagine.  
  
 L'esempio seguente disegna un'immagine in un rettangolo posizionata nel punto (75,75) vale a dire 100 x 100 pixel. La figura seguente illustra il <xref:System.Windows.Media.ImageDrawing> creato dall'esempio. Un bordo grigio è stato aggiunto per mostrare i limiti del <xref:System.Windows.Media.ImageDrawing>.  
  
 ![Un ImageDrawing di 100 per 100 disegnata in &#40;75,75&#41;](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing di 100 per 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Per altre informazioni sulle immagini, vedere [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Riprodurre contenuti multimediali (solo codice)  
  
> [!NOTE]
>  Sebbene sia possibile dichiarare un <xref:System.Windows.Media.VideoDrawing> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile solo caricare e riprodurre i file multimediali usando il codice. Per la riproduzione di video [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], usare un <xref:System.Windows.Controls.MediaElement> invece.  
  
 Per riprodurre un file audio o video, si utilizza un <xref:System.Windows.Media.VideoDrawing> e un <xref:System.Windows.Media.MediaPlayer>. È possibile caricare e riprodurre contenuti multimediali in due modi diversi. Il primo consiste nell'usare un <xref:System.Windows.Media.MediaPlayer> e una <xref:System.Windows.Media.VideoDrawing> da soli e il secondo modo consiste nel creare il proprio <xref:System.Windows.Media.MediaTimeline> da usare con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
 Per riprodurre contenuti multimediali senza creare il proprio <xref:System.Windows.Media.MediaTimeline>, attenersi alla procedura seguente.  
  
1. Creare un oggetto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Usare il <xref:System.Windows.Media.MediaPlayer.Open%2A> per caricare il file multimediale.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Creare un oggetto <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Specificare le dimensioni e il percorso in cui tracciare il contenuto multimediale impostando il <xref:System.Windows.Media.VideoDrawing.Rect%2A> proprietà del <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Impostare il <xref:System.Windows.Media.VideoDrawing.Player%2A> proprietà del <xref:System.Windows.Media.VideoDrawing> con il <xref:System.Windows.Media.MediaPlayer> creato.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Usare la <xref:System.Windows.Media.MediaPlayer.Play%2A> metodo del <xref:System.Windows.Media.MediaPlayer> per avviare la riproduzione di contenuto multimediale.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.VideoDrawing> e un <xref:System.Windows.Media.MediaPlayer> per riprodurre un file video sia una sola volta.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ottenere ulteriore controllo della durata dei contenuti multimediali, usare una <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti. Il <xref:System.Windows.Media.MediaTimeline> consente di specificare se il video deve essere ripetuto. Usare un <xref:System.Windows.Media.MediaTimeline> con un <xref:System.Windows.Media.VideoDrawing>, attenersi alla procedura seguente:  
  
1. Dichiarare il <xref:System.Windows.Media.MediaTimeline> e impostarne i comportamenti temporali.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Creare un <xref:System.Windows.Media.MediaClock> dal <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Creare un <xref:System.Windows.Media.MediaPlayer> e usare il <xref:System.Windows.Media.MediaClock> per impostare il <xref:System.Windows.Media.MediaPlayer.Clock%2A> proprietà.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Creare un <xref:System.Windows.Media.VideoDrawing> e assegnare il <xref:System.Windows.Media.MediaPlayer> per il <xref:System.Windows.Media.VideoDrawing.Player%2A> proprietà del <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.MediaTimeline> con un <xref:System.Windows.Media.MediaPlayer> e un <xref:System.Windows.Media.VideoDrawing> per riprodurre ripetutamente un video.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Si noti che, quando si usa una <xref:System.Windows.Media.MediaTimeline>, si usa l'oggetto interattivo <xref:System.Windows.Media.Animation.ClockController> restituiti dal <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà del <xref:System.Windows.Media.MediaClock> per controllare la riproduzione multimediale anziché i metodi interattivi della <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Creare testo  
 Per disegnare il testo, si usa un' <xref:System.Windows.Media.GlyphRunDrawing> e un <xref:System.Windows.Media.GlyphRun>. L'esempio seguente usa un <xref:System.Windows.Media.GlyphRunDrawing> per disegnare il testo "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Oggetto <xref:System.Windows.Media.GlyphRun> è un oggetto di basso livello deve essere usata con la presentazione di documenti a formato fisso e scenari di stampa. Per disegnare testo sullo schermo in modo più semplice consiste nell'utilizzare un <xref:System.Windows.Controls.Label> o un <xref:System.Windows.Controls.TextBlock>. Per altre informazioni sulle <xref:System.Windows.Media.GlyphRun>, vedere la [Introduzione all'oggetto GlyphRun e all'elemento Glyphs](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) Panoramica.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Disegni composti  
 Oggetto <xref:System.Windows.Media.DrawingGroup> consente di combinare più disegni in un unico disegno composto. Usando un <xref:System.Windows.Media.DrawingGroup>, è possibile combinare forme, immagini e testo in un singolo <xref:System.Windows.Media.Drawing> oggetto.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.DrawingGroup> per combinare due <xref:System.Windows.Media.GeometryDrawing> gli oggetti e un <xref:System.Windows.Media.ImageDrawing> oggetto. Questo esempio produce il seguente output:  
  
 ![Oggetto DrawingGroup con più disegni](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Disegno composto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Oggetto <xref:System.Windows.Media.DrawingGroup> consente inoltre di applicare maschere di opacità, trasformazioni, effetti bitmap e altre operazioni al relativo contenuto. <xref:System.Windows.Media.DrawingGroup> le operazioni vengono applicate nell'ordine seguente: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>e quindi <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 La figura seguente mostra l'ordine in cui <xref:System.Windows.Media.DrawingGroup> vengono applicate le operazioni.  
  
 ![Ordine delle operazioni DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Ordine delle operazioni DrawingGroup  
  
 Nella tabella seguente vengono descritte le proprietà è possibile usare per manipolare un <xref:System.Windows.Media.DrawingGroup> contenuto dell'oggetto.  
  
|Proprietà|Descrizione|Illustrazione|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Modifica l'opacità delle porzioni selezionate del <xref:System.Windows.Media.DrawingGroup> contenuto. Per un esempio, vedere [Procedura: Controllare l'opacità di un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![Oggetto DrawingGroup con una maschera di opacità](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Modificare in modo uniforme l'opacità del <xref:System.Windows.Media.DrawingGroup> contenuto. Utilizzare questa proprietà per rendere un <xref:System.Windows.Media.Drawing> trasparenti o parzialmente trasparenti. Per un esempio, vedere [Procedura: Applicare una maschera di opacità a un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)).|![Oggetto DrawingGroups con impostazioni di opacità diverse](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Si applica una <xref:System.Windows.Media.Effects.BitmapEffect> per il <xref:System.Windows.Media.DrawingGroup> contenuto. Per un esempio, vedere [Procedura: Applicare un BitmapEffect a un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![Oggetto DrawingGroup con BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Ritaglia il <xref:System.Windows.Media.DrawingGroup> contenuto in un'area descritta mediante un <xref:System.Windows.Media.Geometry>. Per un esempio, vedere [Procedura: Ritagliare un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) .|![Oggetto DrawingGroup con area ritagliata definita](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Consente di bloccare i pixel indipendenti del dispositivo ai pixel del dispositivo lungo linee guida specificate. Questa proprietà è utile per garantire che il rendering degli elementi grafici dettagliati venga eseguito con precisione su schermi a DPI basso. Per un esempio, vedere [Procedura: Applicare un GuidelineSet a un disegno](how-to-apply-a-guidelineset-to-a-drawing.md).|![Oggetto DrawingGroup con e senza un GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Trasforma il <xref:System.Windows.Media.DrawingGroup> contenuto. Per un esempio, vedere [Procedura: Applicare una trasformazione a un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)).|![Oggetto DrawingGroup ruotato](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Visualizzare un disegno come immagine  
 Per visualizzare un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Controls.Image> controllare, utilizzare un <xref:System.Windows.Media.DrawingImage> come il <xref:System.Windows.Controls.Image> del controllo <xref:System.Windows.Controls.Image.Source%2A> e impostare il <xref:System.Windows.Media.DrawingImage> dell'oggetto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> proprietà per il disegno che si desidera visualizzare.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.DrawingImage> e un' <xref:System.Windows.Controls.Image> controllo per visualizzare un <xref:System.Windows.Media.GeometryDrawing>. Questo esempio produce il seguente output:  
  
 ![Un oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Oggetto DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Disegnare un oggetto con un oggetto  
 Oggetto <xref:System.Windows.Media.DrawingBrush> è un tipo di pennello che disegna un'area con un oggetto drawing. Può essere usato per disegnare quasi tutti gli oggetti grafici con un oggetto Drawing. Il <xref:System.Windows.Media.Drawing> proprietà di un <xref:System.Windows.Media.DrawingBrush> descrive il <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Eseguire il rendering di un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Media.DrawingBrush>, aggiungerlo al pennello usando la proprietà del pennello <xref:System.Windows.Media.Drawing> proprietà e utilizzare il pennello per disegnare un grafico di oggetti, ad esempio un controllo o un pannello.  
  
 Nell'esempio seguente usa un' <xref:System.Windows.Media.DrawingBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle> con un modello creato da un <xref:System.Windows.Media.GeometryDrawing>. Questo esempio produce il seguente output:  
  
 ![DrawingBrush affiancato](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Oggetto GeometryDrawing usato con un oggetto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 Il <xref:System.Windows.Media.DrawingBrush> classe offre un'ampia gamma di opzioni per l'adattamento e affiancamento del contenuto. Per altre informazioni sulle <xref:System.Windows.Media.DrawingBrush>, vedere la [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md) Panoramica.  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Eseguire il rendering di un disegno con un oggetto Visual  
 Oggetto <xref:System.Windows.Media.DrawingVisual> è un tipo di oggetto visual progettato per eseguire il rendering di un disegno. Lavorare direttamente a livello visivo è un'opportunità per gli sviluppatori che desiderano creare un ambiente grafico altamente personalizzato, ma questo argomento non viene descritto in questa panoramica. Per altre informazioni, vedere [Utilizzo degli oggetti DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>Oggetti DrawingContext  
 Il <xref:System.Windows.Media.DrawingContext> classe consente di popolare un <xref:System.Windows.Media.Visual> o un <xref:System.Windows.Media.Drawing> con contenuto visivo. Molti oggetti grafici di livello inferiore di questo utilizzano un <xref:System.Windows.Media.DrawingContext> perché descrive il contenuto del grafico in modo molto efficiente.  
  
 Anche se il <xref:System.Windows.Media.DrawingContext> metodi di disegno simile ai metodi di disegno del <xref:System.Drawing.Graphics?displayProperty=nameWithType> tipo, sono effettivamente molto diversi. <xref:System.Windows.Media.DrawingContext> viene usato con un sistema di grafica in modalità differita, mentre il <xref:System.Drawing.Graphics?displayProperty=nameWithType> tipo viene usato con un sistema di grafica in modalità immediata. Quando si usa una <xref:System.Windows.Media.DrawingContext> comandi di disegno dell'oggetto, si archivia un set di istruzioni di rendering (anche se il meccanismo di archiviazione esatta dipende dal tipo di oggetto che fornisce il <xref:System.Windows.Media.DrawingContext>) che verrà successivamente utilizzata per la grafica di sistema; è non si disegna sullo schermo in tempo reale. Per altre informazioni su come funziona il sistema di grafica Windows Presentation Foundation (WPF), vedere la [Cenni preliminari sul Rendering WPF grafica](wpf-graphics-rendering-overview.md).  
  
 Mai direttamente creare un'istanza di un <xref:System.Windows.Media.DrawingContext>; tuttavia, è possibile, acquisire un contesto di disegno tramite determinati metodi, ad esempio <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> e <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Enumerare il contenuto di un oggetto Visual  
 Oltre agli altri utilizzi <xref:System.Windows.Media.Drawing> gli oggetti offrono anche un modello a oggetti per l'enumerazione del contenuto di un <xref:System.Windows.Media.Visual>.  
  
 L'esempio seguente usa il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> metodo per recuperare il <xref:System.Windows.Media.DrawingGroup> pari a un <xref:System.Windows.Media.Visual> ed enumerarlo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [Grafica bidimensionale e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Procedure relative alle proprietà](drawings-how-to-topics.md)
