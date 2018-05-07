---
title: Panoramica delle funzionalità multimediali
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 7a986125cff1ff4812528212fa3aee7689af1f16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="multimedia-overview"></a>Panoramica delle funzionalità multimediali
Le funzionalità multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consentono di integrare audio e video nelle applicazioni per migliorare l'esperienza utente. Questo argomento introduce le funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 
  
<a name="mediaapi"></a>   
## <a name="media-api"></a>API multimediali  
 Il <xref:System.Windows.Controls.MediaElement> e <xref:System.Windows.Media.MediaPlayer> classi vengono utilizzate per presentare il contenuto audio o video. Queste classi possono essere controllate in modo interattivo o da un orologio. È possibile usare queste classi sul controllo [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 per la riproduzione multimediale. La classe da usare dipende dallo scenario.  
  
 <xref:System.Windows.Controls.MediaElement> è un <xref:System.Windows.UIElement> che è supportata per il [Layout](../../../../docs/framework/wpf/advanced/layout.md) e può essere utilizzato come contenuto di molti controlli. È anche utilizzabile in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] nonché nel codice. <xref:System.Windows.Media.MediaPlayer>, invece, è progettato per <xref:System.Windows.Media.Drawing> oggetti e non offre il supporto di layout. Contenuti multimediali caricati mediante un <xref:System.Windows.Media.MediaPlayer> possono essere presentati solo utilizzando un <xref:System.Windows.Media.VideoDrawing> o interagendo direttamente con un <xref:System.Windows.Media.DrawingContext>. <xref:System.Windows.Media.MediaPlayer> non è utilizzabile in XAML.  
  
 Per altre informazioni sugli oggetti e sul contesto di disegno, vedere [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
> [!NOTE]
>  Quando si distribuiscono elementi multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Modalità di riproduzione di elementi multimediali  
  
> [!NOTE]
>  Entrambi <xref:System.Windows.Controls.MediaElement> e <xref:System.Windows.Media.MediaPlayer> dispongono di membri simili. I collegamenti in questa sezione si riferiscono al <xref:System.Windows.Controls.MediaElement> i membri della classe. Se non specificato diversamente, i membri collegati nella <xref:System.Windows.Controls.MediaElement> classe può essere rilevata anche nel <xref:System.Windows.Media.MediaPlayer> classe.  
  
 Per comprendere la riproduzione di elementi multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], è necessario conoscere le diverse modalità che è possibile usare per riprodurre questi elementi. Entrambi <xref:System.Windows.Controls.MediaElement> e <xref:System.Windows.Media.MediaPlayer> può essere utilizzato in due modalità di supporti diversi, la modalità indipendente e clock. La modalità di supporto è determinata dal <xref:System.Windows.Controls.MediaElement.Clock%2A> proprietà. Quando <xref:System.Windows.Controls.MediaElement.Clock%2A> è `null`, l'oggetto di supporto è in modalità indipendente. Quando il <xref:System.Windows.Controls.MediaElement.Clock%2A> è diverso da null, l'oggetto di supporto è in modalità orologio. Per impostazione predefinita, gli oggetti multimediali sono in modalità indipendente.  
  
### <a name="independent-mode"></a>Modalità indipendente  
 In modalità indipendente la riproduzione dei contenuti multimediali dipende dai contenuti stessi. Questa modalità presenta le opzioni seguenti:  
  
-   Dell'elemento multimediale <xref:System.Uri> possono essere specificati direttamente.  
  
-   È possibile controllare direttamente la riproduzione degli elementi multimediali.  
  
-   Dell'elemento multimediale <xref:System.Windows.Controls.MediaElement.Position%2A> e <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> proprietà possono essere modificate.  
  
 Contenuti multimediali vengono caricati o impostando la <xref:System.Windows.Controls.MediaElement> dell'oggetto <xref:System.Windows.Controls.MediaElement.Source%2A> proprietà o chiamando il <xref:System.Windows.Media.MediaPlayer> dell'oggetto <xref:System.Windows.Media.MediaPlayer.Open%2A> metodo.  
  
 Per controllare la riproduzione degli elementi multimediali in modalità indipendente, è possibile usare i metodi di controllo dell'oggetto multimediale. I metodi di controllo disponibili sono <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, e <xref:System.Windows.Controls.MediaElement.Stop%2A>. Per <xref:System.Windows.Controls.MediaElement>, il controllo interattivo mediante questi metodi è disponibile solo quando il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è impostato su <xref:System.Windows.Controls.MediaState.Manual>. Questi metodi non sono disponibili quando l'oggetto multimediale è in modalità orologio.  
  
 Vedere [Controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) per un esempio della modalità indipendente.  
  
