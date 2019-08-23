---
title: Panoramica delle funzionalità multimediali
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 44059fe96a0deeda18f0abd9079100b55be98e77
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929614"
---
# <a name="multimedia-overview"></a>Panoramica delle funzionalità multimediali
Le funzionalità multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consentono di integrare audio e video nelle applicazioni per migliorare l'esperienza utente. Questo argomento introduce le funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>   
## <a name="media-api"></a>API multimediali  
 Le <xref:System.Windows.Controls.MediaElement> classi <xref:System.Windows.Media.MediaPlayer> e vengono usate per presentare contenuto audio o video. Queste classi possono essere controllate in modo interattivo o da un orologio. È possibile usare queste classi sul controllo [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 per la riproduzione multimediale. La classe da usare dipende dallo scenario.  
  
 <xref:System.Windows.Controls.MediaElement>è un <xref:System.Windows.UIElement> oggetto supportato dal [layout](../advanced/layout.md) e che può essere utilizzato come contenuto di molti controlli. È anche utilizzabile in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] nonché nel codice. <xref:System.Windows.Media.MediaPlayer>d'altra parte, è progettato per gli oggetti <xref:System.Windows.Media.Drawing> e non dispone del supporto per il layout. I supporti caricati usando <xref:System.Windows.Media.MediaPlayer> un oggetto possono essere presentati solo <xref:System.Windows.Media.VideoDrawing> usando o interagendo direttamente con un <xref:System.Windows.Media.DrawingContext>. <xref:System.Windows.Media.MediaPlayer>non può essere usato in XAML.  
  
 Per altre informazioni sugli oggetti e sul contesto di disegno, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
> Quando si distribuiscono elementi multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Modalità di riproduzione di elementi multimediali  
  
> [!NOTE]
> <xref:System.Windows.Controls.MediaElement> E<xref:System.Windows.Media.MediaPlayer> hanno membri simili. I collegamenti in questa sezione fanno riferimento ai <xref:System.Windows.Controls.MediaElement> membri della classe. A meno che non sia specificato in modo specifico, <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> nella classe è possibile trovare anche i membri collegati alla classe.  
  
 Per comprendere la riproduzione di elementi multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], è necessario conoscere le diverse modalità che è possibile usare per riprodurre questi elementi. Sia <xref:System.Windows.Controls.MediaElement> che<xref:System.Windows.Media.MediaPlayer> possono essere usati in due diverse modalità multimediali, in modalità indipendente e in modalità orologio. La modalità supporto è determinata dalla <xref:System.Windows.Controls.MediaElement.Clock%2A> proprietà. Quando <xref:System.Windows.Controls.MediaElement.Clock%2A> è`null`, l'oggetto multimediale è in modalità indipendente. <xref:System.Windows.Controls.MediaElement.Clock%2A> Quando è diverso da null, l'oggetto multimediale è in modalità clock. Per impostazione predefinita, gli oggetti multimediali sono in modalità indipendente.  
  
### <a name="independent-mode"></a>Modalità indipendente  
 In modalità indipendente la riproduzione dei contenuti multimediali dipende dai contenuti stessi. Questa modalità presenta le opzioni seguenti:  
  
- È <xref:System.Uri> possibile specificare direttamente i supporti.  
  
- È possibile controllare direttamente la riproduzione degli elementi multimediali.  
  
- È possibile <xref:System.Windows.Controls.MediaElement.Position%2A> modificare <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> le proprietà e del supporto.  
  
 Il supporto viene caricato impostando la <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Controls.MediaElement.Source%2A> proprietà dell'oggetto o chiamando il <xref:System.Windows.Media.MediaPlayer.Open%2A> metodo <xref:System.Windows.Media.MediaPlayer> dell'oggetto.  
  
 Per controllare la riproduzione degli elementi multimediali in modalità indipendente, è possibile usare i metodi di controllo dell'oggetto multimediale. I metodi di controllo disponibili <xref:System.Windows.Controls.MediaElement.Play%2A>sono <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>,, e <xref:System.Windows.Controls.MediaElement.Stop%2A>. Per <xref:System.Windows.Controls.MediaElement>, il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> controllo interattivo che usa questi metodi è disponibile solo quando è impostato <xref:System.Windows.Controls.MediaState.Manual>su. Questi metodi non sono disponibili quando l'oggetto multimediale è in modalità orologio.  
  
 Vedere [Controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) per un esempio della modalità indipendente.  
  
### <a name="clock-mode"></a>Modalità orologio  
 In modalità orologio, una <xref:System.Windows.Media.MediaTimeline> unità riproduce i supporti. La modalità orologio presenta le caratteristiche seguenti:  
  
