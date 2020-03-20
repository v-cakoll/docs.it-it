---
title: Suggerimenti sulle animazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting [WPF], animation
- animations [WPF], FillBehavior property
- troubleshooting animation [WPF]
- animating objects [WPF], troubleshooting
- animation tips and tricks [WPF]
- tips and tricks [WPF], animation
- performance troubleshooting [WPF], animation
- animations [WPF], use of system resources
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
ms.openlocfilehash: 6b540448599c1e1083ed367a312ef60fceacd0d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187642"
---
# <a name="animation-tips-and-tricks"></a>Suggerimenti sulle animazioni
Quando si lavora con le animazioni in WPFWPF, sono disponibili una serie di suggerimenti e trucchi che possono migliorare le prestazioni delle animazioni e risparmiare frustrazione.  
  
<a name="generalissuessection"></a>
## <a name="general-issues"></a>Problemi generali  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Blocco di una barra di scorrimento o di un dispositivo di scorrimento se si anima la relativa posizione  
 Se animate la posizione di una barra di scorrimento <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> o di un cursore utilizzando un'animazione che ha un di (valore predefinito), l'utente non sarà più in grado di spostare la barra di scorrimento o il dispositivo di scorrimento. Ciò è dovuto al fatto che, anche se l'animazione è terminata, l'override del valore di base della proprietà di destinazione è ancora in corso. Per impedire all'animazione di eseguire l'override del valore <xref:System.Windows.Media.Animation.FillBehavior> corrente <xref:System.Windows.Media.Animation.FillBehavior.Stop>della proprietà, rimuoverla o assegnarle un valore di . Per ulteriori informazioni e un esempio, vedere [Impostare una proprietà dopo averla animata con uno Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Animazione dell'output di un'animazione senza alcun effetto  
 Non è possibile animare un oggetto che rappresenta l'output di un'altra animazione. Ad esempio, se <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> si utilizza <xref:System.Windows.Shapes.Shape.Fill%2A> un <xref:System.Windows.Shapes.Rectangle> per <xref:System.Windows.Media.RadialGradientBrush> animare il di un da a a , <xref:System.Windows.Media.SolidColorBrush>non è possibile animare le proprietà di <xref:System.Windows.Media.RadialGradientBrush> o <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Impossibile modificare il valore di una proprietà dopo averla animata  
 In alcuni casi può sembrare che non sia possibile modificare il valore di una proprietà dopo che è stata animata, anche dopo il termine dell'animazione. Ciò è dovuto al fatto che, anche se l'animazione è terminata, l'override del valore di base della proprietà è ancora in corso. Per impedire all'animazione di eseguire l'override del valore <xref:System.Windows.Media.Animation.FillBehavior> corrente <xref:System.Windows.Media.Animation.FillBehavior.Stop>della proprietà, rimuoverla o assegnarle un valore di . Per ulteriori informazioni e un esempio, vedere [Impostare una proprietà dopo averla animata con uno Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Modifica di una sequenza temporale senza alcun effetto  
 Anche <xref:System.Windows.Media.Animation.Timeline> se la maggior parte delle proprietà sono animabili <xref:System.Windows.Media.Animation.Timeline> e possono essere associate a dati, la modifica dei valori delle proprietà di un oggetto attivo sembra non avere alcun effetto. Questo perché, quando <xref:System.Windows.Media.Animation.Timeline> un viene iniziato, il sistema <xref:System.Windows.Media.Animation.Timeline> di temporizzazione <xref:System.Windows.Media.Animation.Clock> crea una copia di e lo utilizza per creare un oggetto. La modifica dell'originale non ha alcun effetto sulla copia del sistema.  
  
 Affinché <xref:System.Windows.Media.Animation.Timeline> un oggetto rifletta le modifiche, il relativo orologio deve essere rigenerato e utilizzato per sostituire l'orologio creato in precedenza. Gli orologi non vengono rigenerati automaticamente. Di seguito vengono indicate diverse modalità per applicare le modifiche alla sequenza temporale:  
  
- Se la sequenza temporale <xref:System.Windows.Media.Animation.Storyboard>è o appartiene a un oggetto , <xref:System.Windows.Media.Animation.BeginStoryboard> è <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> possibile fare in modo che rifletta le modifiche riapplicando il relativo storyboard utilizzando un metodo o . Come effetto collaterale, l'animazione viene riavviata. Nel codice, è <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> possibile utilizzare il metodo per spostare lo storyboard alla posizione precedente.  
  
- Se è stata applicata un'animazione direttamente a una proprietà utilizzando il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo , chiamare nuovamente il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo e passargli l'animazione che è stata modificata.  
  
- Se si lavora direttamente a livello di orologio, creare e applicare un nuovo set di orologi e usarli per sostituire il set di orologi generati in precedenza.  
  
 Per ulteriori informazioni sulle sequenze temporali e sugli orologi, vedere Cenni preliminari sul [sistema di animazione e temporizzazione](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>Funzionamento imprevisto di FillBehavior.Stop  
 Ci sono momenti <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> in <xref:System.Windows.Media.Animation.FillBehavior.Stop> cui l'impostazione della proprietà sembra non avere alcun effetto, <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> ad <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>esempio quando un'animazione "passa" a un'altra perché ha un'impostazione di .  
  
 Nell'esempio riportato <xref:System.Windows.Shapes.Rectangle> di <xref:System.Windows.Media.TranslateTransform>seguito vengono creati , <xref:System.Windows.Controls.Canvas>a e a . L'animazione <xref:System.Windows.Media.TranslateTransform> verrà <xref:System.Windows.Shapes.Rectangle> animata per spostare il percorso del <xref:System.Windows.Controls.Canvas>file .  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Negli esempi di questa sezione vengono utilizzati gli <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> oggetti precedenti per illustrare diversi casi in cui la proprietà non si comporta come previsto.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" e HandoffBehavior con animazioni multiple  
 A volte sembra che un'animazione ignori la sua <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà quando viene sostituita da una seconda animazione. Si supponga l'esempio <xref:System.Windows.Media.Animation.Storyboard> seguente, che crea due <xref:System.Windows.Media.TranslateTransform> oggetti e li utilizza per animare lo stesso illustrato nell'esempio precedente.  
  
 Il <xref:System.Windows.Media.Animation.Storyboard>primo `B1`, , <xref:System.Windows.Media.TranslateTransform.X%2A> aggiunge <xref:System.Windows.Media.TranslateTransform> un'animazione alla proprietà di da 0 a 350, che sposta il rettangolo di 350 pixel verso destra. Quando l'animazione raggiunge la fine della <xref:System.Windows.Media.TranslateTransform.X%2A> durata e interrompe la riproduzione, la proprietà torna al valore originale, 0. Il rettangolo di conseguenza si sposta a destra di 350 pixel e quindi torna alla posizione originale.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Il <xref:System.Windows.Media.Animation.Storyboard>secondo `B2`, , <xref:System.Windows.Media.TranslateTransform.X%2A> aggiunge anche <xref:System.Windows.Media.TranslateTransform>un'animazione alla proprietà dello stesso oggetto . Poiché <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> viene impostata solo <xref:System.Windows.Media.Animation.Storyboard> la proprietà dell'animazione in questo, l'animazione utilizza il valore corrente della proprietà che aggiunge un'animazione come valore iniziale.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Se si fa clic sul <xref:System.Windows.Media.Animation.Storyboard> secondo pulsante durante la riproduzione del primo, è possibile che si verifichi il seguente comportamento:  
  
1. Il primo storyboard termina e riporta il rettangolo alla <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> posizione <xref:System.Windows.Media.Animation.FillBehavior.Stop>originale, poiché l'animazione ha un di .  
  
2. Il secondo storyboard viene applicato e viene animato dalla posizione corrente, da 0 a 500.  
  
 **Questa situazioni non è quella che si verifica.** Il rettangolo infatti non torna alla posizione originale ma continua a spostarsi a destra. Ciò accade perché la seconda animazione usa il valore corrente della prima animazione come valore iniziale e viene eseguita da tale valore fino a 500. Quando la seconda animazione sostituisce la prima perché viene utilizzata la <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> seconda animazione, la <xref:System.Windows.Media.Animation.FillBehavior> prima animazione non è importante.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior ed evento Completed  
 Gli esempi successivi dimostrano <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> un altro scenario in cui l'oggetto sembra non avere alcun effetto. Anche in questo caso, l'esempio utilizza uno Storyboard per animare la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà del <xref:System.Windows.Media.TranslateTransform> from 0 a 350. Tuttavia, questa volta l'esempio si registra per l'evento. <xref:System.Windows.Media.Animation.Timeline.Completed>  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Il <xref:System.Windows.Media.Animation.Timeline.Completed> gestore <xref:System.Windows.Media.Animation.Storyboard> eventi ne avvia un altro che aggiunge un'animazione alla stessa proprietà dal valore corrente a 500.The event handler starts another that animates the same property from its current value to 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Di seguito è riportato il <xref:System.Windows.Media.Animation.Storyboard> markup che definisce il secondo come risorsa.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Quando si <xref:System.Windows.Media.Animation.Storyboard>esegue l'oggetto <xref:System.Windows.Media.TranslateTransform.X%2A> , <xref:System.Windows.Media.TranslateTransform> è possibile che la proprietà di <xref:System.Windows.Media.Animation.FillBehavior> venga <xref:System.Windows.Media.Animation.FillBehavior.Stop>animata da 0 a 350, quindi ripristina 0 al termine dell'operazione (poiché dispone di un'impostazione di ) e quindi dell'animazione da 0 a 500. Al contrario, l'animazione <xref:System.Windows.Media.TranslateTransform> da 0 a 350 e quindi a 500.  
  
 Ciò è dovuto all'ordine in cui WPFWPF genera eventi e perché i valori delle proprietà vengono memorizzati nella cache e non vengono ricalcolati a meno che la proprietà non venga invalidata. L'evento <xref:System.Windows.Media.Animation.Timeline.Completed> viene elaborato per primo perché è stato <xref:System.Windows.Media.Animation.Storyboard>attivato dalla sequenza temporale radice (la prima ). In questo momento, la proprietà restituisce ancora il <xref:System.Windows.Media.TranslateTransform.X%2A> valore animato perché non è stata ancora invalidata. Il <xref:System.Windows.Media.Animation.Storyboard> secondo utilizza il valore memorizzato nella cache come valore iniziale e inizia l'animazione.  
  
<a name="performancesection"></a>
## <a name="performance"></a>Prestazioni  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Continuazione dell'esecuzione delle animazioni dopo lo spostamento da una pagina  
 Quando si esce <xref:System.Windows.Controls.Page> da un che contiene animazioni in <xref:System.Windows.Controls.Page> esecuzione, tali animazioni continueranno a essere riprodotte fino a quando il viene sottoposto a garbage collection. A seconda del sistema di navigazione in uso, una pagina da cui ci si è spostati potrebbe rimanere in memoria per un tempo indefinito, usando le risorse con le relative animazioni. Ciò è più evidente quando una pagina contiene animazioni in esecuzione continua.  
  
 Per questo motivo, è consigliabile <xref:System.Windows.FrameworkElement.Unloaded> usare l'evento per rimuovere le animazioni quando si esce da una pagina.  
  
 Per rimuovere un'animazione, sono disponibili modi diversi. Le tecniche seguenti possono essere utilizzate per <xref:System.Windows.Media.Animation.Storyboard>rimuovere le animazioni che appartengono a un file .  
  
- Per rimuovere <xref:System.Windows.Media.Animation.Storyboard> un utente avviato con un trigger di evento, vedere [Procedura: rimuovere uno storyboard](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
- Per utilizzare il <xref:System.Windows.Media.Animation.Storyboard>codice per <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> rimuovere un oggetto , vedere il metodo .  
  
 La tecnica successiva può essere usata indipendentemente dalla modalità di avviamento dell'animazione.  
  
- Per rimuovere animazioni da una <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> proprietà specifica, usare il metodo . Specificare la proprietà animata `null` come primo parametro e come secondo. In questo modo tutti gli orologi dell'animazione vengono rimossi dalla proprietà.  
  
 Per ulteriori informazioni sui diversi modi per animare le proprietà, vedere Cenni preliminari sulle tecniche di [animazione](property-animation-techniques-overview.md)delle proprietà .  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Uso di Compose HandoffBehavior con risorse di sistema  
 Quando si <xref:System.Windows.Media.Animation.Storyboard>applica <xref:System.Windows.Media.Animation.AnimationTimeline>un <xref:System.Windows.Media.Animation.AnimationClock> oggetto , <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>, <xref:System.Windows.Media.Animation.Clock> o a una proprietà utilizzando l'oggetto , tutti gli oggetti precedentemente associati a tale proprietà continuano a utilizzare le risorse di sistema; il sistema di temporizzazione non rimuoverà automaticamente questi orologi.  
  
 Per evitare problemi di prestazioni quando si <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>applica un numero elevato di orologi utilizzando , è necessario rimuovere i clock di composizione dalla proprietà animata dopo il completamento. Esistono diverse modalità di rimozione di un orologio.  
  
- Per rimuovere tutti gli orologi da <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> una proprietà, utilizzare il metodo o dell'oggetto animato. Specificare la proprietà animata `null` come primo parametro e come secondo. In questo modo tutti gli orologi dell'animazione vengono rimossi dalla proprietà.  
  
- Per rimuovere <xref:System.Windows.Media.Animation.AnimationClock> un oggetto specifico da un <xref:System.Windows.Media.Animation.Clock.Controller%2A> elenco <xref:System.Windows.Media.Animation.AnimationClock> di orologi, utilizzare la proprietà di per recuperare un <xref:System.Windows.Media.Animation.ClockController>oggetto , quindi chiamare il <xref:System.Windows.Media.Animation.ClockController.Remove%2A> metodo dell'oggetto <xref:System.Windows.Media.Animation.ClockController>. Questa operazione viene <xref:System.Windows.Media.Animation.Clock.Completed> in genere eseguita nel gestore eventi per un orologio. Si noti che solo i <xref:System.Windows.Media.Animation.ClockController>clock radice possono essere controllati da un ; la <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà di un `null`orologio figlio restituirà . Si noti <xref:System.Windows.Media.Animation.Clock.Completed> inoltre che l'evento non verrà chiamato se la durata effettiva dell'orologio è per sempre.  In tal caso, l'utente dovrà <xref:System.Windows.Media.Animation.ClockController.Remove%2A>determinare quando chiamare .  
  
 Si tratta principalmente di un problema relativo alle animazioni su oggetti di lunga durata.  Quando un oggetto viene raccolto nel Garbage Collector, anche gli orologi vengono disconnessi e raccolti nel Garbage Collector stesso.  
  
 Per ulteriori informazioni sugli oggetti orologio, vedere Cenni preliminari sul [sistema di animazione e temporizzazione](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
