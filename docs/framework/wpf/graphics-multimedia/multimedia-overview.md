---
title: Panoramica delle funzionalità multimediali
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: d4abf4d9fd324ffbf2737dc686c02e50ca1a8a5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181877"
---
# <a name="multimedia-overview"></a>Panoramica delle funzionalità multimediali
Le funzionalità multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consentono di integrare audio e video nelle applicazioni per migliorare l'esperienza utente. Questo argomento introduce le funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>
## <a name="media-api"></a>API multimediali  
 Le <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> classi e vengono utilizzate per presentare contenuti audio o video. Queste classi possono essere controllate in modo interattivo o da un orologio. Queste classi possono utilizzare il controllo Microsoft Windows Media Player 10 per la riproduzione multimediale. La classe da usare dipende dallo scenario.  
  
 <xref:System.Windows.Controls.MediaElement>è <xref:System.Windows.UIElement> un che è supportato dal [Layout](../advanced/layout.md) e può essere utilizzato come contenuto di molti controlli. È anche utilizzabile in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] nonché nel codice. <xref:System.Windows.Media.MediaPlayer>, d'altra parte, <xref:System.Windows.Media.Drawing> è progettato per gli oggetti e manca del supporto del layout. I supporti <xref:System.Windows.Media.MediaPlayer> caricati utilizzando <xref:System.Windows.Media.VideoDrawing> un oggetto possono essere <xref:System.Windows.Media.DrawingContext>presentati solo utilizzando un oggetto o interagendo direttamente con un file . <xref:System.Windows.Media.MediaPlayer>non può essere utilizzato in XAML.  
  
 Per altre informazioni sugli oggetti e sul contesto di disegno, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
> Quando si distribuiscono elementi multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
<a name="mediaplaybackmodes"></a>
## <a name="media-playback-modes"></a>Modalità di riproduzione di elementi multimediali  
  
> [!NOTE]
> Entrambi <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> e hanno membri simili. I link in questa <xref:System.Windows.Controls.MediaElement> sezione fanno riferimento ai membri della classe. A meno che non si <xref:System.Windows.Controls.MediaElement> noti in modo <xref:System.Windows.Media.MediaPlayer> specifico, i membri collegati alla classe possono essere trovati anche nella classe.  
  
 Per comprendere la riproduzione di elementi multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], è necessario conoscere le diverse modalità che è possibile usare per riprodurre questi elementi. Entrambi <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> e possono essere utilizzati in due diverse modalità multimediali, modalità indipendente e modalità orologio. La modalità multimediale <xref:System.Windows.Controls.MediaElement.Clock%2A> è determinata dalla proprietà . Quando <xref:System.Windows.Controls.MediaElement.Clock%2A> `null`è , l'oggetto multimediale è in modalità indipendente. Quando <xref:System.Windows.Controls.MediaElement.Clock%2A> l'oggetto è diverso da null, l'oggetto multimediale è in modalità orologio. Per impostazione predefinita, gli oggetti multimediali sono in modalità indipendente.  
  
### <a name="independent-mode"></a>Modalità indipendente  
 In modalità indipendente la riproduzione dei contenuti multimediali dipende dai contenuti stessi. Questa modalità presenta le opzioni seguenti:  
  
- I supporti <xref:System.Uri> possono essere specificati direttamente.  
  
- È possibile controllare direttamente la riproduzione degli elementi multimediali.  
  
- I <xref:System.Windows.Controls.MediaElement.Position%2A> supporti <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> e le proprietà possono essere modificati.  
  
 Il supporto viene caricato <xref:System.Windows.Controls.MediaElement> impostando <xref:System.Windows.Controls.MediaElement.Source%2A> la proprietà dell'oggetto o chiamando il <xref:System.Windows.Media.MediaPlayer> metodo dell'oggetto. <xref:System.Windows.Media.MediaPlayer.Open%2A>  
  
 Per controllare la riproduzione degli elementi multimediali in modalità indipendente, è possibile usare i metodi di controllo dell'oggetto multimediale. I metodi di <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A>controllo <xref:System.Windows.Controls.MediaElement.Close%2A>disponibili <xref:System.Windows.Controls.MediaElement.Stop%2A>sono , , , e . Per <xref:System.Windows.Controls.MediaElement>, il controllo interattivo che <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> utilizza <xref:System.Windows.Controls.MediaState.Manual>questi metodi è disponibile solo quando l'oggetto è impostato su . Questi metodi non sono disponibili quando l'oggetto multimediale è in modalità orologio.  
  
 Vedere [Controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) per un esempio della modalità indipendente.  
  
### <a name="clock-mode"></a>Modalità orologio  
 In modalità <xref:System.Windows.Media.MediaTimeline> orologio, un aziona la riproduzione multimediale. La modalità orologio presenta le caratteristiche seguenti:  
  
