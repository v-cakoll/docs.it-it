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
ms.openlocfilehash: 3a22c83eb739a735d42fa0f670716a0e75bbd54c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020270"
---
# <a name="animation-tips-and-tricks"></a>Suggerimenti sulle animazioni
Quando si lavora con le animazioni in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], esistono una serie di suggerimenti e consigli che è possono apportare le animazioni offrono prestazioni migliori e migliorano.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>Problemi generali  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Blocco di una barra di scorrimento o di un dispositivo di scorrimento se si anima la relativa posizione  
 Se si anima la posizione di una barra di scorrimento o un dispositivo di scorrimento con un'animazione con una <xref:System.Windows.Media.Animation.FillBehavior> di <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (valore predefinito), l'utente non saranno in grado di spostare la barra di scorrimento o un dispositivo di scorrimento. Ciò è dovuto al fatto che, anche se l'animazione è terminata, l'override del valore di base della proprietà di destinazione è ancora in corso. Per interrompere l'animazione di ignorare il valore della proprietà corrente, rimuoverlo o fornirle un <xref:System.Windows.Media.Animation.FillBehavior> di <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Per altre informazioni e un esempio, vedere [impostare una proprietà dopo averla animata con uno Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Animazione dell'output di un'animazione senza alcun effetto  
 Non è possibile animare un oggetto che rappresenta l'output di un'altra animazione. Ad esempio, se si usa un' <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> per aggiungere un'animazione la <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle> da un <xref:System.Windows.Media.RadialGradientBrush> a un <xref:System.Windows.Media.SolidColorBrush>, non è possibile animare le proprietà del <xref:System.Windows.Media.RadialGradientBrush> o <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Impossibile modificare il valore di una proprietà dopo averla animata  
 In alcuni casi può sembrare che non sia possibile modificare il valore di una proprietà dopo che è stata animata, anche dopo il termine dell'animazione. Ciò è dovuto al fatto che, anche se l'animazione è terminata, l'override del valore di base della proprietà è ancora in corso. Per interrompere l'animazione di ignorare il valore della proprietà corrente, rimuoverlo o fornirle un <xref:System.Windows.Media.Animation.FillBehavior> di <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Per altre informazioni e un esempio, vedere [impostare una proprietà dopo averla animata con uno Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Modifica di una sequenza temporale senza alcun effetto  
 Sebbene la maggior parte degli <xref:System.Windows.Media.Animation.Timeline> sono di proprietà animata e possa essere associata a dati, modificando i valori di proprietà di un oggetto attivo <xref:System.Windows.Media.Animation.Timeline> sembra non produrre alcun effetto. Infatti, quando un <xref:System.Windows.Media.Animation.Timeline> è iniziata, il sistema di temporizzazione crea una copia del <xref:System.Windows.Media.Animation.Timeline> e lo usa per creare un <xref:System.Windows.Media.Animation.Clock> oggetto. La modifica dell'originale non ha alcun effetto sulla copia del sistema.  
  
 Per un <xref:System.Windows.Media.Animation.Timeline> per riflettere le modifiche, l'orologio deve essere rigenerato e usato per sostituire l'orologio creato in precedenza. Gli orologi non vengono rigenerati automaticamente. Di seguito vengono indicate diverse modalità per applicare le modifiche alla sequenza temporale:  
  
- Se la sequenza temporale è o appartiene a un <xref:System.Windows.Media.Animation.Storyboard>, è possibile renderlo riflettere le modifiche tramite una nuova applicazione dello storyboard, utilizzando un <xref:System.Windows.Media.Animation.BeginStoryboard> o il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> (metodo). Come effetto collaterale, l'animazione viene riavviata. Nel codice, è possibile usare il <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> eseguire il metodo per riportare lo storyboard alla posizione precedente.  
  
- Se è applicata un'animazione direttamente a una proprietà utilizzando il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo, chiamare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> nuovo metodo e passare l'animazione che è stato modificato.  
  
- Se si lavora direttamente a livello di orologio, creare e applicare un nuovo set di orologi e usarli per sostituire il set di orologi generati in precedenza.  
  
 Per altre informazioni sulle sequenze temporali e orologi, vedere [Panoramica sistema di temporizzazione e animazione](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>Funzionamento imprevisto di FillBehavior.Stop  
 Esistono situazioni in quando si imposta il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà <xref:System.Windows.Media.Animation.FillBehavior.Stop> sembra non produrre alcun effetto, ad esempio quando un'animazione "Invia" a un'altra perché ha un <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> l'impostazione di <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.  
  
 L'esempio seguente crea una <xref:System.Windows.Controls.Canvas>, una <xref:System.Windows.Shapes.Rectangle> e un <xref:System.Windows.Media.TranslateTransform>. Il <xref:System.Windows.Media.TranslateTransform> verrà animato per spostare il <xref:System.Windows.Shapes.Rectangle> tutto il <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Gli esempi in questa sezione usano gli oggetti precedenti per illustrare numerosi casi in cui il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà non è quello previsto per.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" e HandoffBehavior con animazioni multiple  
 In alcuni casi può sembrare un'animazione ignori relativo <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà quando è sostituita da una seconda animazione. L'esempio seguente, che vengono creati due <xref:System.Windows.Media.Animation.Storyboard> degli oggetti e li usa per animare lo stesso <xref:System.Windows.Media.TranslateTransform> illustrato nell'esempio precedente.  
  
 Il primo <xref:System.Windows.Media.Animation.Storyboard>, `B1`, anima la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà del <xref:System.Windows.Media.TranslateTransform> da 0 a 350, che consente di spostare il rettangolo di 350 pixel a destra. Quando si raggiunge la fine della durata e si interrompe, l'animazione di <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà viene ripristinato il valore originale, 0. Il rettangolo di conseguenza si sposta a destra di 350 pixel e quindi torna alla posizione originale.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 La seconda <xref:System.Windows.Media.Animation.Storyboard>, `B2`, anche anima la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà della stessa <xref:System.Windows.Media.TranslateTransform>. Poiché solo il <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà di animazione in <xref:System.Windows.Media.Animation.Storyboard> è impostato, l'animazione Usa il valore corrente della proprietà che anima come valore iniziale.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Se si fa clic sul secondo pulsante mentre il primo <xref:System.Windows.Media.Animation.Storyboard> viene riprodotto, è prevedibile il comportamento seguente:  
  
1. Il primo storyboard termina e invia il rettangolo torna alla posizione originale, in quanto l'animazione dispone di un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> di <xref:System.Windows.Media.Animation.FillBehavior.Stop>.  
  
2. Il secondo storyboard viene applicato e viene animato dalla posizione corrente, da 0 a 500.  
  
 **Questa situazioni non è quella che si verifica.** Il rettangolo infatti non torna alla posizione originale ma continua a spostarsi a destra. Ciò accade perché la seconda animazione usa il valore corrente della prima animazione come valore iniziale e viene eseguita da tale valore fino a 500. Quando la seconda animazione sostituisce la prima perché il <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> viene usato il <xref:System.Windows.Media.Animation.FillBehavior> della prima animazione non è rilevante.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior ed evento Completed  
 Negli esempi successivi illustrano un altro scenario in cui il <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> sembra non produrre alcun effetto. Anche in questo caso l'esempio usa uno Storyboard per animare la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà del <xref:System.Windows.Media.TranslateTransform> da 0 a 350. Tuttavia, questa volta nell'esempio viene registrato per il <xref:System.Windows.Media.Animation.Timeline.Completed> evento.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Il <xref:System.Windows.Media.Animation.Timeline.Completed> gestore dell'evento avvia un oggetto <xref:System.Windows.Media.Animation.Storyboard> che anima la stessa proprietà dal relativo valore corrente fino a 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Di seguito è riportato il markup che definisce la seconda <xref:System.Windows.Media.Animation.Storyboard> come una risorsa.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Quando si esegue la <xref:System.Windows.Media.Animation.Storyboard>, ci si aspetterebbe il <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà del <xref:System.Windows.Media.TranslateTransform> per aggiungere un'animazione da 0 a 350, quindi venga ripristinata su 0 dopo il completamento (perché contiene una <xref:System.Windows.Media.Animation.FillBehavior> impostazione di <xref:System.Windows.Media.Animation.FillBehavior.Stop>) e quindi aggiungere un'animazione da 0 a 500. Al contrario, il <xref:System.Windows.Media.TranslateTransform> aggiunge un'animazione da 0 a 350 e quindi a 500.  
  
 Poiché l'ordine in cui è [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] genera eventi e che i valori delle proprietà vengono memorizzate nella cache e non vengono ricalcolati solo se la proprietà viene invalidata. Il <xref:System.Windows.Media.Animation.Timeline.Completed> evento venga elaborato prima di tutto quanto attivato dalla sequenza temporale radice (il primo <xref:System.Windows.Media.Animation.Storyboard>). A questo punto, il <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà restituisce comunque il valore animato in quanto non è stata ancora invalidata. Il secondo <xref:System.Windows.Media.Animation.Storyboard> Usa il valore memorizzato nella cache come valore iniziale e inizia l'animazione.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>Prestazioni  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Continuazione dell'esecuzione delle animazioni dopo lo spostamento da una pagina  
 Quando si sposta da una <xref:System.Windows.Controls.Page> contenente animazioni in esecuzione, tali animazioni continuano la riproduzione fino a quando il <xref:System.Windows.Controls.Page> viene sottoposto a garbage collection. A seconda del sistema di navigazione in uso, una pagina da cui ci si è spostati potrebbe rimanere in memoria per un tempo indefinito, usando le risorse con le relative animazioni. Ciò è più evidente quando una pagina contiene animazioni in esecuzione continua.  
  
 Per questo motivo, è consigliabile usare il <xref:System.Windows.FrameworkElement.Unloaded> rimuovere le animazioni quando esce dalla pagina dell'evento.  
  
 Per rimuovere un'animazione, sono disponibili modi diversi. Le tecniche seguenti possono essere utilizzate per rimuovere animazioni appartenenti a un <xref:System.Windows.Media.Animation.Storyboard>.  
  
- Per rimuovere un <xref:System.Windows.Media.Animation.Storyboard> si è iniziato con un trigger di evento, vedere [come: Rimuovere uno Storyboard](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
- Usare il codice per rimuovere un <xref:System.Windows.Media.Animation.Storyboard>, vedere il <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> (metodo).  
  
 La tecnica successiva può essere usata indipendentemente dalla modalità di avviamento dell'animazione.  
  
- Per rimuovere le animazioni da una proprietà specifica, usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> (metodo). Specificare la proprietà animata come primo parametro, e `null` come il secondo. In questo modo tutti gli orologi dell'animazione vengono rimossi dalla proprietà.  
  
 Per altre informazioni sui diversi modi per animare le proprietà, vedere [Cenni preliminari sulle tecniche di animazione di proprietà](property-animation-techniques-overview.md).  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Uso di Compose HandoffBehavior con risorse di sistema  
 Quando si applica una <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>, o <xref:System.Windows.Media.Animation.AnimationClock> a una proprietà utilizzando la <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>, qualsiasi <xref:System.Windows.Media.Animation.Clock> oggetti associati in precedenza a tale proprietà continueranno a utilizzare le risorse di sistema; il sistema di temporizzazione non funzionerà rimuovere automaticamente questi orologi.  
  
 Per evitare problemi di prestazioni quando si applica un numero elevato di orologi usando <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>, è necessario rimuovere gli orologi di composizione dalla proprietà animata una volta completati. Esistono diverse modalità di rimozione di un orologio.  
  
- Per rimuovere tutti gli orologi da una proprietà, usare il <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> o <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> metodo dell'oggetto animato. Specificare la proprietà animata come primo parametro, e `null` come il secondo. In questo modo tutti gli orologi dell'animazione vengono rimossi dalla proprietà.  
  
- Per rimuovere uno specifico <xref:System.Windows.Media.Animation.AnimationClock> da un elenco di orologi, usare il <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà delle <xref:System.Windows.Media.Animation.AnimationClock> per recuperare un <xref:System.Windows.Media.Animation.ClockController>, quindi chiamare il <xref:System.Windows.Media.Animation.ClockController.Remove%2A> metodo del <xref:System.Windows.Media.Animation.ClockController>. Ciò avviene in genere il <xref:System.Windows.Media.Animation.Clock.Completed> gestore eventi per un orologio. Si noti che solo gli orologi di radice possono essere controllati da un <xref:System.Windows.Media.Animation.ClockController>; la <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà di un orologio figlio restituirà `null`. Si noti inoltre che il <xref:System.Windows.Media.Animation.Clock.Completed> evento non verrà chiamato se la durata effettiva dell'orologio è infinita.  In tal caso, l'utente dovrà stabilire quando chiamare <xref:System.Windows.Media.Animation.ClockController.Remove%2A>.  
  
 Si tratta principalmente di un problema relativo alle animazioni su oggetti di lunga durata.  Quando un oggetto viene raccolto nel Garbage Collector, anche gli orologi vengono disconnessi e raccolti nel Garbage Collector stesso.  
  
 Per altre informazioni sugli oggetti orologio, vedere [Panoramica sistema di temporizzazione e animazione](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
