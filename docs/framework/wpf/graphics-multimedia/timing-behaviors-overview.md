---
title: Cenni preliminari sui comportamenti temporali
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: a85f980a0cefaa282e9e92d533a2306a9009e3e7
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559950"
---
# <a name="timing-behaviors-overview"></a>Cenni preliminari sui comportamenti temporali
In questo argomento vengono descritti i comportamenti temporali delle animazioni e altri oggetti <xref:System.Windows.Media.Animation.Timeline>.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere le funzionalità di base delle animazioni. Per ulteriori informazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>Tipi di sequenza temporale  
 Una <xref:System.Windows.Media.Animation.Timeline> rappresenta un intervallo di tempo. Offre proprietà che consentono di specificare la lunghezza di tale intervallo, il momento di inizio, il numero di ripetizioni, la velocità di avanzamento dell'intervallo e così via.  
  
 Le classi che ereditano dalla classe della sequenza temporale offrono funzionalità aggiuntive, ad esempio la riproduzione di animazioni e file multimediali. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce i tipi di <xref:System.Windows.Media.Animation.Timeline> seguenti.  
  
|Tipo di sequenza temporale|Descrizione|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Classe di base astratta per oggetti <xref:System.Windows.Media.Animation.Timeline> che generano valori di output per l'animazione di proprietà.|  
|<xref:System.Windows.Media.MediaTimeline>|Genera l'output da un file multimediale.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Tipo di <xref:System.Windows.Media.Animation.TimelineGroup> che raggruppa e controlla gli oggetti <xref:System.Windows.Media.Animation.Timeline> figlio.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Tipo di <xref:System.Windows.Media.Animation.ParallelTimeline> che fornisce le informazioni di destinazione per gli oggetti della sequenza temporale in esso contenuti.|  
|<xref:System.Windows.Media.Animation.Timeline>|Classe di base astratta che definisce i comportamenti temporali.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Classe astratta per oggetti <xref:System.Windows.Media.Animation.Timeline> che possono contenere altri oggetti <xref:System.Windows.Media.Animation.Timeline>.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>Proprietà che controllano la lunghezza di una sequenza temporale  
 Una <xref:System.Windows.Media.Animation.Timeline> rappresenta un intervallo di tempo e la lunghezza di una sequenza temporale può essere descritta in modi diversi. La tabella seguente definisce vari termini per descrivere la lunghezza di una sequenza temporale.  
  
