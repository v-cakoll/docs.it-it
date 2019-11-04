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
ms.openlocfilehash: d4527c331308ff6cd517705212e09428216d2378
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459737"
---
# <a name="drawing-objects-overview"></a>Cenni preliminari sugli oggetti Drawing
In questo argomento vengono introdotti <xref:System.Windows.Media.Drawing> oggetti e viene descritto come utilizzarli per creare in modo efficiente forme, bitmap, testo e supporti. Utilizzare <xref:System.Windows.Media.Drawing> oggetti quando si crea clipart, si disegna con una <xref:System.Windows.Media.DrawingBrush>oppure si utilizzano <xref:System.Windows.Media.Visual> oggetti.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Definizione di oggetto Drawing  
 Un oggetto <xref:System.Windows.Media.Drawing> descrive il contenuto visibile, ad esempio una forma, una bitmap, un video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
- <xref:System.Windows.Media.GeometryDrawing>: disegna una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>: disegna un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>: disegna il testo.  
  
- <xref:System.Windows.Media.VideoDrawing>: riproduce un file audio o video.  
  
- <xref:System.Windows.Media.DrawingGroup>: disegna altri disegni. È possibile usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 gli oggetti <xref:System.Windows.Media.Drawing> sono versatili; è possibile usare un oggetto <xref:System.Windows.Media.Drawing> in molti modi.  
  
- È possibile visualizzarlo come immagine utilizzando un <xref:System.Windows.Media.DrawingImage> e un controllo <xref:System.Windows.Controls.Image>.  
  
- È possibile usarlo con un <xref:System.Windows.Media.DrawingBrush> per disegnare un oggetto, ad esempio il <xref:System.Windows.Controls.Page.Background%2A> di un <xref:System.Windows.Controls.Page>.  
  
- È possibile usarlo per descrivere l'aspetto di un <xref:System.Windows.Media.DrawingVisual>.  
  
