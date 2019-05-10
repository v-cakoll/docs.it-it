---
title: Panoramica delle funzionalità multimediali
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 95456eb542182d2e3c10cd07e4571a16a2c91d0a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625302"
---
# <a name="multimedia-overview"></a>Panoramica delle funzionalità multimediali
Le funzionalità multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consentono di integrare audio e video nelle applicazioni per migliorare l'esperienza utente. Questo argomento introduce le funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>   
## <a name="media-api"></a>API multimediali  
 Il <xref:System.Windows.Controls.MediaElement> e <xref:System.Windows.Media.MediaPlayer> classi vengono usate per presentare contenuto audio o video. Queste classi possono essere controllate in modo interattivo o da un orologio. È possibile usare queste classi sul controllo [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 per la riproduzione multimediale. La classe da usare dipende dallo scenario.  
  
 <xref:System.Windows.Controls.MediaElement> è un <xref:System.Windows.UIElement> che è supportato per il [Layout](../advanced/layout.md) e può essere utilizzato come contenuto di molti controlli. È anche utilizzabile in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] nonché nel codice. <xref:System.Windows.Media.MediaPlayer>, d'altra parte, è progettato per <xref:System.Windows.Media.Drawing> degli oggetti e non offre il supporto di layout. Elementi multimediali caricati usando un <xref:System.Windows.Media.MediaPlayer> possono essere presentati solo tramite un <xref:System.Windows.Media.VideoDrawing> o interagendo direttamente con un <xref:System.Windows.Media.DrawingContext>. <xref:System.Windows.Media.MediaPlayer> non è possibile usare in XAML.  
  
 Per altre informazioni sugli oggetti e sul contesto di disegno, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
>  Quando si distribuiscono elementi multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Modalità di riproduzione di elementi multimediali  
  
> [!NOTE]
>  Entrambe <xref:System.Windows.Controls.MediaElement> e <xref:System.Windows.Media.MediaPlayer> dispongono di membri simili. I collegamenti in questa sezione si riferiscono al <xref:System.Windows.Controls.MediaElement> membri della classe. Se non specificato diversamente, i membri collegati nella <xref:System.Windows.Controls.MediaElement> classe sono disponibili anche nel <xref:System.Windows.Media.MediaPlayer> classe.  
  
 Per comprendere la riproduzione di elementi multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], è necessario conoscere le diverse modalità che è possibile usare per riprodurre questi elementi. Entrambe <xref:System.Windows.Controls.MediaElement> e <xref:System.Windows.Media.MediaPlayer> può essere usato in due modalità multimediali diverse, la modalità indipendente e la modalità orologio. La modalità multimediale è determinata dal <xref:System.Windows.Controls.MediaElement.Clock%2A> proprietà. Quando <xref:System.Windows.Controls.MediaElement.Clock%2A> è `null`, l'oggetto multimediale si trova in modalità indipendente. Quando il <xref:System.Windows.Controls.MediaElement.Clock%2A> è diverso da null, l'oggetto multimediale si trova in modalità orologio. Per impostazione predefinita, gli oggetti multimediali sono in modalità indipendente.  
  
### <a name="independent-mode"></a>Modalità indipendente  
 In modalità indipendente la riproduzione dei contenuti multimediali dipende dai contenuti stessi. Questa modalità presenta le opzioni seguenti:  
  
- Dell'elemento multimediale <xref:System.Uri> possono essere specificati direttamente.  
  
- È possibile controllare direttamente la riproduzione degli elementi multimediali.  
  
- Dell'elemento multimediale <xref:System.Windows.Controls.MediaElement.Position%2A> e <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> proprietà possono essere modificate.  
  
 Contenuti multimediali vengono caricati impostando il <xref:System.Windows.Controls.MediaElement> dell'oggetto <xref:System.Windows.Controls.MediaElement.Source%2A> proprietà oppure chiamando il <xref:System.Windows.Media.MediaPlayer> dell'oggetto <xref:System.Windows.Media.MediaPlayer.Open%2A> (metodo).  
  
 Per controllare la riproduzione degli elementi multimediali in modalità indipendente, è possibile usare i metodi di controllo dell'oggetto multimediale. I metodi di controllo disponibili sono <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, e <xref:System.Windows.Controls.MediaElement.Stop%2A>. Per la <xref:System.Windows.Controls.MediaElement>, il controllo interattivo usando questi metodi è disponibile solo quando il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è impostata su <xref:System.Windows.Controls.MediaState.Manual>. Questi metodi non sono disponibili quando l'oggetto multimediale è in modalità orologio.  
  
 Vedere [Controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) per un esempio della modalità indipendente.  
  
