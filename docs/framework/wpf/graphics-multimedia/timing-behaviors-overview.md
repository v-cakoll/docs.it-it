---
title: Cenni preliminari sui comportamenti temporali
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 3bb42ddd991d3ae1221cc794afdd4aafc74a6046
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145397"
---
# <a name="timing-behaviors-overview"></a>Cenni preliminari sui comportamenti temporali
In questo argomento vengono descritti i <xref:System.Windows.Media.Animation.Timeline> comportamenti di temporizzazione delle animazioni e di altri oggetti.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere questo argomento, è necessario conoscere le funzionalità di base delle animazioni. Per ulteriori informazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
<a name="timelinetypes"></a>
## <a name="timeline-types"></a>Tipi di sequenza temporale  
 A <xref:System.Windows.Media.Animation.Timeline> rappresenta un segmento di tempo. Offre proprietà che consentono di specificare la lunghezza di tale intervallo, il momento di inizio, il numero di ripetizioni, la velocità di avanzamento dell'intervallo e così via.  
  
 Le classi che ereditano dalla classe della sequenza temporale offrono funzionalità aggiuntive, ad esempio la riproduzione di animazioni e file multimediali. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce i <xref:System.Windows.Media.Animation.Timeline> seguenti tipi.  
  
|Tipo di sequenza temporale|Descrizione|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Classe base <xref:System.Windows.Media.Animation.Timeline> astratta per gli oggetti che generano valori di output per l'animazione delle proprietà.|  
|<xref:System.Windows.Media.MediaTimeline>|Genera l'output da un file multimediale.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Un tipo <xref:System.Windows.Media.Animation.TimelineGroup> di tale <xref:System.Windows.Media.Animation.Timeline> raggruppa e controlla gli oggetti figlio.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Tipo di <xref:System.Windows.Media.Animation.ParallelTimeline> che fornisce informazioni di destinazione per gli oggetti Timeline in esso contenuti.|  
|<xref:System.Windows.Media.Animation.Timeline>|Classe di base astratta che definisce i comportamenti temporali.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Classe astratta per <xref:System.Windows.Media.Animation.Timeline> oggetti <xref:System.Windows.Media.Animation.Timeline> che possono contenere altri oggetti.|  
  
<a name="propertiesthatcontroltimelinelength"></a>
## <a name="properties-that-control-the-length-of-a-timeline"></a>Proprietà che controllano la lunghezza di una sequenza temporale  
 Un <xref:System.Windows.Media.Animation.Timeline> rappresenta un segmento di tempo e la lunghezza di una sequenza temporale può essere descritta in modi diversi. La tabella seguente definisce vari termini per descrivere la lunghezza di una sequenza temporale.  
  
|Termine|Descrizione|Proprietà||||  
|----------|-----------------|----------------|-|-|-|  
|Durata semplice|Periodo di tempo impiegato da una sequenza temporale per compiere una singola iterazione in avanti.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Una ripetizione|Il tempo necessario per la riproduzione in avanti <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> di una sequenza temporale una volta e, se la proprietà è vera, riprodurre all'indietro una volta.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Periodo attivo|Tempo necessario affinché una sequenza temporale completi tutte le <xref:System.Windows.Media.Animation.RepeatBehavior> ripetizioni specificate dalla relativa proprietà.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>
### <a name="the-duration-property"></a>Proprietà Duration  
 Come accennato in precedenza, una sequenza temporale rappresenta un intervallo di tempo. La lunghezza di tale segmento è <xref:System.Windows.Media.Animation.Timeline.Duration%2A>determinata dalla sequenza temporale. Quando una sequenza temporale raggiunge la fine della propria durata, la riproduzione viene interrotta. Se la sequenza temporale dispone di sequenze temporali figlio, anche la loro riproduzione viene interrotta. Nel caso di un'animazione, l'oggetto specifica il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> tempo impiegato dall'animazione per la transizione dal valore iniziale al valore finale. La durata di una sequenza temporale è talvolta chiamata durata *semplice,* per distinguere tra la durata di una singola iterazione e la durata totale della riproduzione dell'animazione, incluse le ripetizioni. È possibile specificare una durata utilizzando un <xref:System.Windows.Duration.Automatic%2A> <xref:System.Windows.Duration.Forever%2A>valore temporale finito o i valori speciali o . La durata di un'animazione deve essere risolta in un valore, in modo che possa passare da un <xref:System.Windows.Duration.TimeSpan%2A> valore all'altro.  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation> viene <xref:System.Windows.Media.Animation.Timeline.Duration%2A> illustrato un con un di cinque secondi.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Le sequenze temporali <xref:System.Windows.Media.Animation.ParallelTimeline>del contenitore, <xref:System.Windows.Duration.Automatic%2A>ad esempio <xref:System.Windows.Media.Animation.Storyboard> e , hanno una durata predefinita pari a , ovvero terminano automaticamente quando l'ultimo elemento figlio interrompe la riproduzione. Nell'esempio seguente <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Timeline.Duration%2A> viene illustrato un cui si risolve a cinque <xref:System.Windows.Media.Animation.DoubleAnimation> secondi, il tempo di tempo che richiede tutti i relativi oggetti figlio per il completamento.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Impostando la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> sequenza temporale <xref:System.Windows.Duration.TimeSpan%2A> di un contenitore su un valore, <xref:System.Windows.Media.Animation.Timeline> è possibile forzare la riproduzione più lunga o più corta rispetto agli oggetti figlio. Se si <xref:System.Windows.Media.Animation.Timeline.Duration%2A> imposta l'oggetto su un valore inferiore alla lunghezza <xref:System.Windows.Media.Animation.Timeline> degli oggetti <xref:System.Windows.Media.Animation.Timeline> figlio della sequenza temporale contenitore, la riproduzione degli oggetti figlio viene interrotta quando viene visualizzata la sequenza temporale del contenitore. Nell'esempio seguente <xref:System.Windows.Media.Animation.Timeline.Duration%2A> l'oggetto <xref:System.Windows.Media.Animation.Storyboard> del da quelli precedenti viene impostato su tre secondi. Di conseguenza, <xref:System.Windows.Media.Animation.DoubleAnimation> il primo interrompe l'avanzamento dopo tre secondi, quando ha animato la larghezza del rettangolo di destinazione a 60.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>