|Termine|Descrizione|Proprietà||||  
|----------|-----------------|----------------|-|-|-|  
|Durata semplice|Periodo di tempo impiegato da una sequenza temporale per compiere una singola iterazione in avanti.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Una ripetizione|Tempo necessario per la riproduzione di una sequenza temporale una volta e, se la proprietà <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> è true, riprodurre una volta all'indietro.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Periodo attivo|Tempo impiegato da una sequenza temporale per completare tutte le ripetizioni specificate dalla relativa proprietà <xref:System.Windows.Media.Animation.RepeatBehavior>.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Proprietà Duration  
 Come accennato in precedenza, una sequenza temporale rappresenta un intervallo di tempo. La lunghezza di tale segmento è determinata dalla <xref:System.Windows.Media.Animation.Timeline.Duration%2A>della sequenza temporale. Quando una sequenza temporale raggiunge la fine della propria durata, la riproduzione viene interrotta. Se la sequenza temporale dispone di sequenze temporali figlio, anche la loro riproduzione viene interrotta. Nel caso di un'animazione, il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifica il tempo necessario per la transizione dell'animazione dal valore iniziale al valore finale. La durata di una sequenza temporale viene talvolta chiamata *durata semplice*, per distinguere tra la durata di una singola iterazione e la durata totale di riproduzione dell'animazione, incluse le ripetizioni. È possibile specificare una durata usando un valore di ora finito o i valori speciali <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>. La durata di un'animazione deve essere risolta in un valore <xref:System.Windows.Duration.TimeSpan%2A>, in modo che sia possibile eseguire la transizione tra i valori.  
  
 Nell'esempio seguente viene illustrato un <xref:System.Windows.Media.Animation.DoubleAnimation> con una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di cinque secondi.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Le sequenze temporali dei contenitori, ad esempio <xref:System.Windows.Media.Animation.Storyboard> e <xref:System.Windows.Media.Animation.ParallelTimeline>, hanno una durata predefinita <xref:System.Windows.Duration.Automatic%2A>, il che significa che terminano automaticamente quando l'ultimo figlio smette di essere riprodotto. Nell'esempio seguente viene illustrato un <xref:System.Windows.Media.Animation.Storyboard> il cui <xref:System.Windows.Media.Animation.Timeline.Duration%2A> si risolve in cinque secondi, il tempo necessario per il completamento di tutti gli oggetti <xref:System.Windows.Media.Animation.DoubleAnimation> figlio.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Impostando il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di una sequenza temporale del contenitore su un valore <xref:System.Windows.Duration.TimeSpan%2A>, è possibile forzare la riproduzione più lunga o più breve rispetto al <xref:System.Windows.Media.Animation.Timeline> oggetti figlio. Se si imposta il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> su un valore minore della lunghezza degli oggetti <xref:System.Windows.Media.Animation.Timeline> figlio della sequenza temporale del contenitore, gli oggetti figlio <xref:System.Windows.Media.Animation.Timeline> interrompono la riproduzione quando la sequenza temporale del contenitore lo esegue. Nell'esempio seguente viene impostata la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> del <xref:System.Windows.Media.Animation.Storyboard> dagli esempi precedenti a tre secondi. Di conseguenza, il primo <xref:System.Windows.Media.Animation.DoubleAnimation> si interrompe dopo tre secondi, quando la larghezza del rettangolo di destinazione è stata animata a 60.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>Proprietà RepeatBehavior  
 La proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> di un <xref:System.Windows.Media.Animation.Timeline> controlla il numero di volte che ripete la durata normale. Utilizzando la proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> è possibile specificare il numero di volte in cui la sequenza temporale viene riprodotta (un'iterazione <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) o la durata totale del tempo che deve riprodurre (ripetizione <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>). In entrambi i casi l'animazione viene eseguita dall'inizio alla fine per il numero di volte necessario per completare il conteggio o la durata richiesti. Per impostazione predefinita, le sequenze temporali hanno un conteggio delle iterazioni di `1.0`, che significa che vengono riprodotte una sola volta e non vengono ripetute.  
  
 Nell'esempio seguente viene usata la proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> per fare in modo che una <xref:System.Windows.Media.Animation.DoubleAnimation> riproduca per due volte la durata semplice specificando un conteggio delle iterazioni.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 Nell'esempio seguente viene usata la proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> per fare in modo che il <xref:System.Windows.Media.Animation.DoubleAnimation> riproduca per metà della relativa durata semplice.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Se si imposta la proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> di un <xref:System.Windows.Media.Animation.Timeline> su <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, il <xref:System.Windows.Media.Animation.Timeline> si ripete fino a quando non viene interrotto in modo interattivo o dal sistema di temporizzazione. Nell'esempio seguente viene usata la proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> per fare in modo che il <xref:System.Windows.Media.Animation.DoubleAnimation> riproduca per un periodo illimitato.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Per un esempio aggiuntivo, vedere [Repeat an Animation](how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>Proprietà AutoReverse  
 La proprietà <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> specifica se una <xref:System.Windows.Media.Animation.Timeline> giocherà a ritroso alla fine di ogni iterazione in avanti. Nell'esempio seguente viene impostata la proprietà <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> di un <xref:System.Windows.Media.Animation.DoubleAnimation> per `true`; di conseguenza, viene animato da zero a 100 e quindi da 100 a zero. La riproduzione ha una durata totale di 10 secondi.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Quando si utilizza un valore <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> per specificare il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> di un <xref:System.Windows.Media.Animation.Timeline> e la proprietà <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> di tale <xref:System.Windows.Media.Animation.Timeline> è `true`, una singola ripetizione è costituita da un'iterazione in avanti seguita da un'iterazione all'indietro.  Nell'esempio seguente viene impostato il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> della <xref:System.Windows.Media.Animation.DoubleAnimation> dall'esempio precedente a un <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> di due. Di conseguenza, il <xref:System.Windows.Media.Animation.DoubleAnimation> viene riprodotto per 20 secondi: avanti per cinque secondi, indietro per cinque secondi, avanti per 5 secondi e poi indietro per cinque secondi.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Se una sequenza temporale del contenitore ha oggetti figlio <xref:System.Windows.Media.Animation.Timeline>, viene invertita quando viene eseguita la sequenza temporale del contenitore. Per altri esempi, vedere [specificare se una sequenza temporale viene invertita automaticamente](how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>Proprietà BeginTime  
 La proprietà <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> consente di specificare quando viene avviata una sequenza temporale.  Il momento di avvio di una sequenza temporale è relativo alla sequenza temporale padre. Un momento di avvio pari a zero secondi indica che la sequenza temporale viene avviata all'avvio della sequenza padre. Qualsiasi altro valore crea un offset tra il momento di avvio della riproduzione della sequenza temporale padre e quello della sequenza temporale figlio. Un momento di avvio di due secondi indica ad esempio che la riproduzione della sequenza temporale viene avviata quando la sequenza temporale padre ha raggiunto un valore di due secondi. Per impostazione predefinita, il momento di avvio di tutte le sequenze temporali è pari a zero secondi. È anche possibile impostare l'ora di inizio di una sequenza temporale su `null`, che impedisce l'avvio della sequenza temporale. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]specificare null usando l'estensione di [markup x:null](../../../desktop-wpf/xaml-services/xnull-markup-extension.md).  
  
 Si noti che l'ora di inizio non viene applicata ogni volta che una sequenza temporale si ripete a causa della relativa impostazione <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>. Se si crea un'animazione con un <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> di 10 secondi e una <xref:System.Windows.Media.Animation.RepeatBehavior> di <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, si verificherà un ritardo di 10 secondi prima che l'animazione venga riprodotta per la prima volta, ma non per ogni ripetizione successiva. Se la sequenza temporale padre dell'animazione tuttavia venisse riavviata o ripetuta, verrebbe applicato il ritardo di 10 secondi.  
  
 La proprietà <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> è utile per scaglionare le sequenze temporali. Nell'esempio seguente viene creato un <xref:System.Windows.Media.Animation.Storyboard> con due oggetti <xref:System.Windows.Media.Animation.DoubleAnimation> figlio. La prima animazione ha un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di cinque secondi e il secondo ha un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di 3 secondi. Nell'esempio viene impostato il <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> della seconda <xref:System.Windows.Media.Animation.DoubleAnimation> su 5 secondi, in modo che inizi la riproduzione dopo che il primo <xref:System.Windows.Media.Animation.DoubleAnimation> termina.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>Proprietà FillBehavior  
 Quando un <xref:System.Windows.Media.Animation.Timeline> raggiunge la fine della durata attiva totale, la proprietà <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> specifica se l'ultimo valore viene arrestato o meno. Un'animazione con <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> di <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "conserva" il valore di output: la proprietà animata mantiene l'ultimo valore dell'animazione. Il valore <xref:System.Windows.Media.Animation.FillBehavior.Stop> fa in modo che l'animazione interrompa la relativa proprietà di destinazione dopo la fine.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Media.Animation.Storyboard> con due oggetti <xref:System.Windows.Media.Animation.DoubleAnimation> figlio. Entrambi gli oggetti <xref:System.Windows.Media.Animation.DoubleAnimation> animano il <xref:System.Windows.FrameworkElement.Width%2A> di un <xref:System.Windows.Shapes.Rectangle> da 0 a 100. Gli elementi <xref:System.Windows.Shapes.Rectangle> hanno valori <xref:System.Windows.FrameworkElement.Width%2A> non animati di 500 [device independent pixels].  
  
- La proprietà <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> della prima <xref:System.Windows.Media.Animation.DoubleAnimation> è impostata su <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, ovvero sul valore predefinito. Di conseguenza, la larghezza del rettangolo rimane a 100 dopo la fine del <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
- La proprietà <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> della seconda <xref:System.Windows.Media.Animation.DoubleAnimation> è impostata su <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Di conseguenza, il <xref:System.Windows.FrameworkElement.Width%2A> della seconda <xref:System.Windows.Shapes.Rectangle> torna a 500 al termine della <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Proprietà che controllano la velocità di una sequenza temporale  
 La classe <xref:System.Windows.Media.Animation.Timeline> fornisce tre proprietà per specificarne la velocità:  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>: specifica la frequenza, relativa all'elemento padre, a cui avanza il tempo per un <xref:System.Windows.Media.Animation.Timeline>. I valori maggiori di uno aumentano la velocità del <xref:System.Windows.Media.Animation.Timeline> e dei relativi oggetti figlio <xref:System.Windows.Media.Animation.Timeline>; valori compresi tra zero e uno rallentano. Il valore 1 indica che <xref:System.Windows.Media.Animation.Timeline> avanza alla stessa velocità del padre. L'impostazione <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> di una sequenza temporale del contenitore influiscono anche su tutti i relativi oggetti <xref:System.Windows.Media.Animation.Timeline> figlio.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>: specifica la percentuale di <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di una sequenza temporale trascorsa in accelerazione. Per un esempio, vedere [procedura: accelerare o decelerare un'animazione](how-to-accelerate-or-decelerate-an-animation.md). 
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>: specifica la percentuale di <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di una sequenza temporale trascorsa per la decelerazione. Per un esempio, vedere [procedura: accelerare o decelerare un'animazione](how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md)
- [Cenni preliminari sugli eventi di tempo](timing-events-overview.md)
- [Procedure relative alle proprietà](animation-and-timing-how-to-topics.md)
- [Esempio di comportamento temporale di un'animazione](https://go.microsoft.com/fwlink/?LinkID=159970)
