---
title: Cenni preliminari sui comportamenti temporali
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 31a6b7d3b92e886d9c90fc39d69f31cf72b99666
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566324"
---
# <a name="timing-behaviors-overview"></a>Cenni preliminari sui comportamenti temporali
In questo argomento vengono descritti i comportamenti temporali delle animazioni e di altri <xref:System.Windows.Media.Animation.Timeline> oggetti.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere le funzionalità di base delle animazioni. Per ulteriori informazioni, vedere il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>Tipi di sequenza temporale  
 Oggetto <xref:System.Windows.Media.Animation.Timeline> rappresenta un segmento di tempo. Offre proprietà che consentono di specificare la lunghezza di tale intervallo, il momento di inizio, il numero di ripetizioni, la velocità di avanzamento dell'intervallo e così via.  
  
 Le classi che ereditano dalla classe della sequenza temporale offrono funzionalità aggiuntive, ad esempio la riproduzione di animazioni e file multimediali. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce le seguenti <xref:System.Windows.Media.Animation.Timeline> tipi.  
  
|Tipo di sequenza temporale|Descrizione|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Classe base astratta per <xref:System.Windows.Media.Animation.Timeline> gli oggetti che generano valori di output per tali proprietà.|  
|<xref:System.Windows.Media.MediaTimeline>|Genera l'output da un file multimediale.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Un tipo di <xref:System.Windows.Media.Animation.TimelineGroup> che i gruppi e controlli figlio <xref:System.Windows.Media.Animation.Timeline> oggetti.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Un tipo di <xref:System.Windows.Media.Animation.ParallelTimeline> che fornisce informazioni per gli oggetti della sequenza temporale che contiene.|  
|<xref:System.Windows.Media.Animation.Timeline>|Classe di base astratta che definisce i comportamenti temporali.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Classe astratta per <xref:System.Windows.Media.Animation.Timeline> gli oggetti che possono contenere altre <xref:System.Windows.Media.Animation.Timeline> oggetti.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>Proprietà che controllano la lunghezza di una sequenza temporale  
 Oggetto <xref:System.Windows.Media.Animation.Timeline> rappresenta un intervallo di tempo e la lunghezza di una sequenza temporale può essere descritto in modi diversi. La tabella seguente definisce vari termini per descrivere la lunghezza di una sequenza temporale.  
  