- <xref:System.Windows.Media.MediaTimeline>I supporti <xref:System.Uri> vengono impostati indirettamente tramite.  
  
- La riproduzione degli elementi multimediali può essere controllata dall'orologio. Non è possibile usare i metodi di controllo dell'oggetto multimediale.  
  
- I supporti vengono caricati impostando <xref:System.Windows.Media.MediaTimeline> la <xref:System.Windows.Media.MediaTimeline.Source%2A> proprietà di un oggetto, creando il clock dalla sequenza temporale e assegnando l'orologio all'oggetto multimediale. Anche il supporto viene caricato in questo modo <xref:System.Windows.Media.MediaTimeline> quando un <xref:System.Windows.Media.Animation.Storyboard> oggetto all' <xref:System.Windows.Controls.MediaElement>interno di un oggetto è destinato a.  
  
 Per controllare la riproduzione di file multimediali in modalità <xref:System.Windows.Media.Animation.ClockController> orologio, è necessario usare i metodi di controllo. Un <xref:System.Windows.Media.Animation.ClockController> oggetto viene ottenuto <xref:System.Windows.Media.Animation.ClockController> dalla proprietà dell'oggetto <xref:System.Windows.Media.MediaClock>. Se si tenta di usare i metodi di controllo di un <xref:System.Windows.Controls.MediaElement> oggetto <xref:System.Windows.Media.MediaPlayer> o in modalità clock, verrà generata <xref:System.InvalidOperationException> un'eccezione.  
  
 Per altre informazioni sugli orologi e sulle sequenze temporali, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Vedere [Controllare un MediaElement utilizzando uno storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md) per un esempio della modalità orologio.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Classe MediaElement  
 L'aggiunta di file multimediali a un'applicazione è semplice quanto <xref:System.Windows.Controls.MediaElement> l'aggiunta di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] un controllo all'oggetto dell'applicazione <xref:System.Uri> e la creazione di un elemento multimediale che si desidera includere. Tutti i tipi di elementi multimediali supportati da [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 sono supportati in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Nell'esempio seguente viene illustrato un semplice utilizzo di <xref:System.Windows.Controls.MediaElement> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In questo esempio gli elementi multimediali vengono riprodotti automaticamente appena vengono caricati. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate (inclusa la memoria video). Questo è il comportamento predefinito dell' <xref:System.Windows.Controls.MediaElement> oggetto ed è controllato <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> dalle proprietà e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> .  
  
### <a name="controlling-a-mediaelement"></a>Controllo di un oggetto MediaElement  
 Le <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> e <xref:System.Windows.FrameworkElement.IsLoaded%2A> `true` controllano il comportamento di `false`quando è o, rispettivamente. <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Controls.MediaState> Le proprietà sono impostate in modo da influire sul comportamento della riproduzione multimediale. Il valore predefinito <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Play> , ad esempio, e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> il <xref:System.Windows.Controls.MediaState.Close>valore predefinito è. Ciò significa che non appena <xref:System.Windows.Controls.MediaElement> viene caricato e il preroll è completo, inizia la riproduzione del supporto. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate.  
  
 Le <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> e non sono l'unico modo per controllare la riproduzione dei supporti. In modalità orologio, l'orologio può controllare <xref:System.Windows.Controls.MediaElement> e i metodi di controllo interattivo hanno il controllo <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> quando è <xref:System.Windows.Controls.MediaState.Manual>. <xref:System.Windows.Controls.MediaElement>gestisce questa competizione per il controllo valutando le priorità seguenti.  
  