### <a name="clock-mode"></a>Modalità orologio  
 In modalità orologio, un <xref:System.Windows.Media.MediaTimeline> avvia la riproduzione multimediale. La modalità orologio presenta le caratteristiche seguenti:  
  
- Dell'elemento multimediale <xref:System.Uri> è impostata indirettamente tramite una <xref:System.Windows.Media.MediaTimeline>.  
  
- La riproduzione degli elementi multimediali può essere controllata dall'orologio. Non è possibile usare i metodi di controllo dell'oggetto multimediale.  
  
- Contenuti multimediali vengono caricati impostando un <xref:System.Windows.Media.MediaTimeline> dell'oggetto <xref:System.Windows.Media.MediaTimeline.Source%2A> proprietà, creando l'orologio dalla sequenza temporale e assegnandolo all'oggetto multimediale. Contenuti multimediali vengono caricati anche in questo modo quando una <xref:System.Windows.Media.MediaTimeline> all'interno di un <xref:System.Windows.Media.Animation.Storyboard> destinazioni un <xref:System.Windows.Controls.MediaElement>.  
  
 Per controllare la riproduzione multimediale in modalità orologio, il <xref:System.Windows.Media.Animation.ClockController> metodi di controllo devono essere utilizzati. Oggetto <xref:System.Windows.Media.Animation.ClockController> ottenuto dal <xref:System.Windows.Media.Animation.ClockController> proprietà del <xref:System.Windows.Media.MediaClock>. Se si prova a usare i metodi di controllo di un <xref:System.Windows.Controls.MediaElement> oppure <xref:System.Windows.Media.MediaPlayer> dell'oggetto mentre è in modalità orologio, un <xref:System.InvalidOperationException> verrà generata.  
  
 Per altre informazioni sugli orologi e sulle sequenze temporali, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Vedere [Controllare un MediaElement utilizzando uno storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md) per un esempio della modalità orologio.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Classe MediaElement  
 Aggiunta di elementi multimediali a un'applicazione è semplice quanto l'aggiunta di un <xref:System.Windows.Controls.MediaElement> il controllo al [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dell'applicazione e fornendo un <xref:System.Uri> nei supporti che si desidera includere. Tutti i tipi di elementi multimediali supportati da [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 sono supportati in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. L'esempio seguente illustra un uso semplificato della <xref:System.Windows.Controls.MediaElement> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In questo esempio gli elementi multimediali vengono riprodotti automaticamente appena vengono caricati. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate (inclusa la memoria video). Si tratta del comportamento predefinito del <xref:System.Windows.Controls.MediaElement> dell'oggetto ed è controllato dalle <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> proprietà.  
  
### <a name="controlling-a-mediaelement"></a>Controllo di un oggetto MediaElement  
 Il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> proprietà controllano il comportamento del <xref:System.Windows.Controls.MediaElement> quando <xref:System.Windows.FrameworkElement.IsLoaded%2A> viene `true` o `false`, rispettivamente. Il <xref:System.Windows.Controls.MediaState> le proprietà vengono impostate per influire sul comportamento della riproduzione multimediale. Ad esempio, il valore predefinito <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> viene <xref:System.Windows.Controls.MediaState.Play> e il valore predefinito <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Close>. Ciò significa che non appena il <xref:System.Windows.Controls.MediaElement> viene caricato e il preroll è completo, il supporto inizia da riprodurre. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate.  
  
 Il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> proprietà non sono l'unico modo per controllare la riproduzione multimediale. In modalità orologio, l'orologio può controllare la <xref:System.Windows.Controls.MediaElement> e i metodi per il controllo interattivo dispone di alcun controllo quando il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Manual>. <xref:System.Windows.Controls.MediaElement> gestisce la concorrenza per il controllo tramite la valutazione delle proprietà seguenti.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. Disponibile quando vengono scaricati gli elementi multimediali. Ciò garantisce che tutte le risorse multimediali siano rilasciate per impostazione predefinita, anche quando un <xref:System.Windows.Media.MediaClock> è associato il <xref:System.Windows.Controls.MediaElement>.  
  
2. <xref:System.Windows.Media.MediaClock>. Disponibile quando i supporti hanno un <xref:System.Windows.Controls.MediaElement.Clock%2A>. Se i supporti vengono scaricati, il <xref:System.Windows.Media.MediaClock> saranno effettive, purché la <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Manual>. La modalità orologio esegue sempre l'override del comportamento caricato del <xref:System.Windows.Controls.MediaElement>.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. Disponibile quando vengono caricati gli elementi multimediali.  
  
4. Metodi di controllo interattivi. In inserire quando <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è <xref:System.Windows.Controls.MediaState.Manual>. I metodi di controllo disponibili sono <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, e <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Visualizzazione di un oggetto MediaElement  
 Per visualizzare un <xref:System.Windows.Controls.MediaElement> deve avere il contenuto per il rendering e avrà relativi <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> proprietà impostate su zero fino a quando non viene caricato il contenuto. Per contenuti esclusivamente audio, il valore di queste proprietà è sempre zero. Per contenuti video, una volta il <xref:System.Windows.Controls.MediaElement.MediaOpened> evento è stato generato il <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> segnaleranno la dimensione dei file multimediali caricati. Ciò significa che fino a quando non viene caricato supporti, il <xref:System.Windows.Controls.MediaElement> non occuperà alcuno spazio fisico nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] a meno che non la <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> proprietà vengono impostate.  
  
 Se si impostano entrambe le <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà genererà adattata per riempire l'area specificata per il supporto di <xref:System.Windows.Controls.MediaElement>. Per conservare le proporzioni originali del contenuto multimediale, ovvero il <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> della proprietà deve essere impostato, ma non entrambi. Se si impostano entrambe le <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà provocherà il supporto per la presentazione in una dimensione fissa che potrebbe non essere appropriata.  
  
 Per evitare questa situazione, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] può effettuare il preroll del contenuto multimediale. Questa operazione viene eseguita impostando il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> a uno <xref:System.Windows.Controls.MediaState.Play> o <xref:System.Windows.Controls.MediaState.Pause>. In un <xref:System.Windows.Controls.MediaState.Pause> lo stato, il supporto verrà effettuato il preroll e presenterà il primo fotogramma. In un <xref:System.Windows.Controls.MediaState.Play> lo stato, il supporto verrà effettuato il preroll e iniziare la riproduzione.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Classe MediaPlayer  
 Mentre il <xref:System.Windows.Controls.MediaElement> classe è un elemento del framework, il <xref:System.Windows.Media.MediaPlayer> classe è progettata per essere usato in <xref:System.Windows.Media.Drawing> oggetti. Gli oggetti Drawing vengono usati quando è possibile sacrificare le funzionalità a livello di framework per migliorare le prestazioni o quando è necessario <xref:System.Windows.Freezable> funzionalità. <xref:System.Windows.Media.MediaPlayer> Consente di sfruttare i vantaggi di queste funzionalità e di fornire contenuti multimediali nelle applicazioni. Ad esempio <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> può essere usato in indipendente o orologio non modalità ma non hanno il <xref:System.Windows.Controls.MediaElement> oggetto scaricati e caricati gli stati. Ciò riduce la complessità del controllo della riproduzione di <xref:System.Windows.Media.MediaPlayer>.  
  