|Termine|Descrizione|Proprietà||||  
|----------|-----------------|----------------|-|-|-|  
|Durata semplice|Periodo di tempo impiegato da una sequenza temporale per compiere una singola iterazione in avanti.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Una ripetizione|Il periodo di tempo impiegato da una sequenza temporale per riprodotta una volta e, se il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> è true, riprodurre con le versioni precedenti di una volta.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Periodo attivo|Il periodo di tempo impiegato da una sequenza temporale per completare tutte le ripetizioni specificate dal relativo <xref:System.Windows.Media.Animation.RepeatBehavior> proprietà.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Proprietà Duration  
 Come accennato in precedenza, una sequenza temporale rappresenta un intervallo di tempo. La lunghezza del segmento è la sequenza temporale <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Quando una sequenza temporale raggiunge la fine della propria durata, la riproduzione viene interrotta. Se la sequenza temporale dispone di sequenze temporali figlio, anche la loro riproduzione viene interrotta. Nel caso di un'animazione, la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifica il tempo impiegato dall'animazione per la transizione dal valore iniziale al valore finale. Una sequenza temporale è detta relativo *durata semplice*, per distinguere tra la durata di una singola iterazione e la lunghezza totale del tempo di riproduzione dell'animazione, incluse le ripetizioni. È possibile specificare una durata utilizzando un valore di tempo finito o i valori speciali <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>. Durata di un'animazione deve restituire un <xref:System.Windows.Duration.TimeSpan%2A> valore, pertanto è possibile eseguire la transizione tra i valori.  
  
 Nell'esempio seguente un <xref:System.Windows.Media.Animation.DoubleAnimation> con un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di cinque secondi.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Le sequenze temporali contenitore, ad esempio <xref:System.Windows.Media.Animation.Storyboard> e <xref:System.Windows.Media.Animation.ParallelTimeline>, hanno una durata predefinita di <xref:System.Windows.Duration.Automatic%2A>, ovvero terminano automaticamente al termine dell'esecuzione dell'ultimo figlio. Nell'esempio seguente un <xref:System.Windows.Media.Animation.Storyboard> cui <xref:System.Windows.Media.Animation.Timeline.Duration%2A> si risolve in cinque secondi, quanto tempo servirebbe per tutti i relativi elementi figlio <xref:System.Windows.Media.Animation.DoubleAnimation> oggetti da completare.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Impostando il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di una sequenza temporale contenitore per un <xref:System.Windows.Duration.TimeSpan%2A> valore, è possibile forzare di riprodurre superiori o inferiori a figlio <xref:System.Windows.Media.Animation.Timeline> degli oggetti. Se si imposta la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> su un valore che è minore della lunghezza dell'elemento figlio della sequenza temporale contenitore <xref:System.Windows.Media.Animation.Timeline> oggetti, l'elemento figlio <xref:System.Windows.Media.Animation.Timeline> oggetti interrompere l'esecuzione quando il contenitore della sequenza temporale. L'esempio seguente imposta il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> del <xref:System.Windows.Media.Animation.Storyboard> degli esempi precedenti per tre secondi. Di conseguenza, il primo <xref:System.Windows.Media.Animation.DoubleAnimation> viene interrotto dopo tre secondi, quando dispone di animazione per 60 la larghezza del rettangolo di destinazione.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>Proprietà RepeatBehavior  
 Il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> controlla quante volte si ripete la propria durata semplice. Utilizzo di <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà, è possibile specificare quante volte la riproduzione della sequenza temporale (un'iterazione <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) o la lunghezza totale del tempo deve essere riprodotto (una ripetizione <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>). In entrambi i casi l'animazione viene eseguita dall'inizio alla fine per il numero di volte necessario per completare il conteggio o la durata richiesti. Per impostazione predefinita, le sequenze temporali hanno un conteggio di iterazioni di `1.0`, vale a dire che vengono riprodotte una sola volta e non vengono ripetuti.  
  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà per rendere un <xref:System.Windows.Media.Animation.DoubleAnimation> riprodurre per due volte la propria durata semplice specificando un conteggio delle iterazioni.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 L'esempio seguente viene utilizzata la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà per rendere il <xref:System.Windows.Media.Animation.DoubleAnimation> riprodurre per metà della durata normale.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Se si imposta la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> per <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, <xref:System.Windows.Media.Animation.Timeline> viene ripetuto finché non viene interrotto in modo interattivo o dal sistema di temporizzazione. L'esempio seguente usa il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà per rendere il <xref:System.Windows.Media.Animation.DoubleAnimation> riprodurre in modo indefinito.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Per un altro esempio, vedere [ripetere un'animazione](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>Proprietà AutoReverse  
 Il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà specifica se un <xref:System.Windows.Media.Animation.Timeline> verrà riprodotto in senso inverso alla fine di ogni iterazione in avanti. Nell'esempio seguente viene impostato il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà di un <xref:System.Windows.Media.Animation.DoubleAnimation> a `true`; di conseguenza, aggiunge un'animazione da zero a 100, quindi da 100 a zero. La riproduzione ha una durata totale di 10 secondi.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Quando si utilizza un <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> valore per specificare il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> di un <xref:System.Windows.Media.Animation.Timeline> e <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà di tale <xref:System.Windows.Media.Animation.Timeline> è `true`, una sola ripetizione è costituita da uno iterazione in avanti seguita da uno con le versioni precedenti dell'iterazione.  L'esempio seguente imposta il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> del <xref:System.Windows.Media.Animation.DoubleAnimation> dell'esempio precedente per un <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> di due. Di conseguenza, il <xref:System.Windows.Media.Animation.DoubleAnimation> viene riprodotto per 20 secondi: inoltrare per inoltrare i cinque secondi, con le versioni precedenti per cinque secondi, per 5 secondi e quindi in senso inverso per cinque secondi.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Se dispone di una sequenza temporale contenitore figlio <xref:System.Windows.Media.Animation.Timeline> oggetti, essi invertire quando il contenitore della sequenza temporale. Per ulteriori esempi, vedere [specificare se una sequenza temporale invertito automaticamente](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>Proprietà BeginTime  
 Il <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà consente di specificare l'inizio di una sequenza temporale.  Il momento di avvio di una sequenza temporale è relativo alla sequenza temporale padre. Un momento di avvio pari a zero secondi indica che la sequenza temporale viene avviata all'avvio della sequenza padre. Qualsiasi altro valore crea un offset tra il momento di avvio della riproduzione della sequenza temporale padre e quello della sequenza temporale figlio. Un momento di avvio di due secondi indica ad esempio che la riproduzione della sequenza temporale viene avviata quando la sequenza temporale padre ha raggiunto un valore di due secondi. Per impostazione predefinita, il momento di avvio di tutte le sequenze temporali è pari a zero secondi. È inoltre possibile impostare una sequenza temporale l'ora di inizio `null`, che impedisce l'avvio la sequenza temporale. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], specificare null tramite il [estensione di Markup X:null](../../../../docs/framework/xaml-services/x-null-markup-extension.md).  
  
 Si noti che l'ora di inizio non è applicato ogni volta che si ripete una sequenza temporale perché il relativo <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> impostazione. Se si crea un'animazione con un <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> di 10 secondi e un <xref:System.Windows.Media.Animation.RepeatBehavior> di <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, non vi sarà un ritardo di 10 secondi prima che l'animazione riprodotto per la prima volta, ma non a ogni ripetizione successivi. Se la sequenza temporale padre dell'animazione tuttavia venisse riavviata o ripetuta, verrebbe applicato il ritardo di 10 secondi.  
  
 Il <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà è utile per scaglionare le sequenze temporali. Nell'esempio seguente viene creato un <xref:System.Windows.Media.Animation.Storyboard> che ha due figlio <xref:System.Windows.Media.Animation.DoubleAnimation> oggetti. La prima animazione è un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di cinque secondi, mentre la seconda è una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di 3 secondi. Nell'esempio viene impostata la <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> del secondo <xref:System.Windows.Media.Animation.DoubleAnimation> su 5 secondi, in modo che non viene avviata la riproduzione dopo il primo <xref:System.Windows.Media.Animation.DoubleAnimation> termina.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>Proprietà FillBehavior  
 Quando un <xref:System.Windows.Media.Animation.Timeline> raggiunge la fine della durata totale attiva, la <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà consente di specificare se si arresta o mantiene l'ultimo valore. Un'animazione con un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> di <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "contiene" il valore di output: proprietà da animare conserva l'ultimo valore dell'animazione. Il valore <xref:System.Windows.Media.Animation.FillBehavior.Stop> che provoca l'arresto di animazione effetto sulla proprietà di destinazione dopo la scadenza.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Media.Animation.Storyboard> che ha due figlio <xref:System.Windows.Media.Animation.DoubleAnimation> oggetti. Entrambi <xref:System.Windows.Media.Animation.DoubleAnimation> animano oggetti di <xref:System.Windows.FrameworkElement.Width%2A> di un <xref:System.Windows.Shapes.Rectangle> da 0 a 100. Il <xref:System.Windows.Shapes.Rectangle> elementi hanno non animati <xref:System.Windows.FrameworkElement.Width%2A> valori pari a 500 [device independent pixel].  
  
-   Il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà del primo <xref:System.Windows.Media.Animation.DoubleAnimation> è impostato su <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, il valore predefinito. Di conseguenza, la larghezza del rettangolo rimane su 100 dopo il <xref:System.Windows.Media.Animation.DoubleAnimation> termina.  
  
-   Il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> la proprietà del secondo <xref:System.Windows.Media.Animation.DoubleAnimation> è impostato su <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Di conseguenza, il <xref:System.Windows.FrameworkElement.Width%2A> del secondo <xref:System.Windows.Shapes.Rectangle> ritorna a 500 dopo il <xref:System.Windows.Media.Animation.DoubleAnimation> termina.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Proprietà che controllano la velocità di una sequenza temporale  
 La <xref:System.Windows.Media.Animation.Timeline> classe fornisce tre proprietà per specificare la velocità:  
  
-   <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> : Specifica la velocità, rispetto al relativo elemento padre, in corrispondenza del quale avanzamento del tempo un <xref:System.Windows.Media.Animation.Timeline>. I valori maggiori di uno di aumentare la velocità del <xref:System.Windows.Media.Animation.Timeline> e del relativo figlio <xref:System.Windows.Media.Animation.Timeline> oggetti, i valori compresi tra zero e uno subire rallentamenti. Il valore 1 indica che <xref:System.Windows.Media.Animation.Timeline> avanza alla stessa velocità del relativo oggetto padre. Il <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> di una sequenza temporale contenitore avrà effetto su tutti del relativo figlio <xref:System.Windows.Media.Animation.Timeline> anche gli oggetti.  
  
-   <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> -Specifica la percentuale del <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di una sequenza temporale trascorsa accelerando. Per un esempio, vedere [procedura: velocizzare o rallentare un'animazione](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md). 
  
-   <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> -Specifica la percentuale del <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di una sequenza temporale trascorsa decelerando. Per un esempio, vedere [procedura: velocizzare o rallentare un'animazione](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sull'animazione e sul sistema di temporizzazione](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Cenni preliminari sugli eventi di tempo](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [Esempio di comportamento temporale di un'animazione](http://go.microsoft.com/fwlink/?LinkID=159970)
