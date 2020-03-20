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
ms.openlocfilehash: 7a5d00eb2fb7c66e5e42d40893806e13717e1d2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186531"
---
# <a name="drawing-objects-overview"></a>Cenni preliminari sugli oggetti Drawing
In questo <xref:System.Windows.Media.Drawing> argomento vengono presentati oggetti e viene descritto come utilizzarli per disegnare in modo efficiente forme, bitmap, testo ed elementi multimediali. Utilizzare <xref:System.Windows.Media.Drawing> gli oggetti quando si creano <xref:System.Windows.Media.DrawingBrush>ClipArt, si disegna con un oggetto o si utilizzano <xref:System.Windows.Media.Visual> gli oggetti.  

<a name="whatisadrawingsection"></a>
## <a name="what-is-a-drawing-object"></a>Definizione di oggetto Drawing  
 Un <xref:System.Windows.Media.Drawing> oggetto descrive il contenuto visibile, ad esempio una forma, una bitmap, un video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
- <xref:System.Windows.Media.GeometryDrawing>– Disegna una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>– Disegna un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>– Disegna il testo.  
  
- <xref:System.Windows.Media.VideoDrawing>– Riproduce un file audio o video.  
  
- <xref:System.Windows.Media.DrawingGroup>– Disegna altri disegni. È possibile usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 <xref:System.Windows.Media.Drawing>gli oggetti sono versatili; ci sono molti modi <xref:System.Windows.Media.Drawing> per utilizzare un oggetto.  
  
- È possibile visualizzarla come immagine <xref:System.Windows.Media.DrawingImage> utilizzando <xref:System.Windows.Controls.Image> un controllo e un controllo .  
  
- È possibile utilizzarlo <xref:System.Windows.Media.DrawingBrush> con un oggetto per <xref:System.Windows.Controls.Page.Background%2A> disegnare <xref:System.Windows.Controls.Page>un oggetto, ad esempio il di un oggetto .  
  
- È possibile utilizzarlo per descrivere <xref:System.Windows.Media.DrawingVisual>l'aspetto di un file .  
  