### <a name="controlling-mediaplayer"></a>Controllo di un oggetto MediaPlayer  
 Poiché <xref:System.Windows.Media.MediaPlayer> è senza stato, sono disponibili solo due modi per controllare la riproduzione multimediale.  
  
1. Metodi di controllo interattivi. Disponibili nella modalità indipendente (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> proprietà).  
  
2. <xref:System.Windows.Media.MediaClock>. Disponibile quando i supporti hanno un <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### <a name="displaying-a-mediaplayer"></a>Visualizzazione di un oggetto MediaPlayer  
 Tecnicamente, un <xref:System.Windows.Media.MediaPlayer> non possono essere visualizzati poiché non dispone di alcuna rappresentazione fisica. Tuttavia, può essere utilizzato per presentare i file multimediali in un <xref:System.Windows.Media.Drawing> utilizzando il <xref:System.Windows.Media.VideoDrawing> classe. Nell'esempio seguente viene illustrato l'utilizzo di un <xref:System.Windows.Media.VideoDrawing> per visualizzare gli elementi multimediali.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Vedere le [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md) per altre informazioni su <xref:System.Windows.Media.Drawing> oggetti.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingGroup>
- [Layout](../advanced/layout.md)
- [Procedure relative alle proprietà](audio-and-video-how-to-topics.md)
