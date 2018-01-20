---
title: Suggerimenti sulle animazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 210f8ff8840f579d352cc579f80f38488b998c5a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="animation-tips-and-tricks"></a>Suggerimenti sulle animazioni
Quando si utilizzano le animazioni in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], esistono una serie di suggerimenti e consigli che rendono le animazioni prestazioni migliori e risparmiare frustrazione.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>Problemi generali  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Blocco di una barra di scorrimento o di un dispositivo di scorrimento se si anima la relativa posizione  
 Se si aggiunge un'animazione la posizione di una barra di scorrimento o un dispositivo di scorrimento mediante un'animazione con un <xref:System.Windows.Media.Animation.FillBehavior> di <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (valore predefinito), l'utente non saranno in grado di spostare la barra di scorrimento o un dispositivo di scorrimento. Ciò è dovuto al fatto che, anche se l'animazione è terminata, l'override del valore di base della proprietà di destinazione è ancora in corso. Per interrompere l'animazione di ignorare il valore della proprietà corrente, rimuoverlo o assegnargli un <xref:System.Windows.Media.Animation.FillBehavior> di <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Per ulteriori informazioni e un esempio, vedere [impostarla una proprietà dopo l'animazione di uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Animazione dell'output di un'animazione senza alcun effetto  
 Non è possibile animare un oggetto che rappresenta l'output di un'altra animazione. Ad esempio, se si utilizza un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> per animare la <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle> da un <xref:System.Windows.Media.RadialGradientBrush> per un <xref:System.Windows.Media.SolidColorBrush>, non è possibile animare tutte le proprietà del <xref:System.Windows.Media.RadialGradientBrush> o <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Impossibile modificare il valore di una proprietà dopo averla animata  
 In alcuni casi può sembrare che non sia possibile modificare il valore di una proprietà dopo che è stata animata, anche dopo il termine dell'animazione. Ciò è dovuto al fatto che, anche se l'animazione è terminata, l'override del valore di base della proprietà è ancora in corso. Per interrompere l'animazione di ignorare il valore della proprietà corrente, rimuoverlo o assegnargli un <xref:System.Windows.Media.Animation.FillBehavior> di <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Per ulteriori informazioni e un esempio, vedere [impostarla una proprietà dopo l'animazione di uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Modifica di una sequenza temporale senza alcun effetto  
 Sebbene la maggior parte delle <xref:System.Windows.Media.Animation.Timeline> proprietà possa animare e possono essere associata a dati, la modifica dei valori di proprietà di un oggetto attivo <xref:System.Windows.Media.Animation.Timeline> sembra non hanno alcun effetto. Infatti, quando un <xref:System.Windows.Media.Animation.Timeline> è iniziata, il sistema di temporizzazione crea una copia del <xref:System.Windows.Media.Animation.Timeline> e viene utilizzato per creare un <xref:System.Windows.Media.Animation.Clock> oggetto. La modifica dell'originale non ha alcun effetto sulla copia del sistema.  
  
 Per un <xref:System.Windows.Media.Animation.Timeline> per riflettere le modifiche, ovvero il clock deve essere rigenerato e utilizzato per sostituire quello creato in precedenza. Gli orologi non vengono rigenerati automaticamente. Di seguito vengono indicate diverse modalità per applicare le modifiche alla sequenza temporale:  
  
-   Se la sequenza temporale è o appartiene a un <xref:System.Windows.Media.Animation.Storyboard>, è possibile apportare modifiche riapplicando dello storyboard, utilizzando un <xref:System.Windows.Media.Animation.BeginStoryboard> o <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo. Come effetto collaterale, l'animazione viene riavviata. Nel codice, è possibile utilizzare il <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> nuovamente metodo per spostare lo storyboard in posizione precedente.  
  
-   Se è applicata un'animazione direttamente a una proprietà utilizzando il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo, chiamare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> nuovo metodo e passare l'animazione che è stato modificato.  
  
-   Se si lavora direttamente a livello di orologio, creare e applicare un nuovo set di orologi e usarli per sostituire il set di orologi generati in precedenza.  
  
 Per ulteriori informazioni sulle sequenze temporali e orologi, vedere [animazione e temporizzazione System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>Funzionamento imprevisto di FillBehavior.Stop  
 Vi sono casi durante l'impostazione di <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà <xref:System.Windows.Media.Animation.FillBehavior.Stop> sembra non avere alcun effetto, ad esempio quando un'animazione "restituita" a un altro perché contiene un <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> l'impostazione di <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Shapes.Rectangle> e <xref:System.Windows.Media.TranslateTransform>. Il <xref:System.Windows.Media.TranslateTransform> verrà animato per spostare il <xref:System.Windows.Shapes.Rectangle> intorno il <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Negli esempi di questa sezione utilizzano gli oggetti precedenti per illustrare alcuni casi in cui il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà non si comportano come previsto in.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" e HandoffBehavior con animazioni multiple  
 In alcuni casi può sembrare un'animazione Ignora relativo <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà quando è sostituito da una seconda animazione. Nell'esempio seguente vengono creati due <xref:System.Windows.Media.Animation.Storyboard> oggetti e li utilizza per animare lo stesso <xref:System.Windows.Media.TranslateTransform> illustrato nell'esempio precedente.  
  
 Il primo <xref:System.Windows.Media.Animation.Storyboard>, `B1`, aggiunge un'animazione di <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà del <xref:System.Windows.Media.TranslateTransform> da 0 a 350, che consente di spostare il rettangolo di 350 pixel a destra. Quando si raggiunge la fine della durata dell'animazione e si interrompe, la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà viene ripristinato il valore originale, 0. Il rettangolo di conseguenza si sposta a destra di 350 pixel e quindi torna alla posizione originale.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Il secondo <xref:System.Windows.Media.Animation.Storyboard>, `B2`, inoltre, aggiunge un'animazione di <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà dello stesso <xref:System.Windows.Media.TranslateTransform>. Poiché solo il <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà di animazione in <xref:System.Windows.Media.Animation.Storyboard> è impostato, l'animazione Usa il valore corrente della proprietà anima come valore iniziale.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Se si fa clic sul secondo pulsante mentre il primo <xref:System.Windows.Media.Animation.Storyboard> è la riproduzione, è prevedibile il comportamento seguente:  
  
1.  Il primo storyboard termina e invia il rettangolo alla relativa posizione originale, in quanto l'animazione è un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> di <xref:System.Windows.Media.Animation.FillBehavior.Stop>.  
  
2.  Il secondo storyboard viene applicato e viene animato dalla posizione corrente, da 0 a 500.  
  
 **Questa situazioni non è quella che si verifica.** Il rettangolo infatti non torna alla posizione originale ma continua a spostarsi a destra. Ciò accade perché la seconda animazione usa il valore corrente della prima animazione come valore iniziale e viene eseguita da tale valore fino a 500. Quando la seconda animazione sostituisce il primo in quanto il <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> viene utilizzato il <xref:System.Windows.Media.Animation.FillBehavior> del primo animazione non ha importanza.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior ed evento Completed  
 Negli esempi successivi viene illustrato un altro scenario in cui il <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> sembra non hanno alcun effetto. Nuovamente, nell'esempio viene utilizzato uno Storyboard per animare la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà del <xref:System.Windows.Media.TranslateTransform> da 0 a 350. Tuttavia, questa volta nell'esempio viene registrato per il <xref:System.Windows.Media.Animation.Timeline.Completed> evento.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Il <xref:System.Windows.Media.Animation.Timeline.Completed> gestore eventi viene avviato un altro <xref:System.Windows.Media.Animation.Storyboard> che aggiunge un'animazione la stessa proprietà rispetto al valore corrente a 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Di seguito è riportato il markup che definisce il secondo <xref:System.Windows.Media.Animation.Storyboard> come risorsa.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Quando si esegue il <xref:System.Windows.Media.Animation.Storyboard>, si potrebbe pensare che il <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà del <xref:System.Windows.Media.TranslateTransform> per animare da 0 a 350, quindi tornare a 0 dopo aver completato (perché contiene un <xref:System.Windows.Media.Animation.FillBehavior> l'impostazione di <xref:System.Windows.Media.Animation.FillBehavior.Stop>) e quindi aggiungere un'animazione compreso tra 0 e 500. Al contrario, il <xref:System.Windows.Media.TranslateTransform> anima da 0 a 350 quindi fino a 500.  
  
 Poiché è stato l'ordine in cui [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] genera eventi e che i valori delle proprietà vengono memorizzate nella cache e non vengono ricalcolate a meno che non viene invalidata la proprietà. Il <xref:System.Windows.Media.Animation.Timeline.Completed> evento viene elaborato per primo perché attivato dalla sequenza temporale radice (il primo <xref:System.Windows.Media.Animation.Storyboard>). In questo momento, il <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà restituisce comunque il valore animato perché non è stata ancora invalidata. Il secondo <xref:System.Windows.Media.Animation.Storyboard> utilizza il valore memorizzato nella cache come valore iniziale e inizia l'animazione.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>Prestazioni  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Continuazione dell'esecuzione delle animazioni dopo lo spostamento da una pagina  
 Quando si sposta da un <xref:System.Windows.Controls.Page> contenente animazioni in esecuzione, tali animazioni continuano la riproduzione fino a quando il <xref:System.Windows.Controls.Page> raccolto nel Garbage Collector. A seconda del sistema di navigazione in uso, una pagina da cui ci si è spostati potrebbe rimanere in memoria per un tempo indefinito, usando le risorse con le relative animazioni. Ciò è più evidente quando una pagina contiene animazioni in esecuzione continua.  
  
 Per questo motivo, è consigliabile utilizzare il <xref:System.Windows.FrameworkElement.Unloaded> rimuovere le animazioni quando esce dalla pagina dell'evento.  
  
 Per rimuovere un'animazione, sono disponibili modi diversi. Le tecniche seguenti possono essere utilizzate per rimuovere le animazioni che appartengono a un <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Per rimuovere un <xref:System.Windows.Media.Animation.Storyboard> si inizia con un trigger di evento, vedere [procedura: rimuovere uno Storyboard](http://msdn.microsoft.com/library/7fe39531-de2f-46a0-a69f-b783d04235ee).  
  
-   Usare il codice per rimuovere un <xref:System.Windows.Media.Animation.Storyboard>, vedere il <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> metodo.  
  
 La tecnica successiva può essere usata indipendentemente dalla modalità di avviamento dell'animazione.  
  
-   Per rimuovere le animazioni da una proprietà specifica, utilizzare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> metodo. Specificare la proprietà viene aggiunta un'animazione come primo parametro, e `null` come il secondo. In questo modo tutti gli orologi dell'animazione vengono rimossi dalla proprietà.  
  
 Per ulteriori informazioni sulle diverse modalità per animare le proprietà, vedere [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Uso di Compose HandoffBehavior con risorse di sistema  
 Quando si applica un <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>, o <xref:System.Windows.Media.Animation.AnimationClock> a una proprietà utilizzando il <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>, qualsiasi <xref:System.Windows.Media.Animation.Clock> gli oggetti precedentemente associati a tale proprietà continueranno a utilizzare le risorse di sistema in caso il sistema di temporizzazione non rimuovere automaticamente questi orologi.  
  
 Per evitare problemi di prestazioni quando si applica un numero elevato di clock utilizzando <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>, è necessario rimuovere clock di composizione dalla proprietà animata dopo il completamento. Esistono diverse modalità di rimozione di un orologio.  
  
-   Per rimuovere tutti gli orologi da una proprietà, utilizzare il <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> o <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> metodo dell'oggetto animato. Specificare la proprietà viene aggiunta un'animazione come primo parametro, e `null` come il secondo. In questo modo tutti gli orologi dell'animazione vengono rimossi dalla proprietà.  
  
-   Per rimuovere un oggetto specifico <xref:System.Windows.Media.Animation.AnimationClock> da un elenco di orologi, utilizzare il <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà del <xref:System.Windows.Media.Animation.AnimationClock> per recuperare un <xref:System.Windows.Media.Animation.ClockController>, quindi chiamare il <xref:System.Windows.Media.Animation.ClockController.Remove%2A> metodo il <xref:System.Windows.Media.Animation.ClockController>. Ciò avviene in genere il <xref:System.Windows.Media.Animation.Clock.Completed> gestore eventi per un orologio. Si noti che solo i clock radice possono essere controllati da un <xref:System.Windows.Media.Animation.ClockController>; <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà di un clock figlio restituirà `null`. Si noti inoltre che il <xref:System.Windows.Media.Animation.Clock.Completed> evento non verrà chiamato se la durata effettiva dell'orologio è infinita.  In tal caso, l'utente sarà necessario determinare quando chiamare <xref:System.Windows.Media.Animation.ClockController.Remove%2A>.  
  
 Si tratta principalmente di un problema relativo alle animazioni su oggetti di lunga durata.  Quando un oggetto viene raccolto nel Garbage Collector, anche gli orologi vengono disconnessi e raccolti nel Garbage Collector stesso.  
  
 Per ulteriori informazioni sugli oggetti clock, vedere [animazione e temporizzazione System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