1. [https://login.microsoftonline.com/common/](<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>). Disponibile quando vengono scaricati gli elementi multimediali. In questo modo si garantisce che tutte le risorse multimediali vengano rilasciate <xref:System.Windows.Media.MediaClock> per impostazione predefinita, <xref:System.Windows.Controls.MediaElement>anche quando un è associato a.  
  
2. <xref:System.Windows.Media.MediaClock>. Sul posto quando i supporti hanno <xref:System.Windows.Controls.MediaElement.Clock%2A>un. Se il supporto viene scaricato, la <xref:System.Windows.Media.MediaClock> funzionerà a condizione <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> che sia <xref:System.Windows.Controls.MediaState.Manual>. La modalità orologio esegue sempre l'override del comportamento <xref:System.Windows.Controls.MediaElement>caricato della.  
  
3. [https://login.microsoftonline.com/common/](<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>). Disponibile quando vengono caricati gli elementi multimediali.  
  
4. Metodi di controllo interattivi. Sul posto quando <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Manual>. I metodi di controllo disponibili <xref:System.Windows.Controls.MediaElement.Play%2A>sono <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>,, e <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Visualizzazione di un oggetto MediaElement  
 Per visualizzare un <xref:System.Windows.Controls.MediaElement> oggetto, deve essere presente contenuto di cui eseguire il rendering <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> le sue proprietà e sono impostate su zero fino a quando il contenuto non viene caricato. Per contenuti esclusivamente audio, il valore di queste proprietà è sempre zero. Per il contenuto video, una <xref:System.Windows.Controls.MediaElement.MediaOpened> volta che l'evento è <xref:System.Windows.FrameworkElement.ActualWidth%2A> stato <xref:System.Windows.FrameworkElement.ActualHeight%2A> generato e segnalerà le dimensioni del supporto caricato. Ciò significa che fino a quando non viene caricato <xref:System.Windows.Controls.MediaElement> un supporto, non viene occupato alcuno spazio fisico [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] in, a <xref:System.Windows.FrameworkElement.Width%2A> meno <xref:System.Windows.FrameworkElement.Height%2A> che non siano impostate le proprietà o.  
  
 Impostando entrambe <xref:System.Windows.FrameworkElement.Width%2A> le <xref:System.Windows.FrameworkElement.Height%2A> proprietà e, il supporto si estenderà per riempire <xref:System.Windows.Controls.MediaElement>l'area specificata per. Per mantenere le proporzioni originali del supporto, è necessario <xref:System.Windows.FrameworkElement.Width%2A> impostare <xref:System.Windows.FrameworkElement.Height%2A> la proprietà o, ma non entrambe. Impostando entrambe <xref:System.Windows.FrameworkElement.Width%2A> le <xref:System.Windows.FrameworkElement.Height%2A> proprietà e, il supporto sarà presente in una dimensione dell'elemento fissa che potrebbe non essere auspicabile.  
  
 Per evitare questa situazione, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] può effettuare il preroll del contenuto multimediale. Questa operazione viene eseguita <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> impostando <xref:System.Windows.Controls.MediaState.Play> su o <xref:System.Windows.Controls.MediaState.Pause>su. In uno <xref:System.Windows.Controls.MediaState.Pause> stato, viene eseguito il prerolling del supporto e il primo frame è presente. In uno <xref:System.Windows.Controls.MediaState.Play> stato, i supporti vengono preroll e iniziano a riprodursi.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Classe MediaPlayer  
 Laddove la <xref:System.Windows.Controls.MediaElement> classe è un elemento del Framework, la <xref:System.Windows.Media.MediaPlayer> classe è progettata per essere utilizzata negli <xref:System.Windows.Media.Drawing> oggetti. Gli oggetti Drawing vengono usati quando è possibile sacrificare le funzionalità a livello di Framework per ottenere vantaggi <xref:System.Windows.Freezable> in termini di prestazioni o quando sono necessarie funzionalità. <xref:System.Windows.Media.MediaPlayer>consente di sfruttare queste funzionalità fornendo contenuti multimediali nelle applicazioni. Like <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> può essere utilizzato in modalità indipendente o orologio, ma non dispone degli <xref:System.Windows.Controls.MediaElement> stati scaricati e caricati dell'oggetto. In questo modo si riduce la complessità del <xref:System.Windows.Media.MediaPlayer>controllo della riproduzione di.  
  
### <a name="controlling-mediaplayer"></a>Controllo di un oggetto MediaPlayer  
 Poiché <xref:System.Windows.Media.MediaPlayer> è senza stato, esistono solo due modi per controllare la riproduzione dei supporti.  
  
1. Metodi di controllo interattivi. Sul posto in modalità indipendente (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> proprietà).  
  
2. <xref:System.Windows.Media.MediaClock>. Sul posto quando i supporti hanno <xref:System.Windows.Media.MediaPlayer.Clock%2A>un.  
  
### <a name="displaying-a-mediaplayer"></a>Visualizzazione di un oggetto MediaPlayer  
 Tecnicamente, non <xref:System.Windows.Media.MediaPlayer> è possibile visualizzare un oggetto perché non è presente alcuna rappresentazione fisica. Può tuttavia essere utilizzato per presentare supporti in un oggetto <xref:System.Windows.Media.Drawing> utilizzando la <xref:System.Windows.Media.VideoDrawing> classe. Nell'esempio seguente viene illustrato l'utilizzo di <xref:System.Windows.Media.VideoDrawing> un oggetto per visualizzare i supporti.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ulteriori informazioni sugli <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari](drawing-objects-overview.md) sugli oggetti Drawing.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingGroup>
- [Layout](../advanced/layout.md)
- [Procedure relative alle proprietà](audio-and-video-how-to-topics.md)
