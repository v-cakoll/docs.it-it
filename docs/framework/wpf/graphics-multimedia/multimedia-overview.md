---
title: Panoramica delle funzionalità multimediali
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 42d0d388e859b556d23b7fc81931cd61470ba541
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039807"
---
# <a name="multimedia-overview"></a>Panoramica delle funzionalità multimediali
Le funzionalità multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consentono di integrare audio e video nelle applicazioni per migliorare l'esperienza utente. Questo argomento introduce le funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>   
## <a name="media-api"></a>API multimediali  
 Le classi <xref:System.Windows.Controls.MediaElement> e <xref:System.Windows.Media.MediaPlayer> vengono usate per presentare contenuti audio o video. Queste classi possono essere controllate in modo interattivo o da un orologio. Queste classi possono essere usate nel controllo Microsoft Windows Media Player 10 per la riproduzione di contenuti multimediali. La classe da usare dipende dallo scenario.  
  
 <xref:System.Windows.Controls.MediaElement> è un <xref:System.Windows.UIElement> supportato dal [layout](../advanced/layout.md) e può essere utilizzato come contenuto di molti controlli. È anche utilizzabile in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] nonché nel codice. <xref:System.Windows.Media.MediaPlayer>, d'altra parte, è progettato per gli oggetti <xref:System.Windows.Media.Drawing> e non dispone del supporto per il layout. I supporti caricati utilizzando un <xref:System.Windows.Media.MediaPlayer> possono essere presentati solo utilizzando un <xref:System.Windows.Media.VideoDrawing> o interagendo direttamente con un <xref:System.Windows.Media.DrawingContext>. Impossibile utilizzare <xref:System.Windows.Media.MediaPlayer> in XAML.  
  
 Per altre informazioni sugli oggetti e sul contesto di disegno, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
> Quando si distribuiscono elementi multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Modalità di riproduzione di elementi multimediali  
  
> [!NOTE]
> Sia <xref:System.Windows.Controls.MediaElement> che <xref:System.Windows.Media.MediaPlayer> hanno membri simili. I collegamenti in questa sezione fanno riferimento ai membri della classe <xref:System.Windows.Controls.MediaElement>. Se non specificato diversamente, i membri collegati alla classe <xref:System.Windows.Controls.MediaElement> possono trovarsi anche nella classe <xref:System.Windows.Media.MediaPlayer>.  
  
 Per comprendere la riproduzione di elementi multimediali in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], è necessario conoscere le diverse modalità che è possibile usare per riprodurre questi elementi. Sia <xref:System.Windows.Controls.MediaElement> che <xref:System.Windows.Media.MediaPlayer> possono essere usati in due diverse modalità multimediali, in modalità indipendente e in modalità orologio. La modalità supporto è determinata dalla proprietà <xref:System.Windows.Controls.MediaElement.Clock%2A>. Quando <xref:System.Windows.Controls.MediaElement.Clock%2A> viene `null`, l'oggetto multimediale è in modalità indipendente. Quando il <xref:System.Windows.Controls.MediaElement.Clock%2A> è diverso da null, l'oggetto multimediale è in modalità clock. Per impostazione predefinita, gli oggetti multimediali sono in modalità indipendente.  
  
### <a name="independent-mode"></a>Modalità indipendente  
 In modalità indipendente la riproduzione dei contenuti multimediali dipende dai contenuti stessi. Questa modalità presenta le opzioni seguenti:  
  
- È possibile specificare direttamente il <xref:System.Uri> del supporto.  
  
- È possibile controllare direttamente la riproduzione degli elementi multimediali.  
  
- Le proprietà <xref:System.Windows.Controls.MediaElement.Position%2A> e <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> del supporto possono essere modificate.  
  
 Il supporto viene caricato impostando la proprietà <xref:System.Windows.Controls.MediaElement.Source%2A> dell'oggetto <xref:System.Windows.Controls.MediaElement> o chiamando il metodo <xref:System.Windows.Media.MediaPlayer.Open%2A> dell'oggetto <xref:System.Windows.Media.MediaPlayer>.  
  
 Per controllare la riproduzione degli elementi multimediali in modalità indipendente, è possibile usare i metodi di controllo dell'oggetto multimediale. I metodi di controllo disponibili sono <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>e <xref:System.Windows.Controls.MediaElement.Stop%2A>. Per <xref:System.Windows.Controls.MediaElement>, il controllo interattivo che usa questi metodi è disponibile solo quando il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> è impostato su <xref:System.Windows.Controls.MediaState.Manual>. Questi metodi non sono disponibili quando l'oggetto multimediale è in modalità orologio.  
  
 Vedere [Controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) per un esempio della modalità indipendente.  
  