- È possibile utilizzarlo per enumerare il contenuto di un <xref:System.Windows.Media.Visual>oggetto .  
  
 WPF fornisce altri tipi di oggetti che consentono di disegnare forme, bitmap, testo e contenuti multimediali. Ad esempio, è <xref:System.Windows.Shapes.Shape> anche possibile utilizzare gli <xref:System.Windows.Controls.MediaElement> oggetti per disegnare forme e il controllo fornisce un altro modo per aggiungere video all'applicazione. Quindi, quando <xref:System.Windows.Media.Drawing> si dovrebbe usare gli oggetti? Quando è possibile sacrificare le funzionalità a <xref:System.Windows.Freezable> livello di framework per ottenere vantaggi in termini di prestazioni o quando sono necessarie funzionalità. Poiché <xref:System.Windows.Media.Drawing> gli oggetti non supportano [il layout,](../advanced/layout.md)l'input e lo stato attivo, offrono vantaggi in <xref:System.Windows.Media.Visual> termini di prestazioni che li rendono ideali per la descrizione di sfondi, ClipArt e per il disegno di basso livello con gli oggetti.  
  
 Poiché sono <xref:System.Windows.Freezable> un <xref:System.Windows.Media.Drawing> oggetto di tipo, gli oggetti ottengono diverse funzionalità speciali, tra cui le seguenti: possono essere dichiarati come [risorse](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivisi tra più oggetti, resi di sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per ulteriori informazioni sulle diverse <xref:System.Windows.Freezable> funzionalità fornite dagli oggetti, vedere Cenni preliminari sugli [oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>
## <a name="draw-a-shape"></a>Disegnare una forma  
 Per disegnare una forma, <xref:System.Windows.Media.GeometryDrawing>utilizzare un file . La <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> proprietà di un disegno geometrico descrive <xref:System.Windows.Media.GeometryDrawing.Brush%2A> la forma da disegnare, la relativa proprietà descrive <xref:System.Windows.Media.GeometryDrawing.Pen%2A> come deve essere disegnato l'interno della forma e la relativa proprietà descrive come deve essere disegnato il contorno.  
  
 Nell'esempio seguente <xref:System.Windows.Media.GeometryDrawing> viene utilizzato un oggetto per disegnare una forma. La forma è <xref:System.Windows.Media.GeometryGroup> descritta <xref:System.Windows.Media.EllipseGeometry> da a e due oggetti. L'interno della forma è <xref:System.Windows.Media.LinearGradientBrush> dipinto con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>e il suo contorno è disegnato con un .  
  
 In questo esempio <xref:System.Windows.Media.GeometryDrawing>viene creato il metodo .  
  
 ![Oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Per un esempio completo, vedere [Procedura: Creare un oggetto GeometryDrawing](how-to-create-a-geometrydrawing.md).  
  
 Altre <xref:System.Windows.Media.Geometry> classi, <xref:System.Windows.Media.PathGeometry> ad esempio consentono di creare forme più complesse mediante la creazione di curve e archi. Per ulteriori <xref:System.Windows.Media.Geometry> informazioni sugli oggetti, vedere Cenni preliminari sulla [geometria](geometry-overview.md).  
  
 Per altre informazioni su altri modi per <xref:System.Windows.Media.Drawing> disegnare forme che non utilizzano oggetti, vedere Cenni preliminari sulle forme e sul [disegno di base in WPF.](shapes-and-basic-drawing-in-wpf-overview.md)  
  
<a name="drawingimagessection"></a>
## <a name="draw-an-image"></a>Disegnare un'immagine  
 Per disegnare un'immagine, <xref:System.Windows.Media.ImageDrawing>utilizzare un file . La <xref:System.Windows.Media.ImageDrawing> proprietà <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> di un oggetto descrive l'immagine da disegnare e la relativa <xref:System.Windows.Media.ImageDrawing.Rect%2A> proprietà definisce l'area in cui viene disegnata l'immagine.  
  
 L'esempio seguente disegna un'immagine in un rettangolo posizionata nel punto (75,75) vale a dire 100 x 100 pixel. Nella figura seguente <xref:System.Windows.Media.ImageDrawing> viene illustrato il creato dall'esempio. È stato aggiunto un bordo grigio <xref:System.Windows.Media.ImageDrawing>per mostrare i limiti del file .  
  
 ![Oggetto ImageDrawing di 100 x 100 disegnato in corrispondenza di &#40;75,75&#41;](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing di 100 per 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Per altre informazioni sulle immagini, vedere [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md).  
  
<a name="playmedia"></a>
## <a name="play-media-code-only"></a>Riprodurre contenuti multimediali (solo codice)  
  
> [!NOTE]
> Sebbene sia <xref:System.Windows.Media.VideoDrawing> possibile [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]dichiarare un oggetto in , è possibile caricare e riprodurre solo i relativi file multimediali utilizzando il codice. Per riprodurre [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]il <xref:System.Windows.Controls.MediaElement> video in , utilizzare invece un.  
  
 Per riprodurre un file audio <xref:System.Windows.Media.VideoDrawing> o <xref:System.Windows.Media.MediaPlayer>video, utilizzare un file . È possibile caricare e riprodurre contenuti multimediali in due modi diversi. Il primo è <xref:System.Windows.Media.MediaPlayer> quello <xref:System.Windows.Media.VideoDrawing> di utilizzare a e a da <xref:System.Windows.Media.MediaTimeline> soli, e <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing>il secondo modo è quello di creare il proprio da utilizzare con il e .  
  
> [!NOTE]
> Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
 Per riprodurre contenuti <xref:System.Windows.Media.MediaTimeline>multimediali senza creare propri, eseguire la procedura seguente.  
  
1. Creare un oggetto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Utilizzare <xref:System.Windows.Media.MediaPlayer.Open%2A> il metodo per caricare il file multimediale.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Creare un oggetto <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Specificare le dimensioni e la posizione <xref:System.Windows.Media.VideoDrawing.Rect%2A> in <xref:System.Windows.Media.VideoDrawing>cui disegnare il supporto impostando la proprietà dell'oggetto .  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Impostare <xref:System.Windows.Media.VideoDrawing.Player%2A> la <xref:System.Windows.Media.VideoDrawing> proprietà <xref:System.Windows.Media.MediaPlayer> dell'oggetto con l'utente creato.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Utilizzare <xref:System.Windows.Media.MediaPlayer.Play%2A> il metodo <xref:System.Windows.Media.MediaPlayer> di per avviare la riproduzione del file multimediale.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 L'esempio seguente <xref:System.Windows.Media.VideoDrawing> usa <xref:System.Windows.Media.MediaPlayer> a e a per riprodurre un file video una sola volta.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ottenere un ulteriore controllo <xref:System.Windows.Media.MediaTimeline> della <xref:System.Windows.Media.MediaPlayer> temporizzazione sul supporto, utilizzare un oggetto con gli oggetti e <xref:System.Windows.Media.VideoDrawing> . Consente <xref:System.Windows.Media.MediaTimeline> di specificare se il video deve essere ripetuto. Per utilizzare <xref:System.Windows.Media.MediaTimeline> a <xref:System.Windows.Media.VideoDrawing>con un , attenersi alla seguente procedura:  
  
1. Dichiarare <xref:System.Windows.Media.MediaTimeline> il e impostare i relativi comportamenti di temporizzazione.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Creare <xref:System.Windows.Media.MediaClock> un <xref:System.Windows.Media.MediaTimeline>dal file .  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Creare <xref:System.Windows.Media.MediaPlayer> un e <xref:System.Windows.Media.MediaClock> utilizzare <xref:System.Windows.Media.MediaPlayer.Clock%2A> il per impostare la relativa proprietà.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Creare <xref:System.Windows.Media.VideoDrawing> a e <xref:System.Windows.Media.MediaPlayer> assegnare l'oggetto <xref:System.Windows.Media.VideoDrawing.Player%2A> alla proprietà del <xref:System.Windows.Media.VideoDrawing>file .  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 L'esempio seguente <xref:System.Windows.Media.MediaTimeline> usa <xref:System.Windows.Media.MediaPlayer> un <xref:System.Windows.Media.VideoDrawing> con a e a per riprodurre ripetutamente un video.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Si noti che, <xref:System.Windows.Media.MediaTimeline>quando si <xref:System.Windows.Media.Animation.ClockController> utilizza un <xref:System.Windows.Media.Animation.Clock.Controller%2A> oggetto , <xref:System.Windows.Media.MediaClock> si utilizza l'oggetto restituito <xref:System.Windows.Media.MediaPlayer>dalla proprietà dell'oggetto per controllare la riproduzione multimediale anziché i metodi interattivi di .  
  
<a name="drawtext"></a>
## <a name="draw-text"></a>Creare testo  
 Per disegnare il testo, utilizzare a <xref:System.Windows.Media.GlyphRunDrawing> e un <xref:System.Windows.Media.GlyphRun>file . Nell'esempio seguente <xref:System.Windows.Media.GlyphRunDrawing> viene utilizzato un per disegnare il testo "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 A <xref:System.Windows.Media.GlyphRun> è un oggetto di basso livello destinato all'utilizzo con scenari di presentazione e stampa di documenti in formato fisso. Un modo più semplice per disegnare testo <xref:System.Windows.Controls.Label> sullo <xref:System.Windows.Controls.TextBlock>schermo consiste nell'utilizzare un oggetto . Per ulteriori <xref:System.Windows.Media.GlyphRun>informazioni su , vedere I cenni preliminari [sull'oggetto GlyphRun e sull'elemento Glyphs.](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md)  
  
<a name="compositedrawingssection"></a>
## <a name="composite-drawings"></a>Disegni composti  
 A <xref:System.Windows.Media.DrawingGroup> consente di combinare più disegni in un unico disegno composito. Utilizzando un <xref:System.Windows.Media.DrawingGroup>oggetto , è possibile combinare forme, <xref:System.Windows.Media.Drawing> immagini e testo in un unico oggetto.  
  
 Nell'esempio seguente <xref:System.Windows.Media.DrawingGroup> viene <xref:System.Windows.Media.GeometryDrawing> utilizzato un <xref:System.Windows.Media.ImageDrawing> per combinare due oggetti e un oggetto. Questo esempio produce il seguente output:  
  
 ![Oggetto DrawingGroup con più disegni](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Disegno composto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Un <xref:System.Windows.Media.DrawingGroup> oggetto consente inoltre di applicare maschere di opacità, trasformazioni, effetti bitmap e altre operazioni al relativo contenuto. <xref:System.Windows.Media.DrawingGroup>le operazioni vengono applicate <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>nel <xref:System.Windows.Media.DrawingGroup.Opacity%2A> <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>seguente <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>ordine: <xref:System.Windows.Media.DrawingGroup.Transform%2A>, , , , , e quindi .  
  
 Nella figura seguente viene <xref:System.Windows.Media.DrawingGroup> illustrato l'ordine in cui vengono applicate le operazioni.  
  
 ![Ordine delle operazioni DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Ordine delle operazioni DrawingGroup  
  
 Nella tabella seguente vengono descritte le <xref:System.Windows.Media.DrawingGroup> proprietà che è possibile utilizzare per modificare il contenuto di un oggetto.  
  
|Proprietà|Descrizione|Illustrazione|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Modifica l'opacità delle parti <xref:System.Windows.Media.DrawingGroup> selezionate del contenuto. Per un esempio, vedere [Procedura: Controllare l'opacità di un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![Oggetto DrawingGroup con una maschera di opacità](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Modifica uniformemente l'opacità del <xref:System.Windows.Media.DrawingGroup> contenuto. Utilizzare questa proprietà <xref:System.Windows.Media.Drawing> per rendere trasparente o parzialmente trasparente. Per un esempio, vedere [How to: Apply an Opacity Mask to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)) (Procedura: Applicare una maschera di opacità a un disegno).|![DrawingGroup con impostazioni di opacità diverse](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Applica <xref:System.Windows.Media.Effects.BitmapEffect> a <xref:System.Windows.Media.DrawingGroup> al contenuto. Per un esempio, vedere [Procedura: Applicare un BitmapEffect a un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![DrawingGroup con BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Consente <xref:System.Windows.Media.DrawingGroup> di ritagliare il contenuto <xref:System.Windows.Media.Geometry>in una regione descritta utilizzando un file . Per un esempio, vedere [Procedura: Ritagliare un disegno](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)).|![DrawingGroup con area di ritaglio definita](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Consente di bloccare i pixel indipendenti del dispositivo ai pixel del dispositivo lungo linee guida specificate. Questa proprietà è utile per garantire che il rendering degli elementi grafici dettagliati venga eseguito con precisione su schermi a DPI basso. Per un esempio, vedere [Procedura: Applicare un GuidelineSet a un disegno](how-to-apply-a-guidelineset-to-a-drawing.md).|![DrawingGroup con e senza GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Trasforma il <xref:System.Windows.Media.DrawingGroup> contenuto. Per un esempio, vedere [How to: Apply a Transform to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)) (Procedura: Applicare una trasformazione a un disegno).|![DrawingGroup ruotato](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>
## <a name="display-a-drawing-as-an-image"></a>Visualizzare un disegno come immagine  
 Per visualizzare <xref:System.Windows.Media.Drawing> un <xref:System.Windows.Controls.Image> con un <xref:System.Windows.Media.DrawingImage> controllo, utilizzare <xref:System.Windows.Controls.Image.Source%2A> un <xref:System.Windows.Media.DrawingImage> come <xref:System.Windows.Controls.Image> controllo <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> e impostare la proprietà dell'oggetto sul disegno che si desidera visualizzare.  
  
 Nell'esempio riportato <xref:System.Windows.Controls.Image> di seguito <xref:System.Windows.Media.GeometryDrawing>vengono utilizzati un controllo e un <xref:System.Windows.Media.DrawingImage> controllo per visualizzare un controllo . Questo esempio produce il seguente output:  
  
 ![Oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Oggetto DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>
## <a name="paint-an-object-with-a-drawing"></a>Disegnare un oggetto con un oggetto  
 A <xref:System.Windows.Media.DrawingBrush> è un tipo di pennello che dipinge un'area con un oggetto di disegno. Può essere usato per disegnare quasi tutti gli oggetti grafici con un oggetto Drawing. La <xref:System.Windows.Media.Drawing> proprietà <xref:System.Windows.Media.DrawingBrush> di un <xref:System.Windows.Media.DrawingBrush.Drawing%2A>oggetto ne descrive la proprietà . Per eseguire <xref:System.Windows.Media.Drawing> il <xref:System.Windows.Media.DrawingBrush>rendering di un oggetto con <xref:System.Windows.Media.Drawing> un oggetto , aggiungerlo al pennello utilizzando la proprietà del pennello e utilizzare il pennello per disegnare un oggetto grafico, ad esempio un controllo o un pannello.  
  
 Negli esempi seguenti <xref:System.Windows.Media.DrawingBrush> viene <xref:System.Windows.Shapes.Shape.Fill%2A> utilizzato <xref:System.Windows.Shapes.Rectangle> un per disegnare <xref:System.Windows.Media.GeometryDrawing>l'oggetto con un motivo creato da un oggetto . Questo esempio produce il seguente output:  
  
 ![Oggetto DrawingBrush affiancato](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Oggetto GeometryDrawing usato con un oggetto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 La <xref:System.Windows.Media.DrawingBrush> classe fornisce una varietà di opzioni per lo stiramento e l'afpagamento del contenuto. Per ulteriori <xref:System.Windows.Media.DrawingBrush>informazioni su , vedere la panoramica [Disegno con immagini, disegni e oggetti visivi.](painting-with-images-drawings-and-visuals.md)  
  
<a name="renderingwithvisualsection"></a>
## <a name="render-a-drawing-with-a-visual"></a>Eseguire il rendering di un disegno con un oggetto Visual  
 Un <xref:System.Windows.Media.DrawingVisual> è un tipo di oggetto visivo progettato per eseguire il rendering di un disegno. Lavorare direttamente a livello visivo è un'opportunità per gli sviluppatori che desiderano creare un ambiente grafico altamente personalizzato, ma questo argomento non viene descritto in questa panoramica. Per altre informazioni, vedere [Utilizzo degli oggetti DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>
## <a name="drawingcontext-objects"></a>Oggetti DrawingContext  
 La <xref:System.Windows.Media.DrawingContext> classe consente di <xref:System.Windows.Media.Visual> popolare <xref:System.Windows.Media.Drawing> un o un con contenuto visivo. Molti di questi oggetti grafici di livello inferiore utilizzano un <xref:System.Windows.Media.DrawingContext> perché descrive il contenuto grafico in modo molto efficiente.  
  
 Anche <xref:System.Windows.Media.DrawingContext> se i metodi di disegno <xref:System.Drawing.Graphics?displayProperty=nameWithType> appaiono simili ai metodi di disegno del tipo, in realtà sono molto diversi. <xref:System.Windows.Media.DrawingContext>viene utilizzato con un sistema grafico <xref:System.Drawing.Graphics?displayProperty=nameWithType> in modalità trattenuta, mentre il tipo viene utilizzato con un sistema grafico in modalità immediata. Quando si <xref:System.Windows.Media.DrawingContext> utilizzano i comandi di disegno di un oggetto, in realtà si archivia un insieme <xref:System.Windows.Media.DrawingContext>di istruzioni di rendering (anche se l'esatto meccanismo di archiviazione dipende dal tipo di oggetto che fornisce l'oggetto ) che verrà successivamente utilizzato dal sistema grafico; non si sta disegnando sullo schermo in tempo reale. Per ulteriori informazioni sul funzionamento del sistema grafico di Windows Presentation Foundation (WPF), vedere [Cenni](wpf-graphics-rendering-overview.md)preliminari sul rendering della grafica WPF .  
  
 Non si crea <xref:System.Windows.Media.DrawingContext>mai direttamente un'istanza di ; è tuttavia possibile acquisire un contesto di <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>disegno da determinati metodi, ad esempio e .  
  
<a name="enumeratevisualcontents"></a>
## <a name="enumerate-the-contents-of-a-visual"></a>Enumerare il contenuto di un oggetto Visual  
 Oltre agli altri utilizzi, <xref:System.Windows.Media.Drawing> gli oggetti forniscono anche un <xref:System.Windows.Media.Visual>modello a oggetti per l'enumerazione del contenuto di un oggetto .  
  
 Nell'esempio seguente <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> viene utilizzato <xref:System.Windows.Media.DrawingGroup> il <xref:System.Windows.Media.Visual> metodo per recuperare il valore di un oggetto ed enumerarlo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [Grafica 2D e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Argomenti relativi alle procedure](drawings-how-to-topics.md)
