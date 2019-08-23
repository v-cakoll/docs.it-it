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
ms.openlocfilehash: d739865a692fa5ef448eba91369015580e5eda97
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916305"
---
# <a name="drawing-objects-overview"></a>Cenni preliminari sugli oggetti Drawing
In questo argomento <xref:System.Windows.Media.Drawing> vengono introdotti gli oggetti e viene descritto come utilizzarli per creare in modo efficiente forme, bitmap, testo e supporti. Usare <xref:System.Windows.Media.Drawing> gli oggetti quando si crea clipart, disegnarli <xref:System.Windows.Media.DrawingBrush>con o usare <xref:System.Windows.Media.Visual> oggetti.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Definizione di oggetto Drawing  
 <xref:System.Windows.Media.Drawing> Oggetto che descrive il contenuto visibile, ad esempio una forma, una bitmap, un video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
- <xref:System.Windows.Media.GeometryDrawing>: Disegna una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>: Disegna un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>: Disegna il testo.  
  
- <xref:System.Windows.Media.VideoDrawing>: Riproduce un file audio o video.  
  
- <xref:System.Windows.Media.DrawingGroup>: Disegna altri disegni. Usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 <xref:System.Windows.Media.Drawing>gli oggetti sono versatili; è possibile utilizzare un <xref:System.Windows.Media.Drawing> oggetto in molti modi.  
  
- È possibile visualizzarlo come immagine usando un <xref:System.Windows.Media.DrawingImage> oggetto e un <xref:System.Windows.Controls.Image> controllo.  
  
- È possibile usarlo con un <xref:System.Windows.Media.DrawingBrush> oggetto per disegnare un oggetto, ad esempio <xref:System.Windows.Controls.Page.Background%2A> di un <xref:System.Windows.Controls.Page>oggetto.  
  
- È possibile usarlo per descrivere l'aspetto di un <xref:System.Windows.Media.DrawingVisual>oggetto.  
  