### <a name="the-repeatbehavior-property"></a>Proprietà RepeatBehavior  
 La <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà <xref:System.Windows.Media.Animation.Timeline> di un controlla quante volte ripete la durata semplice. Utilizzando <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> la proprietà , è possibile specificare quante <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>volte la sequenza temporale viene riprodotta (un'iterazione ) o la durata totale di riproduzione (una ripetizione <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>). In entrambi i casi l'animazione viene eseguita dall'inizio alla fine per il numero di volte necessario per completare il conteggio o la durata richiesti. Per impostazione predefinita, le `1.0`sequenze temporali hanno un conteggio delle iterazioni pari a , il che significa che vengono riprodotte una sola volta e non si ripetono affatto.  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> viene utilizzata <xref:System.Windows.Media.Animation.DoubleAnimation> la proprietà per creare una riproduzione per due volte la durata semplice specificando un conteggio delle iterazioni.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 Nell'esempio successivo <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> viene utilizzata <xref:System.Windows.Media.Animation.DoubleAnimation> la proprietà per rendere il gioco per metà della sua durata semplice.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Se si <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> imposta la <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>proprietà <xref:System.Windows.Media.Animation.Timeline> di a su , la ripetizione viene ripetuta fino a quando non viene interrotta in modo interattivo o dal sistema di temporizzazione. Nell'esempio seguente <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> viene utilizzata <xref:System.Windows.Media.Animation.DoubleAnimation> la proprietà per eseguire la riproduzione a tempo indeterminato.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Per un altro esempio, vedere Ripetizione di [un'animazione](how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>
### <a name="the-autoreverse-property"></a>Proprietà AutoReverse  
 La <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà specifica <xref:System.Windows.Media.Animation.Timeline> se un oggetto verrà riprodotto all'indietro alla fine di ogni iterazione in avanti. Nell'esempio riportato <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> di <xref:System.Windows.Media.Animation.DoubleAnimation> seguito `true`viene impostato sulla proprietà di a to ; di conseguenza, aggiunge un'animazione da zero a 100 e quindi da 100 a zero. La riproduzione ha una durata totale di 10 secondi.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Quando si <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> utilizza un <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> valore <xref:System.Windows.Media.Animation.Timeline> per <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> specificare <xref:System.Windows.Media.Animation.Timeline> la `true`proprietà di a e la proprietà di , una singola ripetizione è costituita da un'iterazione in avanti seguita da un'iterazione all'indietro.  Nell'esempio seguente <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> l'oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> da dell'esempio precedente viene impostato su a <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> di due. Di conseguenza, <xref:System.Windows.Media.Animation.DoubleAnimation> le giocate per 20 secondi: avanti per cinque secondi, indietro per cinque secondi, in avanti per 5 secondi di nuovo, e poi indietro per cinque secondi.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Se una sequenza <xref:System.Windows.Media.Animation.Timeline> temporale contenitore ha oggetti figlio, si invertono quando la sequenza temporale contenitore. Per ulteriori esempi, consultate [Specificare se una linea temporale viene invertita automaticamente.](how-to-specify-whether-a-timeline-automatically-reverses.md)  
  
<a name="timelinebegin"></a>
## <a name="the-begintime-property"></a>Proprietà BeginTime  
 La <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà consente di specificare quando viene avviata una sequenza temporale.  Il momento di avvio di una sequenza temporale è relativo alla sequenza temporale padre. Un momento di avvio pari a zero secondi indica che la sequenza temporale viene avviata all'avvio della sequenza padre. Qualsiasi altro valore crea un offset tra il momento di avvio della riproduzione della sequenza temporale padre e quello della sequenza temporale figlio. Un momento di avvio di due secondi indica ad esempio che la riproduzione della sequenza temporale viene avviata quando la sequenza temporale padre ha raggiunto un valore di due secondi. Per impostazione predefinita, il momento di avvio di tutte le sequenze temporali è pari a zero secondi. È inoltre possibile impostare l'ora di inizio di una sequenza temporale su `null`, che impedisce l'avvio della sequenza temporale. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], specificare null utilizzando l'estensione di [markup x:Null](../../../desktop-wpf/xaml-services/xnull-markup-extension.md).  
  
 Si noti che l'ora di inizio non <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> viene applicata ogni volta che una sequenza temporale viene ripetuta a causa della relativa impostazione. Se si creasse un'animazione con un <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> valore di 10 secondi e un <xref:System.Windows.Media.Animation.RepeatBehavior> di <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, ci sarebbe un ritardo di 10 secondi prima che l'animazione venga riprodotta per la prima volta, ma non per ogni ripetizione successiva. Se la sequenza temporale padre dell'animazione tuttavia venisse riavviata o ripetuta, verrebbe applicato il ritardo di 10 secondi.  
  
 La <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà è utile per scaglionare le sequenze temporali. Nell'esempio seguente <xref:System.Windows.Media.Animation.Storyboard> viene creato <xref:System.Windows.Media.Animation.DoubleAnimation> un che dispone di due oggetti figlio. La prima animazione ha un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> valore di <xref:System.Windows.Media.Animation.Timeline.Duration%2A> cinque secondi e la seconda ha un valore di 3 secondi. Nell'esempio <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> viene impostato <xref:System.Windows.Media.Animation.DoubleAnimation> il secondo su 5 secondi, <xref:System.Windows.Media.Animation.DoubleAnimation> in modo che inizi la riproduzione dopo la prima fine.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>
## <a name="the-fillbehavior-property"></a>Proprietà FillBehavior  
 Quando <xref:System.Windows.Media.Animation.Timeline> un oggetto raggiunge la fine della <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> durata attiva totale, la proprietà specifica se interrompe o mantiene l'ultimo valore. Un'animazione <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> con un "contiene" il valore di output: la proprietà a cui viene aggiunta un'animazione mantiene l'ultimo valore dell'animazione. Valore di <xref:System.Windows.Media.Animation.FillBehavior.Stop> fa sì che l'animazione si arresta che influisce sulla proprietà di destinazione al termine.  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.Storyboard> viene creato <xref:System.Windows.Media.Animation.DoubleAnimation> un che dispone di due oggetti figlio. Entrambi <xref:System.Windows.Media.Animation.DoubleAnimation> gli <xref:System.Windows.FrameworkElement.Width%2A> oggetti <xref:System.Windows.Shapes.Rectangle> animano il di a da 0 a 100. Gli <xref:System.Windows.Shapes.Rectangle> elementi hanno <xref:System.Windows.FrameworkElement.Width%2A> valori non animati di 500 [pixel indipendenti dal dispositivo].  
  
- La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà del <xref:System.Windows.Media.Animation.DoubleAnimation> primo <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>è impostata su , il valore predefinito. Di conseguenza, la larghezza del rettangolo rimane <xref:System.Windows.Media.Animation.DoubleAnimation> a 100 dopo le estremità.  
  
- La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà del <xref:System.Windows.Media.Animation.DoubleAnimation> secondo <xref:System.Windows.Media.Animation.FillBehavior.Stop>è impostata su . Di conseguenza, <xref:System.Windows.FrameworkElement.Width%2A> il <xref:System.Windows.Shapes.Rectangle> secondo ritorna a 500 dopo le <xref:System.Windows.Media.Animation.DoubleAnimation> estremità.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Proprietà che controllano la velocità di una sequenza temporale  
 La <xref:System.Windows.Media.Animation.Timeline> classe fornisce tre proprietà per specificarne la velocità:The class provides three properties for specifying its speed:  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>– Specifica che la velocità, rispetto al relativo padre, viene ecosì a lungo per un oggetto <xref:System.Windows.Media.Animation.Timeline>. I valori maggiori di uno <xref:System.Windows.Media.Animation.Timeline> aumentano <xref:System.Windows.Media.Animation.Timeline> la velocità degli oggetti figlio e di essi; valori compresi tra zero e uno rallentarlo. Il valore 1 pari <xref:System.Windows.Media.Animation.Timeline> a uno indica che avanza alla stessa velocità dell'elemento padre. L'impostazione <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> di una sequenza <xref:System.Windows.Media.Animation.Timeline> temporale contenitore influisce anche su tutti i relativi oggetti figlio.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>– Specifica la percentuale <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di una linea temporale speso per l'accelerazione. Per un esempio, vedere [Procedura: accelerare o decelerare un'animazione](how-to-accelerate-or-decelerate-an-animation.md).
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>- Specifica la percentuale <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di una sequenza temporale spesa decelerazione. Per un esempio, vedere [Procedura: accelerare o decelerare un'animazione](how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md)
- [Cenni preliminari sugli eventi di tempo](timing-events-overview.md)
- [Argomenti relativi alle procedure](animation-and-timing-how-to-topics.md)
- [Esempio di comportamento temporale di un'animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