### <a name="clock-mode"></a>Modalità orologio  
 In modalità orologio, un <xref:System.Windows.Media.MediaTimeline> avvia la riproduzione di supporti. La modalità orologio presenta le caratteristiche seguenti:  
  
-   Dell'elemento multimediale <xref:System.Uri> è impostata indirettamente tramite una <xref:System.Windows.Media.MediaTimeline>.  
  
-   La riproduzione degli elementi multimediali può essere controllata dall'orologio. Non è possibile usare i metodi di controllo dell'oggetto multimediale.  
  
-   Contenuti multimediali vengono caricati impostando un <xref:System.Windows.Media.MediaTimeline> dell'oggetto <xref:System.Windows.Media.MediaTimeline.Source%2A> proprietà, creando l'orologio dalla sequenza temporale e assegnandolo all'oggetto di supporto. Contenuti multimediali vengono caricati anche in questo modo quando un <xref:System.Windows.Media.MediaTimeline> all'interno di un <xref:System.Windows.Media.Animation.Storyboard> destinazioni un <xref:System.Windows.Controls.MediaElement>.  
  
 Per controllare la riproduzione multimediale in modalità orologio, il <xref:System.Windows.Media.Animation.ClockController> metodi di controllo devono essere utilizzati. Oggetto <xref:System.Windows.Media.Animation.ClockController> ottenuto dal <xref:System.Windows.Media.Animation.ClockController> proprietà del <xref:System.Windows.Media.MediaClock>. Se si tenta di utilizzare i metodi di controllo di un <xref:System.Windows.Controls.MediaElement> o <xref:System.Windows.Media.MediaPlayer> dell'oggetto in modalità di orologio, un <xref:System.InvalidOperationException> verrà generata.  
  
 Per altre informazioni sugli orologi e sulle sequenze temporali, vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Vedere [Controllare un MediaElement utilizzando uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md) per un esempio della modalità orologio.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Classe MediaElement  
 Aggiunge supporto a un'applicazione è semplice come l'aggiunta di un <xref:System.Windows.Controls.MediaElement> controllo il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dell'applicazione e fornendo un <xref:System.Uri> nei supporti che si desidera includere. Tutti i tipi di elementi multimediali supportati da [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 sono supportati in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Nell'esempio seguente viene illustrato un utilizzo semplice del <xref:System.Windows.Controls.MediaElement> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In questo esempio gli elementi multimediali vengono riprodotti automaticamente appena vengono caricati. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate (inclusa la memoria video). Si tratta del comportamento predefinito del <xref:System.Windows.Controls.MediaElement> oggetto ed è controllato dal <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> proprietà.  
  
### <a name="controlling-a-mediaelement"></a>Controllo di un oggetto MediaElement  
 Il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> proprietà controllano il comportamento del <xref:System.Windows.Controls.MediaElement> quando <xref:System.Windows.FrameworkElement.IsLoaded%2A> è `true` o `false`, rispettivamente. Il <xref:System.Windows.Controls.MediaState> le proprietà impostate influiscono sul comportamento di riproduzione supporti. Ad esempio, il valore predefinito <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Play> e il valore predefinito <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Close>. Ciò significa che non appena il <xref:System.Windows.Controls.MediaElement> viene caricato e il preroll è completo, che inizia il supporto per la riproduzione. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate.  
  
 Il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> proprietà non sono l'unico modo per controllare la riproduzione multimediale. In modalità orologio, è possibile controllare l'orologio di <xref:System.Windows.Controls.MediaElement> e i metodi di controllo interattivo sono controllare quando il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Manual>. <xref:System.Windows.Controls.MediaElement> gestisce la concorrenza per il controllo per la valutazione delle proprietà seguenti.  
  
1.  <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. Disponibile quando vengono scaricati gli elementi multimediali. In questo modo si garantisce che tutte le risorse multimediali vengono rilasciate per impostazione predefinita, anche quando un <xref:System.Windows.Media.MediaClock> è associato il <xref:System.Windows.Controls.MediaElement>.  
  
