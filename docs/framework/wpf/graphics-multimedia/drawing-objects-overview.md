---
title: Cenni preliminari sugli oggetti Drawing
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: acdbcac957f8dc682e0038600afa90ccdfd0fe14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="drawing-objects-overview"></a>Cenni preliminari sugli oggetti Drawing
Questo argomento vengono presentate <xref:System.Windows.Media.Drawing> degli oggetti e viene descritto come utilizzarli per creare in modo efficace le forme, bitmap, testo e supporto. Utilizzare <xref:System.Windows.Media.Drawing> oggetti quando si crea ClipArt, disegnare con un <xref:System.Windows.Media.DrawingBrush>, oppure utilizzare <xref:System.Windows.Media.Visual> oggetti.  
  
 
  
<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Definizione di oggetto Drawing  
 Oggetto <xref:System.Windows.Media.Drawing> descrive il contenuto visibile, ad esempio una forma, bitmap, video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
-   <xref:System.Windows.Media.GeometryDrawing>-Consente di disegnare una forma.  
  
-   <xref:System.Windows.Media.ImageDrawing>-Consente di disegnare un'immagine.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing>-Consente di disegnare il testo.  
  
-   <xref:System.Windows.Media.VideoDrawing>-Consente di riprodurre un file audio o video.  
  
-   <xref:System.Windows.Media.DrawingGroup>: Consente di eseguire altri disegni. Usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 <xref:System.Windows.Media.Drawing>gli oggetti sono versatili. Esistono molti modi per utilizzare un <xref:System.Windows.Media.Drawing> oggetto.  
  
-   È possibile visualizzare come un'immagine utilizzando un <xref:System.Windows.Media.DrawingImage> e <xref:System.Windows.Controls.Image> controllo.  
  
-   È possibile utilizzarlo con un <xref:System.Windows.Media.DrawingBrush> per disegnare un oggetto, ad esempio il <xref:System.Windows.Controls.Page.Background%2A> di un <xref:System.Windows.Controls.Page>.  
  
-   Utilizzare per descrivere l'aspetto di un <xref:System.Windows.Media.DrawingVisual>.  
  