### <a name="clock-mode"></a>Modalità orologio  
 In modalità orologio, un <xref:System.Windows.Media.MediaTimeline> guida la riproduzione multimediale. La modalità orologio presenta le caratteristiche seguenti:  
  
- Il <xref:System.Uri> del supporto viene impostato indirettamente tramite una <xref:System.Windows.Media.MediaTimeline>.  
  
- La riproduzione degli elementi multimediali può essere controllata dall'orologio. Non è possibile usare i metodi di controllo dell'oggetto multimediale.  
  
- Il supporto viene caricato impostando la proprietà <xref:System.Windows.Media.MediaTimeline.Source%2A> di un oggetto <xref:System.Windows.Media.MediaTimeline>, creando il clock dalla sequenza temporale e assegnando l'orologio all'oggetto multimediale. Anche il supporto viene caricato in questo modo quando un <xref:System.Windows.Media.MediaTimeline> all'interno di una <xref:System.Windows.Media.Animation.Storyboard> è destinato a un <xref:System.Windows.Controls.MediaElement>.  
  
 Per controllare la riproduzione di file multimediali in modalità orologio, è necessario usare i metodi di controllo <xref:System.Windows.Media.Animation.ClockController>. Una <xref:System.Windows.Media.Animation.ClockController> viene ottenuta dalla proprietà <xref:System.Windows.Media.Animation.ClockController> dell'<xref:System.Windows.Media.MediaClock>. Se si tenta di usare i metodi di controllo di un oggetto <xref:System.Windows.Controls.MediaElement> o <xref:System.Windows.Media.MediaPlayer> in modalità orologio, verrà generata un'<xref:System.InvalidOperationException>.  
  
 Per altre informazioni sugli orologi e sulle sequenze temporali, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Vedere [Controllare un MediaElement utilizzando uno storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md) per un esempio della modalità orologio.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Classe MediaElement  
 L'aggiunta di file multimediali a un'applicazione è semplice quanto l'aggiunta di un controllo <xref:System.Windows.Controls.MediaElement> al [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dell'applicazione e la fornitura di un <xref:System.Uri> ai supporti da includere. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]sono supportati tutti i tipi di supporto supportati da Microsoft Windows Media Player 10. Nell'esempio seguente viene illustrato un semplice utilizzo del <xref:System.Windows.Controls.MediaElement> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In questo esempio gli elementi multimediali vengono riprodotti automaticamente appena vengono caricati. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate (inclusa la memoria video). Si tratta del comportamento predefinito dell'oggetto <xref:System.Windows.Controls.MediaElement> ed è controllato dalle proprietà <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>.  
  
### <a name="controlling-a-mediaelement"></a>Controllo di un oggetto MediaElement  
 Le proprietà <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> controllano il comportamento della <xref:System.Windows.Controls.MediaElement> quando <xref:System.Windows.FrameworkElement.IsLoaded%2A> è rispettivamente `true` o `false`. Il <xref:System.Windows.Controls.MediaState> le proprietà sono impostate in modo da influire sul comportamento della riproduzione multimediale. Ad esempio, il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> predefinito è <xref:System.Windows.Controls.MediaState.Play> e il <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> predefinito è <xref:System.Windows.Controls.MediaState.Close>. Ciò significa che non appena viene caricato il <xref:System.Windows.Controls.MediaElement> e il preroll è completo, inizia la riproduzione del supporto. Al termine della riproduzione gli elementi multimediali vengono chiusi e tutte le risorse multimediali rilasciate.  
  
 Le proprietà <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> e <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> non sono l'unico modo per controllare la riproduzione dei supporti. In modalità orologio, l'orologio può controllare il <xref:System.Windows.Controls.MediaElement> e i metodi di controllo interattivo hanno il controllo quando viene <xref:System.Windows.Controls.MediaState.Manual>la <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. <xref:System.Windows.Controls.MediaElement> gestisce questa competizione per il controllo valutando le priorità seguenti.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Disponibile quando vengono scaricati gli elementi multimediali. In questo modo si garantisce che tutte le risorse multimediali vengano rilasciate per impostazione predefinita, anche quando un <xref:System.Windows.Media.MediaClock> è associato al <xref:System.Windows.Controls.MediaElement>.  
  