- È possibile usarlo per enumerare il contenuto di <xref:System.Windows.Media.Visual>un oggetto.  
  
 WPF fornisce altri tipi di oggetti che consentono di disegnare forme, bitmap, testo e contenuti multimediali. Ad esempio, è anche possibile usare <xref:System.Windows.Shapes.Shape> gli oggetti per creare forme e il <xref:System.Windows.Controls.MediaElement> controllo fornisce un altro modo per aggiungere video all'applicazione. Quindi, quando è consigliabile <xref:System.Windows.Media.Drawing> usare gli oggetti? Quando è possibile sacrificare le funzionalità a livello di Framework per ottenere vantaggi in <xref:System.Windows.Freezable> termini di prestazioni o quando sono necessarie funzionalità. Poiché <xref:System.Windows.Media.Drawing> gli oggetti non supportano il [layout](../advanced/layout.md), l'input e lo stato attivo, offrono vantaggi a livello di prestazioni che li rendono ideali per la descrizione di sfondi, ClipArt e per il disegno <xref:System.Windows.Media.Visual> di basso livello con oggetti.  
  
 Poiché si tratta di un <xref:System.Windows.Freezable> oggetto tipo <xref:System.Windows.Media.Drawing> , gli oggetti ottengono diverse funzionalità speciali, tra cui i seguenti: possono essere dichiarati come [risorse](../advanced/xaml-resources.md), condivisi tra più oggetti, resi di sola lettura per migliorare le prestazioni, clonati e reso thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite dagli <xref:System.Windows.Freezable> oggetti, vedere Cenni preliminari sugli [oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Disegnare una forma  
 Per disegnare una forma, usare un oggetto <xref:System.Windows.Media.GeometryDrawing>. La <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> proprietà di un disegno di geometria descrive la forma da disegnare <xref:System.Windows.Media.GeometryDrawing.Brush%2A> , la relativa proprietà descrive il modo in cui deve essere disegnata l' <xref:System.Windows.Media.GeometryDrawing.Pen%2A> area interna della forma e la relativa proprietà descrive il modo in cui deve essere disegnata la struttura.  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.GeometryDrawing> un oggetto per disegnare una forma. La forma è descritta da un <xref:System.Windows.Media.GeometryGroup> oggetto e <xref:System.Windows.Media.EllipseGeometry> da due oggetti. L'interno della forma viene disegnato con un <xref:System.Windows.Media.LinearGradientBrush> oggetto e il contorno viene disegnato <xref:System.Windows.Media.Brushes.Black%2A> con un oggetto <xref:System.Windows.Media.Pen>.  
  
 Questo esempio crea quanto segue <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Per un esempio completo, vedere [Procedura: Creare un oggetto GeometryDrawing](how-to-create-a-geometrydrawing.md).  
  
 Altre <xref:System.Windows.Media.Geometry> classi, <xref:System.Windows.Media.PathGeometry> ad esempio, consentono di creare forme più complesse creando curve e archi. Per ulteriori informazioni sugli <xref:System.Windows.Media.Geometry> oggetti, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
 Per ulteriori informazioni su altri modi per disegnare forme che non utilizzano <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sulle forme e il disegno di base in WPF](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Disegnare un'immagine  
 Per creare un'immagine, è necessario usare <xref:System.Windows.Media.ImageDrawing>un oggetto. La <xref:System.Windows.Media.ImageDrawing> <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> proprietà di un oggetto descrive l'immagine da disegnare e la <xref:System.Windows.Media.ImageDrawing.Rect%2A> relativa proprietà definisce l'area in cui viene disegnata l'immagine.  
  
 L'esempio seguente disegna un'immagine in un rettangolo posizionata nel punto (75,75) vale a dire 100 x 100 pixel. Nella figura seguente viene illustrato <xref:System.Windows.Media.ImageDrawing> l'oggetto creato dall'esempio. È stato aggiunto un bordo grigio per visualizzare i limiti dell'oggetto <xref:System.Windows.Media.ImageDrawing>.  
  
 ![100 di 100 ImageDrawing disegnata a &#40;75, 75&#41; ](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing di 100 per 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Per altre informazioni sulle immagini, vedere [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Riprodurre contenuti multimediali (solo codice)  
  
> [!NOTE]
> Sebbene sia possibile dichiarare un <xref:System.Windows.Media.VideoDrawing> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile caricare e riprodurre i supporti solo usando il codice. Per riprodurre video in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], <xref:System.Windows.Controls.MediaElement> usare invece.  
  
 Per riprodurre un file audio o video, è possibile usare <xref:System.Windows.Media.VideoDrawing> un oggetto <xref:System.Windows.Media.MediaPlayer>e un oggetto. È possibile caricare e riprodurre contenuti multimediali in due modi diversi. Il primo consiste nell'usare un <xref:System.Windows.Media.MediaPlayer> oggetto e <xref:System.Windows.Media.VideoDrawing> un autonomo e il secondo modo consiste nel creare un oggetto <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> personalizzato da usare con e <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
> Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
 Per riprodurre supporti senza crearne di <xref:System.Windows.Media.MediaTimeline>personalizzati, seguire questa procedura.  
  
1. Creare un oggetto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Usare il <xref:System.Windows.Media.MediaPlayer.Open%2A> metodo per caricare il file multimediale.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Creare un oggetto <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Specificare le dimensioni e la posizione in cui creare i supporti impostando la <xref:System.Windows.Media.VideoDrawing.Rect%2A> proprietà dell'oggetto. <xref:System.Windows.Media.VideoDrawing>  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Impostare la <xref:System.Windows.Media.VideoDrawing.Player%2A> proprietà dell'oggetto <xref:System.Windows.Media.VideoDrawing> con l' <xref:System.Windows.Media.MediaPlayer> oggetto creato.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Utilizzare il <xref:System.Windows.Media.MediaPlayer.Play%2A> metodo <xref:System.Windows.Media.MediaPlayer> di per avviare la riproduzione dei supporti.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 Nell'esempio seguente vengono utilizzati <xref:System.Windows.Media.VideoDrawing> un oggetto <xref:System.Windows.Media.MediaPlayer> e un oggetto per riprodurre un file video una sola volta.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ottenere un controllo temporale aggiuntivo sui supporti, utilizzare un <xref:System.Windows.Media.MediaTimeline> oggetto con <xref:System.Windows.Media.MediaPlayer> gli <xref:System.Windows.Media.VideoDrawing> oggetti e. <xref:System.Windows.Media.MediaTimeline> Consente di specificare se il video deve essere ripetuto. Per usare un <xref:System.Windows.Media.MediaTimeline> con un <xref:System.Windows.Media.VideoDrawing>, seguire questa procedura:  
  
1. Dichiarare e <xref:System.Windows.Media.MediaTimeline> impostare i relativi comportamenti temporali.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Creare un <xref:System.Windows.Media.MediaClock> oggetto <xref:System.Windows.Media.MediaTimeline>da.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Creare un <xref:System.Windows.Media.MediaPlayer> oggetto e utilizzare <xref:System.Windows.Media.MediaClock> per impostarne <xref:System.Windows.Media.MediaPlayer.Clock%2A> la proprietà.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Creare un <xref:System.Windows.Media.VideoDrawing> oggetto e <xref:System.Windows.Media.MediaPlayer> assegnarlo alla <xref:System.Windows.Media.VideoDrawing.Player%2A> proprietà dell'oggetto <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.MediaTimeline> un oggetto <xref:System.Windows.Media.MediaPlayer> con un <xref:System.Windows.Media.VideoDrawing> oggetto e un oggetto per riprodurre un video ripetutamente.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Si noti che, quando si usa <xref:System.Windows.Media.MediaTimeline>un, si usa l' <xref:System.Windows.Media.Animation.ClockController> elemento interattivo restituito <xref:System.Windows.Media.Animation.Clock.Controller%2A> <xref:System.Windows.Media.MediaClock> dalla proprietà di per controllare la riproduzione dei supporti anziché i metodi interattivi di <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Creare testo  
 Per creare testo, usare un oggetto <xref:System.Windows.Media.GlyphRunDrawing> e un <xref:System.Windows.Media.GlyphRun>oggetto. Nell'esempio seguente viene usato <xref:System.Windows.Media.GlyphRunDrawing> un oggetto per creare il testo "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Un <xref:System.Windows.Media.GlyphRun> è un oggetto di basso livello destinato a essere utilizzato con scenari di presentazione e di stampa di documenti a formato fisso. Un modo più semplice per creare testo sullo schermo consiste nell'usare un oggetto <xref:System.Windows.Controls.Label> o un <xref:System.Windows.Controls.TextBlock>oggetto. Per ulteriori informazioni su <xref:System.Windows.Media.GlyphRun>, vedere l' [Introduzione all'oggetto GlyphRun e](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) Cenni preliminari sull'elemento Glyphs.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Disegni composti  
 Un <xref:System.Windows.Media.DrawingGroup> oggetto consente di combinare più disegni in un unico disegno composto. Utilizzando un <xref:System.Windows.Media.DrawingGroup>è possibile combinare forme, immagini e testo in un unico <xref:System.Windows.Media.Drawing> oggetto.  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.DrawingGroup> un oggetto per <xref:System.Windows.Media.GeometryDrawing> combinare due oggetti <xref:System.Windows.Media.ImageDrawing> e un oggetto. Questo esempio produce il seguente output:  
  
 ![Oggetto DrawingGroup con più disegni](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Disegno composto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Consente <xref:System.Windows.Media.DrawingGroup> inoltre di applicare al contenuto maschere di opacità, trasformazioni, effetti bitmap e altre operazioni. <xref:System.Windows.Media.DrawingGroup>le operazioni vengono applicate nell'ordine seguente: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>e quindi <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Nella figura seguente viene illustrato l'ordine in <xref:System.Windows.Media.DrawingGroup> cui vengono applicate le operazioni.  
  
 ![Ordine delle operazioni di DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Ordine delle operazioni DrawingGroup  
  
 Nella tabella seguente vengono descritte le proprietà che è possibile utilizzare per <xref:System.Windows.Media.DrawingGroup> modificare il contenuto di un oggetto.  
  
|Proprietà|Descrizione|Illustrazione|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Modifica l'opacità delle parti selezionate del <xref:System.Windows.Media.DrawingGroup> contenuto. Per un esempio, vedere [Procedura: Controllare l'opacità di un](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90))disegno.|![Oggetto DrawingGroup con una maschera di opacità](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Modifica in modo uniforme l'opacità del <xref:System.Windows.Media.DrawingGroup> contenuto. Utilizzare questa proprietà per rendere <xref:System.Windows.Media.Drawing> trasparente o parzialmente trasparente. Per un esempio, vedere [Procedura: Applicare una maschera di opacità a](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90))un disegno.|![Oggetto DrawingGroups con impostazioni di opacità diverse](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|<xref:System.Windows.Media.Effects.BitmapEffect> Applica<xref:System.Windows.Media.DrawingGroup> al contenuto. Per un esempio, vedere [Procedura: Applicare un oggetto BitmapEffect a un](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90))disegno.|![Oggetto DrawingGroup con BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Consente di <xref:System.Windows.Media.DrawingGroup> ritagliare il contenuto in un'area <xref:System.Windows.Media.Geometry>descritta utilizzando un. Per un esempio, vedere [Procedura: Ritagliare un](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) disegno.|![Oggetto DrawingGroup con area ritagliata definita](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Consente di bloccare i pixel indipendenti del dispositivo ai pixel del dispositivo lungo linee guida specificate. Questa proprietà è utile per garantire che il rendering degli elementi grafici dettagliati venga eseguito con precisione su schermi a DPI basso. Per un esempio, vedere [Procedura: Applicare un GuidelineSet a un disegno](how-to-apply-a-guidelineset-to-a-drawing.md).|![Oggetto DrawingGroup con e senza un GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Trasforma il <xref:System.Windows.Media.DrawingGroup> contenuto. Per un esempio, vedere [Procedura: Applicare una trasformazione a un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)).|![Oggetto DrawingGroup ruotato](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Visualizzare un disegno come immagine  
 Per visualizzare un <xref:System.Windows.Media.Drawing> oggetto con <xref:System.Windows.Controls.Image> un controllo, usare <xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Controls.Image.Source%2A> un oggetto <xref:System.Windows.Controls.Image> <xref:System.Windows.Media.DrawingImage> come<xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> oggetto del controllo e impostare la proprietà dell'oggetto sul disegno che si vuole visualizzare.  
  
 Nell'esempio seguente vengono utilizzati <xref:System.Windows.Media.DrawingImage> un oggetto <xref:System.Windows.Controls.Image> e un controllo per <xref:System.Windows.Media.GeometryDrawing>visualizzare un oggetto. Questo esempio produce il seguente output:  
  
 ![GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Oggetto DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Disegnare un oggetto con un oggetto  
 Un <xref:System.Windows.Media.DrawingBrush> è un tipo di pennello che disegna un'area con un oggetto Drawing. Può essere usato per disegnare quasi tutti gli oggetti grafici con un oggetto Drawing. La <xref:System.Windows.Media.Drawing> proprietà di un <xref:System.Windows.Media.DrawingBrush> oggetto descrive <xref:System.Windows.Media.DrawingBrush.Drawing%2A>la relativa. Per eseguire il <xref:System.Windows.Media.Drawing> rendering di <xref:System.Windows.Media.DrawingBrush>un oggetto con un oggetto, aggiungerlo al <xref:System.Windows.Media.Drawing> pennello utilizzando la proprietà del pennello e utilizzare il pennello per disegnare un oggetto grafico, ad esempio un controllo o un pannello.  
  
 Negli esempi seguenti viene usato <xref:System.Windows.Media.DrawingBrush> un oggetto per <xref:System.Windows.Shapes.Shape.Fill%2A> disegnare l' <xref:System.Windows.Shapes.Rectangle> oggetto di un oggetto con un <xref:System.Windows.Media.GeometryDrawing>criterio creato da un oggetto. Questo esempio produce il seguente output:  
  
 ![DrawingBrush affiancato](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Oggetto GeometryDrawing usato con un oggetto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 La <xref:System.Windows.Media.DrawingBrush> classe offre un'ampia gamma di opzioni per l'estensione e l'affiancamento del contenuto. Per altre informazioni su <xref:System.Windows.Media.DrawingBrush>, vedere Cenni preliminari sul [disegno con immagini, disegni e](painting-with-images-drawings-and-visuals.md) oggetti visivi.  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Eseguire il rendering di un disegno con un oggetto Visual  
 Un <xref:System.Windows.Media.DrawingVisual> è un tipo di oggetto visivo progettato per eseguire il rendering di un disegno. Lavorare direttamente a livello visivo è un'opportunità per gli sviluppatori che desiderano creare un ambiente grafico altamente personalizzato, ma questo argomento non viene descritto in questa panoramica. Per altre informazioni, vedere [Utilizzo degli oggetti DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>Oggetti DrawingContext  
 La <xref:System.Windows.Media.DrawingContext> classe consente di popolare un <xref:System.Windows.Media.Visual> oggetto o <xref:System.Windows.Media.Drawing> con contenuto visivo. Molti di questi oggetti grafici di basso livello usano <xref:System.Windows.Media.DrawingContext> un oggetto perché descrive il contenuto grafico in modo molto efficiente.  
  
 Sebbene i <xref:System.Windows.Media.DrawingContext> metodi <xref:System.Drawing.Graphics?displayProperty=nameWithType> di richiamo siano simili ai metodi di estrazione del tipo, sono in realtà molto diversi. <xref:System.Windows.Media.DrawingContext>viene usato con un sistema grafico in modalità mantenuta, <xref:System.Drawing.Graphics?displayProperty=nameWithType> mentre il tipo viene usato con un sistema di grafica in modalità immediata. Quando si usano i <xref:System.Windows.Media.DrawingContext> comandi di progetto di un oggetto, si archivia effettivamente un set di istruzioni per il rendering (sebbene il meccanismo di archiviazione esatto dipenda dal tipo di <xref:System.Windows.Media.DrawingContext>oggetto che fornisce) che verrà usato in un secondo momento dal sistema grafico; non vengono disegnati sullo schermo in tempo reale. Per ulteriori informazioni sul funzionamento del sistema grafico Windows Presentation Foundation (WPF), vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).  
  
 Non è mai possibile creare direttamente <xref:System.Windows.Media.DrawingContext>un'istanza di. è tuttavia possibile acquisire un contesto di disegno da determinati metodi, <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> ad <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>esempio e.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Enumerare il contenuto di un oggetto Visual  
 Oltre agli altri utilizzi, <xref:System.Windows.Media.Drawing> gli oggetti forniscono anche un modello a oggetti per l'enumerazione del contenuto di un <xref:System.Windows.Media.Visual>oggetto.  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> il metodo per recuperare <xref:System.Windows.Media.DrawingGroup> il valore di <xref:System.Windows.Media.Visual> un oggetto ed enumerarlo.  
  
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