- I media <xref:System.Uri> sono indirettamente <xref:System.Windows.Media.MediaTimeline>impostati tramite un file .  
  
- La riproduzione degli elementi multimediali può essere controllata dall'orologio. Non è possibile usare i metodi di controllo dell'oggetto multimediale.  
  
- Il supporto viene <xref:System.Windows.Media.MediaTimeline> caricato impostando <xref:System.Windows.Media.MediaTimeline.Source%2A> la proprietà di un oggetto, creando l'orologio dalla sequenza temporale e assegnando l'orologio all'oggetto multimediale. Anche i supporti vengono <xref:System.Windows.Media.MediaTimeline> caricati <xref:System.Windows.Controls.MediaElement>in questo modo quando un'applicazione all'interno di un oggetto .NET <xref:System.Windows.Media.Animation.Storyboard> .  
  
 Per controllare la riproduzione <xref:System.Windows.Media.Animation.ClockController> multimediale in modalità orologio, è necessario utilizzare i metodi di controllo. A <xref:System.Windows.Media.Animation.ClockController> si ottiene <xref:System.Windows.Media.Animation.ClockController> dalla <xref:System.Windows.Media.MediaClock>proprietà del file . Se si tenta di utilizzare i <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> metodi di controllo di <xref:System.InvalidOperationException> un oggetto o in modalità orologio, verrà generato un verrà generato un verrà generato un.  
  
 Per altre informazioni sugli orologi e sulle sequenze temporali, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Vedere [Controllare un MediaElement utilizzando uno storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md) per un esempio della modalità orologio.  
  
<a name="mediaelement"></a>
## <a name="mediaelement-class"></a>Classe MediaElement  
 L'aggiunta di supporti a <xref:System.Windows.Controls.MediaElement> un'applicazione [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] è semplice come <xref:System.Uri> aggiungere un controllo all'applicazione e fornire a al supporto che si desidera includere. Tutti i tipi di supporto supportati da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Microsoft Windows Media Player 10 sono supportati in . Nell'esempio seguente viene illustrato <xref:System.Windows.Controls.MediaElement> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]un semplice utilizzo di in .  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In questo esempio gli elementi multimediali vengono riprodotti automaticamente appena vengono caricati. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate (inclusa la memoria video). Questo è il comportamento <xref:System.Windows.Controls.MediaElement> predefinito dell'oggetto <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> ed è controllato dalle proprietà e .  
  
### <a name="controlling-a-mediaelement"></a>Controllo di un oggetto MediaElement  
 Le <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> proprietà e controllano <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.FrameworkElement.IsLoaded%2A> il `true` `false`comportamento di quando è o , rispettivamente. Le <xref:System.Windows.Controls.MediaState> proprietà sono impostate per influenzare il comportamento di riproduzione multimediale. Ad esempio, <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> il <xref:System.Windows.Controls.MediaState.Play> valore <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> predefinito <xref:System.Windows.Controls.MediaState.Close>è e il valore predefinito è . Ciò significa che <xref:System.Windows.Controls.MediaElement> non appena il carico e il preroll è completo, il supporto inizia a giocare. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate.  
  
 Le <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> proprietà e non sono l'unico modo per controllare la riproduzione multimediale. In modalità orologio, l'orologio può controllare e <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> i <xref:System.Windows.Controls.MediaState.Manual>metodi di controllo interattivi hanno il controllo quando l'oggetto è . <xref:System.Windows.Controls.MediaElement>questo concorso per il controllo valutando le seguenti priorità.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. Disponibile quando vengono scaricati gli elementi multimediali. In questo modo si garantisce che tutte <xref:System.Windows.Media.MediaClock> le risorse <xref:System.Windows.Controls.MediaElement>multimediali vengano rilasciate per impostazione predefinita, anche quando un oggetto è associato all'oggetto .  
  
2. <xref:System.Windows.Media.MediaClock>. In atto quando <xref:System.Windows.Controls.MediaElement.Clock%2A>i media hanno un . Se il supporto viene <xref:System.Windows.Media.MediaClock> scaricato, l'oggetto <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>avrà effetto finché il è . La modalità orologio esegue sempre <xref:System.Windows.Controls.MediaElement>l'override del comportamento caricato dell'oggetto .  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. Disponibile quando vengono caricati gli elementi multimediali.  
  
4. Metodi di controllo interattivi. In luogo <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>quando è . I metodi di <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A>controllo <xref:System.Windows.Controls.MediaElement.Close%2A>disponibili <xref:System.Windows.Controls.MediaElement.Stop%2A>sono , , , e .  
  