2. <xref:System.Windows.Media.MediaClock> Sul posto quando il supporto ha un <xref:System.Windows.Controls.MediaElement.Clock%2A>. Se il supporto viene scaricato, le <xref:System.Windows.Media.MediaClock> diverranno effettive purché venga <xref:System.Windows.Controls.MediaState.Manual>la <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. La modalità orologio esegue sempre l'override del comportamento caricato del <xref:System.Windows.Controls.MediaElement>.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Disponibile quando vengono caricati gli elementi multimediali.  
  
4. Metodi di controllo interattivi. Quando <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> viene <xref:System.Windows.Controls.MediaState.Manual>. I metodi di controllo disponibili sono <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>e <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Visualizzazione di un oggetto MediaElement  
 Per visualizzare un <xref:System.Windows.Controls.MediaElement> è necessario che sia presente contenuto di cui eseguire il rendering e che le proprietà <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> siano impostate su zero fino a quando il contenuto non viene caricato. Per contenuti esclusivamente audio, il valore di queste proprietà è sempre zero. Per il contenuto video, una volta generato l'evento <xref:System.Windows.Controls.MediaElement.MediaOpened> <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> segnalerà le dimensioni del supporto caricato. Ciò significa che finché non viene caricato il supporto, il <xref:System.Windows.Controls.MediaElement> non prenderà spazio fisico nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] a meno che non siano impostate le proprietà <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>.  
  
 Impostando entrambe le proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>, il supporto si estenderà per riempire l'area specificata per il <xref:System.Windows.Controls.MediaElement>. Per mantenere le proporzioni originali del supporto, è necessario impostare la proprietà <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>, ma non entrambe. Impostando entrambe le proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>, i supporti saranno presenti in una dimensione di elemento fissa che potrebbe non essere auspicabile.  
  
 Per evitare questa situazione, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] può effettuare il preroll del contenuto multimediale. Questa operazione viene eseguita impostando il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> su <xref:System.Windows.Controls.MediaState.Play> o <xref:System.Windows.Controls.MediaState.Pause>. In uno stato di <xref:System.Windows.Controls.MediaState.Pause>, il supporto viene preregistrato e presenta il primo frame. In uno stato di <xref:System.Windows.Controls.MediaState.Play>, i supporti vengono preroll e iniziano a essere riprodotti.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Classe MediaPlayer  
 Laddove la classe <xref:System.Windows.Controls.MediaElement> è un elemento del Framework, la classe <xref:System.Windows.Media.MediaPlayer> è progettata per essere utilizzata negli oggetti <xref:System.Windows.Media.Drawing>. Gli oggetti Drawing vengono usati quando è possibile sacrificare le funzionalità a livello di Framework per ottenere vantaggi in termini di prestazioni o quando è necessario <xref:System.Windows.Freezable> funzionalità. <xref:System.Windows.Media.MediaPlayer> consente di sfruttare queste funzionalità fornendo contenuti multimediali nelle applicazioni. Analogamente a <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> può essere utilizzato in modalità indipendente o orologio, ma non dispone degli stati scaricati e caricati dell'oggetto <xref:System.Windows.Controls.MediaElement>. In questo modo si riduce la complessità del controllo della riproduzione del <xref:System.Windows.Media.MediaPlayer>.  
  
### <a name="controlling-mediaplayer"></a>Controllo di un oggetto MediaPlayer  
 Poiché <xref:System.Windows.Media.MediaPlayer> è senza stato, esistono solo due modi per controllare la riproduzione dei supporti.  
  
1. Metodi di controllo interattivi. Sul posto in modalità indipendente (`null`<xref:System.Windows.Media.MediaPlayer.Clock%2A> proprietà).  
  
2. <xref:System.Windows.Media.MediaClock> Sul posto quando il supporto ha un <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### <a name="displaying-a-mediaplayer"></a>Visualizzazione di un oggetto MediaPlayer  
 Tecnicamente, non è possibile visualizzare un <xref:System.Windows.Media.MediaPlayer> perché non ha alcuna rappresentazione fisica. Può tuttavia essere usato per presentare i supporti in un <xref:System.Windows.Media.Drawing> usando la classe <xref:System.Windows.Media.VideoDrawing>. Nell'esempio seguente viene illustrato l'utilizzo di un <xref:System.Windows.Media.VideoDrawing> per visualizzare i supporti.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ulteriori informazioni sugli oggetti <xref:System.Windows.Media.Drawing>, vedere [Cenni preliminari](drawing-objects-overview.md) sugli oggetti Drawing.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingGroup>
- [Layout](../advanced/layout.md)
- [Procedure relative alle proprietà](audio-and-video-how-to-topics.md)