2.  <xref:System.Windows.Media.MediaClock>. Disponibile quando i supporti sono un <xref:System.Windows.Controls.MediaElement.Clock%2A>. Se i supporti vengono scaricati, il <xref:System.Windows.Media.MediaClock> diventeranno effettive fino al <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Manual>. Modalità di orologio Ignora sempre il comportamento di caricamento di <xref:System.Windows.Controls.MediaElement>.  
  
3.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. Disponibile quando vengono caricati gli elementi multimediali.  
  
4.  Metodi di controllo interattivi. Sul posto quando <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Manual>. I metodi di controllo disponibili sono <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, e <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Visualizzazione di un oggetto MediaElement  
 Per visualizzare un <xref:System.Windows.Controls.MediaElement> deve avere il contenuto per il rendering e sarà relativo <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> le proprietà impostate su zero fino a quando non viene caricato il contenuto. Per contenuti esclusivamente audio, il valore di queste proprietà è sempre zero. Per il contenuto video, una volta il <xref:System.Windows.Controls.MediaElement.MediaOpened> evento è stato generato il <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> verrà indicata la dimensione del supporto caricato. Ciò significa che fino a quando non viene caricato media, il <xref:System.Windows.Controls.MediaElement> non occupa spazio fisico nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , a meno che il <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> sono impostate.  
  
 Se si impostano entrambe il <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà causerà adattata per riempire l'area disponibile per il supporto di <xref:System.Windows.Controls.MediaElement>. Per mantenere le proporzioni del supporto originale, ovvero il <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> della proprietà deve essere impostato, ma non entrambi. Se si impostano entrambe le <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà causerà il supporto per la presentazione in una dimensione fissa che potrebbe non essere appropriata.  
  
 Per evitare questa situazione, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] può effettuare il preroll del contenuto multimediale. Questa operazione viene eseguita impostando il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> al <xref:System.Windows.Controls.MediaState.Play> o <xref:System.Windows.Controls.MediaState.Pause>. In un <xref:System.Windows.Controls.MediaState.Pause> lo stato, il supporto verrà effettuato il preroll e presenta il primo frame. In un <xref:System.Windows.Controls.MediaState.Play> stato, il supporto verrà effettuato il preroll e iniziare la riproduzione.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Classe MediaPlayer  
 Mentre il <xref:System.Windows.Controls.MediaElement> classe è un elemento framework, il <xref:System.Windows.Media.MediaPlayer> classe è progettata per essere utilizzato in <xref:System.Windows.Media.Drawing> oggetti. Gli oggetti di disegno vengono utilizzati quando è possibile sacrificare le funzionalità di livello di framework per migliorare le prestazioni o quando è necessario <xref:System.Windows.Freezable> funzionalità. <xref:System.Windows.Media.MediaPlayer> Consente di sfruttare queste funzionalità, offrendo contenuti multimediali nelle applicazioni. Ad esempio <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> può essere utilizzato in indipendente o modalità ma non di clock non dispone di <xref:System.Windows.Controls.MediaElement> stati caricato e scaricato oggetto. Questo riduce la complessità del controllo di riproduzione di <xref:System.Windows.Media.MediaPlayer>.  
  
### <a name="controlling-mediaplayer"></a>Controllo di un oggetto MediaPlayer  
 Poiché <xref:System.Windows.Media.MediaPlayer> è senza stato, sono disponibili solo due modi per controllare la riproduzione multimediale.  
  
1.  Metodi di controllo interattivi. Sul posto in modalità indipendenti (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> proprietà).  
  
2.  <xref:System.Windows.Media.MediaClock>. Disponibile quando i supporti sono un <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### <a name="displaying-a-mediaplayer"></a>Visualizzazione di un oggetto MediaPlayer  
 Tecnicamente, un <xref:System.Windows.Media.MediaPlayer> non possono essere visualizzati poiché non dispone di alcuna rappresentazione fisica. Tuttavia, può essere utilizzato per presentare i supporti in un <xref:System.Windows.Media.Drawing> utilizzando la <xref:System.Windows.Media.VideoDrawing> classe. Nell'esempio seguente viene illustrato l'utilizzo di un <xref:System.Windows.Media.VideoDrawing> per visualizzare gli elementi multimediali.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Vedere il [panoramica sugli oggetti disegno](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md) per ulteriori informazioni su <xref:System.Windows.Media.Drawing> oggetti.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.DrawingGroup>  
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)