-   Consente di enumerare il contenuto di un <xref:System.Windows.Media.Visual>.  
  
 WPF fornisce altri tipi di oggetti che consentono di disegnare forme, bitmap, testo e contenuti multimediali. Ad esempio, è possibile utilizzare anche <xref:System.Windows.Shapes.Shape> oggetti per disegnare forme e <xref:System.Windows.Controls.MediaElement> controllo fornisce un altro modo per aggiungere video all'applicazione. Pertanto, quando è necessario utilizzare <xref:System.Windows.Media.Drawing> oggetti? Quando è possibile sacrificare le funzionalità di livello di framework per migliorare le prestazioni o quando è necessario <xref:System.Windows.Freezable> funzionalità. Perché <xref:System.Windows.Media.Drawing> oggetti prive del supporto per [Layout](../../../../docs/framework/wpf/advanced/layout.md), l'input e concentrare l'attenzione, offrono i vantaggi delle prestazioni che li rendono ideali per descrivere sfondi, ClipArt e per il disegno di basso livello con <xref:System.Windows.Media.Visual> oggetti.  
  
 Poiché si tratta di un tipo <xref:System.Windows.Freezable> oggetto <xref:System.Windows.Media.Drawing> gli oggetti ottengono molte funzionalità speciali, ad esempio: possono essere dichiarate come [risorse](../../../../docs/framework/wpf/advanced/xaml-resources.md)condiviso tra più oggetti, in sola lettura per migliorare prestazioni, duplicati e resi thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite da <xref:System.Windows.Freezable> degli oggetti, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Disegnare una forma  
 Per disegnare una forma, si utilizza un <xref:System.Windows.Media.GeometryDrawing>. Del disegno della geometria <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> proprietà descrive la forma da disegnare, il relativo <xref:System.Windows.Media.GeometryDrawing.Brush%2A> proprietà descrive come deve essere disegnato l'interno della forma e il relativo <xref:System.Windows.Media.GeometryDrawing.Pen%2A> proprietà descrive la modalità con cui deve essere disegnato il contorno.  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.GeometryDrawing> per disegnare una forma. La forma è descritta da un <xref:System.Windows.Media.GeometryGroup> e due <xref:System.Windows.Media.EllipseGeometry> oggetti. Viene disegnato l'interno della forma con un <xref:System.Windows.Media.LinearGradientBrush> e la struttura con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.  
  
 In questo esempio vengono creati i seguenti <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing di due ellissi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Per un esempio completo, vedere [Procedura: Creare un oggetto GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-geometrydrawing.md).  
  
 Altri <xref:System.Windows.Media.Geometry> classi, ad esempio <xref:System.Windows.Media.PathGeometry> consentono di creare forme più complesse mediante la creazione di curve e archi. Per ulteriori informazioni su <xref:System.Windows.Media.Geometry> degli oggetti, vedere il [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 Per ulteriori informazioni su altri modi per disegnare forme che non usano <xref:System.Windows.Media.Drawing> degli oggetti, vedere [forme e disegno di base di WPF Overview](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Disegnare un'immagine  
 Per disegnare un'immagine, si utilizza un <xref:System.Windows.Media.ImageDrawing>. Un <xref:System.Windows.Media.ImageDrawing> dell'oggetto <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> proprietà descrive l'immagine da disegnare e il relativo <xref:System.Windows.Media.ImageDrawing.Rect%2A> proprietà definisce l'area in cui viene disegnata l'immagine.  
  
 L'esempio seguente disegna un'immagine in un rettangolo posizionata nel punto (75,75) vale a dire 100 x 100 pixel. La figura seguente mostra il <xref:System.Windows.Media.ImageDrawing> creato dall'esempio. Per mostrare i limiti di cui è stato aggiunto un bordo grigio di <xref:System.Windows.Media.ImageDrawing>.  
  
 ![75,75 100 per 100 disegnata in ImageDrawing &#40; &#41; ] (../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing di 100 per 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Per altre informazioni sulle immagini, vedere [Cenni preliminari sulla creazione dell'immagine](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Riprodurre contenuti multimediali (solo codice)  
  
> [!NOTE]
>  Sebbene sia possibile dichiarare un <xref:System.Windows.Media.VideoDrawing> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è solo possibile caricare e riprodurre i file multimediali tramite codice. Per la riproduzione di video [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utilizzare un <xref:System.Windows.Controls.MediaElement> invece.  
  
 Per riprodurre un file audio o video, si utilizza un <xref:System.Windows.Media.VideoDrawing> e <xref:System.Windows.Media.MediaPlayer>. È possibile caricare e riprodurre contenuti multimediali in due modi diversi. Il primo consiste nell'usare un <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> da se stessi, mentre la seconda consiste nel crearne di proprie <xref:System.Windows.Media.MediaTimeline> da utilizzare con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
 Per riprodurre file multimediali senza crearne una propria <xref:System.Windows.Media.MediaTimeline>, attenersi alla procedura seguente.  
  
1.  Creare un oggetto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2.  Utilizzare il <xref:System.Windows.Media.MediaPlayer.Open%2A> metodo per caricare il file multimediale.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3.  Creare un oggetto <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4.  Specificare le dimensioni e posizione per disegnare il supporto impostando il <xref:System.Windows.Media.VideoDrawing.Rect%2A> proprietà del <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5.  Impostare il <xref:System.Windows.Media.VideoDrawing.Player%2A> proprietà del <xref:System.Windows.Media.VideoDrawing> con il <xref:System.Windows.Media.MediaPlayer> creato.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6.  Utilizzare il <xref:System.Windows.Media.MediaPlayer.Play%2A> metodo il <xref:System.Windows.Media.MediaPlayer> per avviare la riproduzione di file multimediale.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.VideoDrawing> e <xref:System.Windows.Media.MediaPlayer> per riprodurre un file video, una volta.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per un ulteriore controllo della durata dei contenuti multimediali, utilizzare un <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti. Il <xref:System.Windows.Media.MediaTimeline> consente di specificare se deve essere ripetuto il video. Per utilizzare un <xref:System.Windows.Media.MediaTimeline> con un <xref:System.Windows.Media.VideoDrawing>, attenersi alla procedura seguente:  
  
1.  Dichiarare il <xref:System.Windows.Media.MediaTimeline> e impostarne i comportamenti di temporizzazione.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2.  Creare un <xref:System.Windows.Media.MediaClock> dal <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3.  Creare un <xref:System.Windows.Media.MediaPlayer> e utilizzare il <xref:System.Windows.Media.MediaClock> per impostare il relativo <xref:System.Windows.Media.MediaPlayer.Clock%2A> proprietà.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4.  Creare un <xref:System.Windows.Media.VideoDrawing> e assegnare il <xref:System.Windows.Media.MediaPlayer> per il <xref:System.Windows.Media.VideoDrawing.Player%2A> proprietà del <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.MediaTimeline> con un <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> per riprodurre un video più volte.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Si noti che, quando si utilizza un <xref:System.Windows.Media.MediaTimeline>, utilizzare l'oggetto interattivo <xref:System.Windows.Media.Animation.ClockController> restituito dal <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà del <xref:System.Windows.Media.MediaClock> per controllare la riproduzione multimediale anziché i metodi interattivi di <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Creare testo  
 Per disegnare il testo, si utilizza un <xref:System.Windows.Media.GlyphRunDrawing> e <xref:System.Windows.Media.GlyphRun>. Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.GlyphRunDrawing> per disegnare il testo "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Oggetto <xref:System.Windows.Media.GlyphRun> è un oggetto di basso livello per l'utilizzo con la presentazione di documenti in formato fisso e scenari di stampa. Un modo più semplice per disegnare testo sullo schermo consiste nell'utilizzare un <xref:System.Windows.Controls.Label> o <xref:System.Windows.Controls.TextBlock>. Per ulteriori informazioni su <xref:System.Windows.Media.GlyphRun>, vedere il [Introduzione all'oggetto GlyphRun e icone elemento](../../../../docs/framework/wpf/advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) Panoramica.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Disegni composti  
 Oggetto <xref:System.Windows.Media.DrawingGroup> consente di combinare più disegni in un unico disegno composto. Utilizzando un <xref:System.Windows.Media.DrawingGroup>, è possibile combinare forme, immagini e testo in un singolo <xref:System.Windows.Media.Drawing> oggetto.  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.DrawingGroup> per combinare due <xref:System.Windows.Media.GeometryDrawing> oggetti e un <xref:System.Windows.Media.ImageDrawing> oggetto. Questo esempio produce il seguente output:  
  
 ![DrawingGroup con più disegni](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")  
Disegno composto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Oggetto <xref:System.Windows.Media.DrawingGroup> consente inoltre di applicare la maschera di opacità, trasformazioni, gli effetti bitmap e altre operazioni al relativo contenuto. <xref:System.Windows.Media.DrawingGroup>le operazioni vengono applicate nell'ordine seguente: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>e quindi <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Nella figura seguente viene illustrato l'ordine in cui <xref:System.Windows.Media.DrawingGroup> vengono applicate le operazioni.  
  
 ![Ordine delle operazioni DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Ordine delle operazioni DrawingGroup  
  
 Nella tabella seguente vengono descritte le proprietà che è possibile utilizzare per modificare un <xref:System.Windows.Media.DrawingGroup> contenuto dell'oggetto.  
  
|Proprietà|Descrizione|Illustrazione|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Modifica l'opacità di parti selezionate del <xref:System.Windows.Media.DrawingGroup> contenuto. Per un esempio, vedere [Procedura: Controllare l'opacità di un disegno](http://msdn.microsoft.com/en-us/68580652-7d32-4d27-93cc-a5148cf4d5ee).|![Oggetto DrawingGroup con una maschera di opacità](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Modificare in modo uniforme l'opacità del <xref:System.Windows.Media.DrawingGroup> contenuto. Utilizzare questa proprietà per rendere un <xref:System.Windows.Media.Drawing> trasparente o semitrasparente. Per un esempio, vedere [How to: Apply an Opacity Mask to a Drawing](http://msdn.microsoft.com/en-us/d77b420b-9be2-479c-a45e-82f4da30eb9f) (Procedura: Applicare una maschera di opacità a un disegno).|![Oggetto DrawingGroups con impostazioni di opacità diverse](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Si applica un <xref:System.Windows.Media.Effects.BitmapEffect> per il <xref:System.Windows.Media.DrawingGroup> contenuto. Per un esempio, vedere [Procedura: Applicare un BitmapEffect a un disegno](http://msdn.microsoft.com/en-us/c5b1de83-8d09-47fb-96db-5f174471f4b5).|![Oggetto DrawingGroup con BlurBitmapEffect](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Ritaglia il <xref:System.Windows.Media.DrawingGroup> contenuto a un'area descritta mediante un <xref:System.Windows.Media.Geometry>. Per un esempio, vedere [Procedura: Ritagliare un disegno](http://msdn.microsoft.com/en-us/1f7d8a2c-c3c2-42cb-a542-e6796f9fb058).|![Oggetto DrawingGroup con area ritagliata definita](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Consente di bloccare i pixel indipendenti del dispositivo ai pixel del dispositivo lungo linee guida specificate. Questa proprietà è utile per garantire che il rendering degli elementi grafici dettagliati venga eseguito con precisione su schermi a DPI basso. Per un esempio, vedere [Procedura: Applicare un GuidelineSet a un disegno](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-a-guidelineset-to-a-drawing.md).|![Oggetto DrawingGroup con e senza un GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Trasforma il <xref:System.Windows.Media.DrawingGroup> contenuto. Per un esempio, vedere [How to: Apply a Transform to a Drawing](http://msdn.microsoft.com/en-us/0d525f2b-682d-4d67-9660-cf46929fbabd) (Procedura: Applicare una trasformazione a un disegno).|![Oggetto DrawingGroup ruotato](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Visualizzare un disegno come immagine  
 Per visualizzare un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Controls.Image> controllo, utilizzare un <xref:System.Windows.Media.DrawingImage> come il <xref:System.Windows.Controls.Image> del controllo <xref:System.Windows.Controls.Image.Source%2A> e impostare il <xref:System.Windows.Media.DrawingImage> dell'oggetto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> proprietà per il disegno che si desidera visualizzare.  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.DrawingImage> e <xref:System.Windows.Controls.Image> controllo per visualizzare un <xref:System.Windows.Media.GeometryDrawing>. Questo esempio produce il seguente output:  
  
 ![GeometryDrawing di due ellissi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Oggetto DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Disegnare un oggetto con un oggetto  
 Oggetto <xref:System.Windows.Media.DrawingBrush> è un tipo di pennello che disegna un'area con un oggetto. Può essere usato per disegnare quasi tutti gli oggetti grafici con un oggetto Drawing. Il <xref:System.Windows.Media.Drawing> proprietà di un <xref:System.Windows.Media.DrawingBrush> descrive relativo <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Per eseguire il rendering di un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Media.DrawingBrush>, aggiungerlo al pennello usando il pennello <xref:System.Windows.Media.Drawing> proprietà e utilizzare il pennello per disegnare un grafico di oggetti, ad esempio un controllo o un pannello.  
  
 Negli esempi seguenti viene utilizzata una <xref:System.Windows.Media.DrawingBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle> con un modello creato da un <xref:System.Windows.Media.GeometryDrawing>. Questo esempio produce il seguente output:  
  
 ![Oggetto affiancato di DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Oggetto GeometryDrawing usato con un oggetto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 La <xref:System.Windows.Media.DrawingBrush> classe offre un'ampia gamma di opzioni per l'adattamento e affiancamento del contenuto. Per ulteriori informazioni su <xref:System.Windows.Media.DrawingBrush>, vedere il [il disegno di immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md) Panoramica.  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Eseguire il rendering di un disegno con un oggetto Visual  
 Oggetto <xref:System.Windows.Media.DrawingVisual> è un tipo di oggetto visivo progettato per eseguire il rendering di un disegno. Lavorare direttamente a livello visivo è un'opportunità per gli sviluppatori che desiderano creare un ambiente grafico altamente personalizzato, ma questo argomento non viene descritto in questa panoramica. Per altre informazioni, vedere [Utilizzo degli oggetti DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>Oggetti DrawingContext  
 Il <xref:System.Windows.Media.DrawingContext> classe consente di popolare un <xref:System.Windows.Media.Visual> o <xref:System.Windows.Media.Drawing> con contenuto visivo. Molti tali oggetti di livello inferiore grafici utilizzano un <xref:System.Windows.Media.DrawingContext> perché descrive il contenuto del grafico in modo molto efficiente.  
  
 Sebbene il <xref:System.Windows.Media.DrawingContext> metodi di disegno simile ai metodi di disegno di <xref:System.Drawing.Graphics?displayProperty=nameWithType> tipo, si tratta in realtà molto diversi. <xref:System.Windows.Media.DrawingContext>viene utilizzato con un sistema di grafica in modalità differita, mentre il <xref:System.Drawing.Graphics?displayProperty=nameWithType> tipo viene utilizzato con un sistema di grafica in modalità immediata. Quando si utilizza un <xref:System.Windows.Media.DrawingContext> comandi di disegno dell'oggetto, si archivia un set di istruzioni di rendering (anche se il meccanismo di archiviazione esatto dipende dal tipo di oggetto che fornisce il <xref:System.Windows.Media.DrawingContext>) che verrà successivamente utilizzata per il grafico sistema; non sono disegno sullo schermo in tempo reale. Per altre informazioni sul funzionamento del sistema grafico di [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], vedere [Cenni preliminari sul rendering della grafica WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 Non creare direttamente un'istanza un <xref:System.Windows.Media.DrawingContext>; tuttavia, è possibile, acquisire un contesto di disegno da determinati metodi, ad esempio <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> e <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Enumerare il contenuto di un oggetto Visual  
 Oltre agli altri utilizzi <xref:System.Windows.Media.Drawing> oggetti forniscono anche un modello a oggetti per l'enumerazione del contenuto di un <xref:System.Windows.Media.Visual>.  
  
 L'esempio seguente usa il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> metodo per recuperare il <xref:System.Windows.Media.DrawingGroup> valore di un <xref:System.Windows.Media.Visual> e di eseguirne l'enumerazione.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Cenni preliminari sulle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Cenni preliminari sul rendering della grafica WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/graphics-multimedia/drawings-how-to-topics.md)