### <a name="displaying-a-mediaelement"></a>Visualizzazione di un oggetto MediaElement  
 Per visualizzare <xref:System.Windows.Controls.MediaElement> un esso deve avere contenuto <xref:System.Windows.FrameworkElement.ActualWidth%2A> per <xref:System.Windows.FrameworkElement.ActualHeight%2A> il rendering e avrà le sue proprietà e impostate su zero fino a quando il contenuto viene caricato. Per contenuti esclusivamente audio, il valore di queste proprietà è sempre zero. Per i contenuti <xref:System.Windows.Controls.MediaElement.MediaOpened> video, una <xref:System.Windows.FrameworkElement.ActualWidth%2A> volta <xref:System.Windows.FrameworkElement.ActualHeight%2A> che l'evento è stato generato e segnalerà le dimensioni del supporto caricato. Ciò significa che fino <xref:System.Windows.Controls.MediaElement> a quando il supporto non [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] viene <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> caricato, il non occuperà alcuno spazio fisico nel meno che non sono impostate le proprietà o .  
  
 L'impostazione di entrambe le <xref:System.Windows.FrameworkElement.Width%2A> proprietà e <xref:System.Windows.FrameworkElement.Height%2A> causerà <xref:System.Windows.Controls.MediaElement>l'estensione del supporto per riempire l'area prevista per il file . Per mantenere le proporzioni originali del <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> supporto, è necessario impostare la proprietà o, ma non entrambe. L'impostazione di entrambe le <xref:System.Windows.FrameworkElement.Width%2A> proprietà e <xref:System.Windows.FrameworkElement.Height%2A> causerà la presenza del supporto in una dimensione fissa dell'elemento che potrebbe non essere auspicabile.  
  
 Per evitare questa situazione, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] può effettuare il preroll del contenuto multimediale. Questa operazione viene <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> eseguita <xref:System.Windows.Controls.MediaState.Play> <xref:System.Windows.Controls.MediaState.Pause>impostando il su o . In <xref:System.Windows.Controls.MediaState.Pause> uno stato, il supporto sarà preroll e presenterà il primo fotogramma. In <xref:System.Windows.Controls.MediaState.Play> uno stato, i media preroll e inizieranno a giocare.  
  
<a name="mediaplayer"></a>
## <a name="mediaplayer-class"></a>Classe MediaPlayer  
 Dove la <xref:System.Windows.Controls.MediaElement> classe è un <xref:System.Windows.Media.MediaPlayer> elemento del framework, <xref:System.Windows.Media.Drawing> la classe è progettata per essere utilizzata negli oggetti. Gli oggetti di disegno vengono utilizzati quando è possibile <xref:System.Windows.Freezable> sacrificare le funzionalità a livello di framework per ottenere vantaggi in termini di prestazioni o quando sono necessarie funzionalità. <xref:System.Windows.Media.MediaPlayer>consente di sfruttare queste funzionalità fornendo al contempo contenuti multimediali nelle applicazioni. Like <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> , può essere utilizzato in modalità <xref:System.Windows.Controls.MediaElement> indipendente o orologio, ma non dispone degli stati scaricato e caricato dell'oggetto. In questo modo si riduce <xref:System.Windows.Media.MediaPlayer>la complessità del controllo di riproduzione dell'oggetto .  
  
### <a name="controlling-mediaplayer"></a>Controllo di un oggetto MediaPlayer  
 Poiché <xref:System.Windows.Media.MediaPlayer> è senza stato, ci sono solo due modi per controllare la riproduzione multimediale.  
  
1. Metodi di controllo interattivi. Sul posto in modalità indipendente (proprietà).`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A>  
  
2. <xref:System.Windows.Media.MediaClock>. In atto quando <xref:System.Windows.Media.MediaPlayer.Clock%2A>i media hanno un .  
  
### <a name="displaying-a-mediaplayer"></a>Visualizzazione di un oggetto MediaPlayer  
 Tecnicamente, <xref:System.Windows.Media.MediaPlayer> un oggetto non può essere visualizzato in quanto non ha alcuna rappresentazione fisica. Tuttavia, può essere utilizzato per <xref:System.Windows.Media.Drawing> presentare i contenuti multimediali in un utilizzando la <xref:System.Windows.Media.VideoDrawing> classe . Nell'esempio seguente viene <xref:System.Windows.Media.VideoDrawing> illustrato l'utilizzo di un per visualizzare i supporti.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ulteriori informazioni sugli oggetti, vedere [Cenni .Drawing Objects Overview.See](drawing-objects-overview.md) the Drawing Objects Overview for more information about <xref:System.Windows.Media.Drawing> objects.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingGroup>
- [Layout](../advanced/layout.md)
- [Argomenti relativi alle procedure](audio-and-video-how-to-topics.md)