- È possibile usarlo per enumerare il contenuto di un <xref:System.Windows.Media.Visual>.  
  
 WPF fornisce altri tipi di oggetti che consentono di disegnare forme, bitmap, testo e contenuti multimediali. Ad esempio, è anche possibile usare <xref:System.Windows.Shapes.Shape> oggetti per creare forme e il controllo <xref:System.Windows.Controls.MediaElement> fornisce un altro modo per aggiungere video all'applicazione. Quando è necessario usare <xref:System.Windows.Media.Drawing> oggetti? Quando è possibile sacrificare le funzionalità a livello di Framework per ottenere vantaggi in termini di prestazioni o quando è necessario <xref:System.Windows.Freezable> funzionalità. Poiché gli oggetti <xref:System.Windows.Media.Drawing> non supportano il [layout](../advanced/layout.md), l'input e lo stato attivo, offrono vantaggi a livello di prestazioni che li rendono ideali per la descrizione di sfondi, ClipArt e per il disegno di basso livello con <xref:System.Windows.Media.Visual> oggetti.  
  
 Poiché si tratta di un tipo <xref:System.Windows.Freezable> oggetto, <xref:System.Windows.Media.Drawing> oggetti ottengono diverse funzionalità speciali, tra cui le seguenti: possono essere dichiarate come [risorse](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivise tra più oggetti, rese di sola lettura per migliorare le prestazioni, clonate e apportate thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite dagli oggetti <xref:System.Windows.Freezable>, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Disegnare una forma  
 Per disegnare una forma, utilizzare un <xref:System.Windows.Media.GeometryDrawing>. La proprietà <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> di un disegno Geometry descrive la forma da disegnare, la relativa proprietà <xref:System.Windows.Media.GeometryDrawing.Brush%2A> descrive il modo in cui deve essere disegnata l'area interna della forma e la relativa proprietà <xref:System.Windows.Media.GeometryDrawing.Pen%2A> descrive il modo in cui deve essere disegnata la struttura.  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.GeometryDrawing> per disegnare una forma. La forma è descritta da un <xref:System.Windows.Media.GeometryGroup> e due <xref:System.Windows.Media.EllipseGeometry> oggetti. L'interno della forma viene disegnato con un <xref:System.Windows.Media.LinearGradientBrush> e il contorno viene disegnato con un <xref:System.Windows.Media.Pen><xref:System.Windows.Media.Brushes.Black%2A>.  
  
 In questo esempio viene creata la <xref:System.Windows.Media.GeometryDrawing>seguente.  
  
 ![Oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Per un esempio completo, vedere [Procedura: Creare un oggetto GeometryDrawing](how-to-create-a-geometrydrawing.md).  
  
 Altre <xref:System.Windows.Media.Geometry> classi, ad esempio <xref:System.Windows.Media.PathGeometry> consentono di creare forme più complesse creando curve e archi. Per ulteriori informazioni sugli oggetti <xref:System.Windows.Media.Geometry>, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
 Per ulteriori informazioni su altri modi per disegnare forme che non utilizzano oggetti <xref:System.Windows.Media.Drawing>, vedere [Cenni preliminari sulle forme e il disegno di base in WPF](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Disegnare un'immagine  
 Per creare un'immagine, usare un <xref:System.Windows.Media.ImageDrawing>. La proprietà <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> di un oggetto <xref:System.Windows.Media.ImageDrawing> descrive l'immagine da disegnare e la relativa proprietà <xref:System.Windows.Media.ImageDrawing.Rect%2A> definisce l'area in cui viene disegnata l'immagine.  
  
 L'esempio seguente disegna un'immagine in un rettangolo posizionata nel punto (75,75) vale a dire 100 x 100 pixel. Nella figura seguente viene illustrato il <xref:System.Windows.Media.ImageDrawing> creato dall'esempio. È stato aggiunto un bordo grigio per visualizzare i limiti del <xref:System.Windows.Media.ImageDrawing>.  
  
 ![Oggetto ImageDrawing di 100 x 100 disegnato in corrispondenza di &#40;75,75&#41;](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing di 100 per 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Per altre informazioni sulle immagini, vedere [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Riprodurre contenuti multimediali (solo codice)  
  
> [!NOTE]
> Sebbene sia possibile dichiarare un <xref:System.Windows.Media.VideoDrawing> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile caricare e riprodurre i supporti solo usando il codice. Per riprodurre video in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], usare invece una <xref:System.Windows.Controls.MediaElement>.  
  
 Per riprodurre un file audio o video, usare un <xref:System.Windows.Media.VideoDrawing> e un <xref:System.Windows.Media.MediaPlayer>. È possibile caricare e riprodurre contenuti multimediali in due modi diversi. Il primo consiste nell'utilizzare una <xref:System.Windows.Media.MediaPlayer> e una <xref:System.Windows.Media.VideoDrawing> da soli e il secondo modo consiste nel creare <xref:System.Windows.Media.MediaTimeline> personalizzati da utilizzare con i <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
> Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
 Per riprodurre file multimediali senza creare <xref:System.Windows.Media.MediaTimeline>personalizzati, seguire questa procedura.  
  
1. Creare un oggetto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Usare il metodo <xref:System.Windows.Media.MediaPlayer.Open%2A> per caricare il file multimediale.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Creare un oggetto <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Specificare le dimensioni e la posizione in cui creare i supporti impostando la proprietà <xref:System.Windows.Media.VideoDrawing.Rect%2A> della <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Impostare la proprietà <xref:System.Windows.Media.VideoDrawing.Player%2A> della <xref:System.Windows.Media.VideoDrawing> con la <xref:System.Windows.Media.MediaPlayer> creata.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Usare il metodo <xref:System.Windows.Media.MediaPlayer.Play%2A> della <xref:System.Windows.Media.MediaPlayer> per avviare la riproduzione del supporto.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 Nell'esempio seguente vengono usati una <xref:System.Windows.Media.VideoDrawing> e un <xref:System.Windows.Media.MediaPlayer> per riprodurre un file video una sola volta.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ottenere un controllo temporale aggiuntivo sui supporti, utilizzare una <xref:System.Windows.Media.MediaTimeline> con gli oggetti <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing>. Il <xref:System.Windows.Media.MediaTimeline> consente di specificare se il video deve essere ripetuto. Per usare un <xref:System.Windows.Media.MediaTimeline> con una <xref:System.Windows.Media.VideoDrawing>, seguire questa procedura:  
  
1. Dichiarare il <xref:System.Windows.Media.MediaTimeline> e impostarne i comportamenti temporali.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Creare una <xref:System.Windows.Media.MediaClock> dalla <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Creare una <xref:System.Windows.Media.MediaPlayer> e usare il <xref:System.Windows.Media.MediaClock> per impostare la relativa proprietà <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Creare una <xref:System.Windows.Media.VideoDrawing> e assegnare la <xref:System.Windows.Media.MediaPlayer> alla proprietà <xref:System.Windows.Media.VideoDrawing.Player%2A> della <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.MediaTimeline> con una <xref:System.Windows.Media.MediaPlayer> e un <xref:System.Windows.Media.VideoDrawing> per riprodurre un video ripetutamente.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Si noti che, quando si usa un <xref:System.Windows.Media.MediaTimeline>, si usa il <xref:System.Windows.Media.Animation.ClockController> interattivo restituito dalla proprietà <xref:System.Windows.Media.Animation.Clock.Controller%2A> della <xref:System.Windows.Media.MediaClock> per controllare la riproduzione dei supporti anziché i metodi interattivi di <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Creare testo  
 Per creare testo, usare un <xref:System.Windows.Media.GlyphRunDrawing> e un <xref:System.Windows.Media.GlyphRun>. Nell'esempio seguente viene usato un <xref:System.Windows.Media.GlyphRunDrawing> per creare il testo "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Un <xref:System.Windows.Media.GlyphRun> è un oggetto di basso livello destinato all'uso con scenari di presentazione e stampa di documenti a formato fisso. Un modo più semplice per creare testo sullo schermo consiste nell'usare un <xref:System.Windows.Controls.Label> o una <xref:System.Windows.Controls.TextBlock>. Per ulteriori informazioni su <xref:System.Windows.Media.GlyphRun>, vedere [Introduzione all'oggetto GlyphRun e](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) Cenni preliminari sull'elemento Glyphs.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Disegni composti  
 Un <xref:System.Windows.Media.DrawingGroup> consente di combinare più disegni in un unico disegno composto. Utilizzando un <xref:System.Windows.Media.DrawingGroup>è possibile combinare forme, immagini e testo in un singolo oggetto <xref:System.Windows.Media.Drawing>.  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.DrawingGroup> per combinare due oggetti <xref:System.Windows.Media.GeometryDrawing> e un oggetto <xref:System.Windows.Media.ImageDrawing>. Questo esempio produce il seguente output:  
  
 ![Oggetto DrawingGroup con più disegni](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Disegno composto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Un <xref:System.Windows.Media.DrawingGroup> consente inoltre di applicare maschere di opacità, trasformazioni, effetti bitmap e altre operazioni al relativo contenuto. <xref:System.Windows.Media.DrawingGroup> operazioni vengono applicate nell'ordine seguente: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, quindi <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Nella figura seguente viene illustrato l'ordine in cui vengono applicate <xref:System.Windows.Media.DrawingGroup> operazioni.  
  
 ![Ordine delle operazioni DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Ordine delle operazioni DrawingGroup  
  
 Nella tabella seguente vengono descritte le proprietà che è possibile utilizzare per modificare il contenuto di un oggetto <xref:System.Windows.Media.DrawingGroup>.  
  
|proprietà|Descrizione|Illustrazione|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Modifica l'opacità delle parti selezionate del contenuto del <xref:System.Windows.Media.DrawingGroup>. Per un esempio, vedere [Procedura: Controllare l'opacità di un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![Oggetto DrawingGroup con maschera di opacità](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Modifica in modo uniforme l'opacità del contenuto del <xref:System.Windows.Media.DrawingGroup>. Utilizzare questa proprietà per rendere trasparente o parzialmente trasparente un <xref:System.Windows.Media.Drawing>. Per un esempio, vedere [How to: Apply an Opacity Mask to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)) (Procedura: Applicare una maschera di opacità a un disegno).|![DrawingGroup con impostazioni di opacità diverse](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Applica una <xref:System.Windows.Media.Effects.BitmapEffect> al contenuto del <xref:System.Windows.Media.DrawingGroup>. Per un esempio, vedere [Procedura: Applicare un BitmapEffect a un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![DrawingGroup con BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Consente di ritagliare il contenuto del <xref:System.Windows.Media.DrawingGroup> in un'area descritta utilizzando una <xref:System.Windows.Media.Geometry>. Per un esempio, vedere [Procedura: Ritagliare un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)).|![DrawingGroup con un'area di ritaglio definita](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Consente di bloccare i pixel indipendenti del dispositivo ai pixel del dispositivo lungo linee guida specificate. Questa proprietà è utile per garantire che il rendering degli elementi grafici dettagliati venga eseguito con precisione su schermi a DPI basso. Per un esempio, vedere [Procedura: Applicare un GuidelineSet a un disegno](how-to-apply-a-guidelineset-to-a-drawing.md).|![Oggetto DrawingGroup con e senza un insieme di istruzioni](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Trasforma il contenuto del <xref:System.Windows.Media.DrawingGroup>. Per un esempio, vedere [How to: Apply a Transform to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)) (Procedura: Applicare una trasformazione a un disegno).|![Oggetto DrawingGroup ruotato](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Visualizzare un disegno come immagine  
 Per visualizzare un <xref:System.Windows.Media.Drawing> con un controllo <xref:System.Windows.Controls.Image>, utilizzare un <xref:System.Windows.Media.DrawingImage> come <xref:System.Windows.Controls.Image.Source%2A> del controllo <xref:System.Windows.Controls.Image> e impostare la proprietà <xref:System.Windows.Media.DrawingImage> dell'oggetto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> sul disegno da visualizzare.  
  
 Nell'esempio seguente vengono utilizzati un <xref:System.Windows.Media.DrawingImage> e un controllo <xref:System.Windows.Controls.Image> per visualizzare un <xref:System.Windows.Media.GeometryDrawing>. Questo esempio produce il seguente output:  
  
 ![Oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Oggetto DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Disegnare un oggetto con un oggetto  
 Un <xref:System.Windows.Media.DrawingBrush> è un tipo di pennello che disegna un'area con un oggetto Drawing. Può essere usato per disegnare quasi tutti gli oggetti grafici con un oggetto Drawing. La proprietà <xref:System.Windows.Media.Drawing> di un <xref:System.Windows.Media.DrawingBrush> ne descrive il <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Per eseguire il rendering di un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Media.DrawingBrush>, aggiungerlo al pennello utilizzando la proprietà <xref:System.Windows.Media.Drawing> del pennello e utilizzare il pennello per disegnare un oggetto grafico, ad esempio un controllo o un pannello.  
  
 Negli esempi seguenti viene usato un <xref:System.Windows.Media.DrawingBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle> con un modello creato da un <xref:System.Windows.Media.GeometryDrawing>. Questo esempio produce il seguente output:  
  
 ![Oggetto DrawingBrush affiancato](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Oggetto GeometryDrawing usato con un oggetto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 La classe <xref:System.Windows.Media.DrawingBrush> offre un'ampia gamma di opzioni per l'estensione e l'affiancamento del contenuto. Per ulteriori informazioni su <xref:System.Windows.Media.DrawingBrush>, vedere Cenni preliminari sul [disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md) .  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Eseguire il rendering di un disegno con un oggetto Visual  
 Un <xref:System.Windows.Media.DrawingVisual> è un tipo di oggetto visivo progettato per eseguire il rendering di un disegno. Lavorare direttamente a livello visivo è un'opportunità per gli sviluppatori che desiderano creare un ambiente grafico altamente personalizzato, ma questo argomento non viene descritto in questa panoramica. Per altre informazioni, vedere [Utilizzo degli oggetti DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>Oggetti DrawingContext  
 La classe <xref:System.Windows.Media.DrawingContext> consente di popolare una <xref:System.Windows.Media.Visual> o una <xref:System.Windows.Media.Drawing> con contenuto visivo. Molti di questi oggetti grafici di basso livello usano un <xref:System.Windows.Media.DrawingContext> perché descrivono contenuti grafici in modo molto efficiente.  
  
 Sebbene i <xref:System.Windows.Media.DrawingContext> metodi di richiamo siano simili ai metodi di estrazione del tipo di <xref:System.Drawing.Graphics?displayProperty=nameWithType>, sono in realtà molto diversi. <xref:System.Windows.Media.DrawingContext> viene usato con un sistema grafico in modalità mantenuta, mentre il tipo di <xref:System.Drawing.Graphics?displayProperty=nameWithType> viene usato con un sistema di grafica in modalità immediata. Quando si usano i comandi di progetto di un oggetto <xref:System.Windows.Media.DrawingContext>, si archivia effettivamente un set di istruzioni per il rendering (sebbene il meccanismo di archiviazione esatto dipenda dal tipo di oggetto che fornisce la <xref:System.Windows.Media.DrawingContext>) che verrà usato successivamente dal sistema grafico; non si sta disegnando sullo schermo in tempo reale. Per ulteriori informazioni sul funzionamento del sistema grafico Windows Presentation Foundation (WPF), vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).  
  
 Non è mai possibile creare direttamente un'istanza di un <xref:System.Windows.Media.DrawingContext>; è tuttavia possibile acquisire un contesto di disegno da determinati metodi, ad esempio <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> e <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Enumerare il contenuto di un oggetto Visual  
 Oltre agli altri utilizzi, <xref:System.Windows.Media.Drawing> oggetti forniscono anche un modello a oggetti per l'enumerazione del contenuto di un <xref:System.Windows.Media.Visual>.  
  
 Nell'esempio seguente viene usato il metodo <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> per recuperare il valore <xref:System.Windows.Media.DrawingGroup> di un <xref:System.Windows.Media.Visual> ed enumerarlo.  
  
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
