---
title: Cenni preliminari sull'animazione e sul sistema di temporizzazione
ms.date: 03/30/2017
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
ms.openlocfilehash: bfb9a337a604fe8d86d208344d4371748e28f285
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557966"
---
# <a name="animation-and-timing-system-overview"></a>Cenni preliminari sull'animazione e sul sistema di temporizzazione
Questo argomento viene descritto l'utilizzo di animazione, il sistema di temporizzazione <xref:System.Windows.Media.Animation.Timeline>, e <xref:System.Windows.Media.Animation.Clock> classi per l'animazione di proprietà.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per la comprensione di questo argomento, è necessario essere in grado di usare le animazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per animare le proprietà, come descritto in [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). È anche utile conoscere le proprietà di dipendenza. Per altre informazioni, vedere [Cenni preliminari sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>   
## <a name="timelines-and-clocks"></a>Sequenze temporali e orologi  
 Il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) descritto come un <xref:System.Windows.Media.Animation.Timeline> rappresenta un segmento di tempo e un'animazione è un tipo di <xref:System.Windows.Media.Animation.Timeline> che produce valori di output. Di per sé un <xref:System.Windows.Media.Animation.Timeline>, non esegue alcuna operazione tranne limita a descrivere un intervallo di tempo. È la sequenza temporale <xref:System.Windows.Media.Animation.Clock> oggetto che esegue il lavoro effettivo. Analogamente, animazione non anima proprio proprietà: una classe di animazione viene descritto il calcolo di valori di output, ma è il <xref:System.Windows.Media.Animation.Clock> che è stato creato per l'animazione che l'output di animazione e ad applicarlo alle proprietà.  
  
 Oggetto <xref:System.Windows.Media.Animation.Clock> è un tipo speciale di oggetto che gestisce lo stato di runtime correlati alla temporizzazione per il <xref:System.Windows.Media.Animation.Timeline>. Fornisce tre informazioni essenziali per l'animazione e il sistema di temporizzazione: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>, e <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>. Oggetto <xref:System.Windows.Media.Animation.Clock> determina l'ora corrente, lo stato di avanzamento e lo stato tramite i comportamenti di temporizzazione descritti dal relativo <xref:System.Windows.Media.Animation.Timeline>: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>e così via.  
  
 Nella maggior parte dei casi, un <xref:System.Windows.Media.Animation.Clock> viene creato automaticamente per la sequenza temporale. Quando si aggiunge un'animazione con un <xref:System.Windows.Media.Animation.Storyboard> o <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> (metodo), gli orologi creati automaticamente per le sequenze temporali e le animazioni e applicati alle proprietà di destinazione. È inoltre possibile creare un <xref:System.Windows.Media.Animation.Clock> in modo esplicito utilizzando il <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> metodo i <xref:System.Windows.Media.Animation.Timeline>. Il <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> metodo crea un orologio del tipo appropriato per il <xref:System.Windows.Media.Animation.Timeline> su cui viene chiamato. Se il <xref:System.Windows.Media.Animation.Timeline> contiene sequenze temporali figlio, viene creato <xref:System.Windows.Media.Animation.Clock> anche oggetti relativa. Il valore risultante <xref:System.Windows.Media.Animation.Clock> oggetti siano disposti in strutture ad albero che corrisponde alla struttura del <xref:System.Windows.Media.Animation.Timeline> della struttura ad albero di oggetti da cui sono stati creati.  
  
 Esistono tipi di orologi diversi per tipi di sequenze temporali diversi. La tabella seguente mostra il <xref:System.Windows.Media.Animation.Clock> tipi che corrispondono ad alcune delle diverse <xref:System.Windows.Media.Animation.Timeline> tipi.  
  
|Tipo di sequenza temporale|Tipo di orologio|Scopo dell'orologio|  
|-------------------|----------------|-------------------|  
|Animazione (eredita da <xref:System.Windows.Media.Animation.AnimationTimeline>)|<xref:System.Windows.Media.Animation.AnimationClock>|Genera valori di output per una proprietà di dipendenza.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Elabora un file multimediale.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Gruppi e controlli figlio <xref:System.Windows.Media.Animation.Clock> oggetti|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Gruppi e controlli figlio <xref:System.Windows.Media.Animation.Clock> oggetti|  
  
 È possibile applicare qualsiasi <xref:System.Windows.Media.Animation.AnimationClock> oggetti crei alle proprietà di dipendenza compatibili con il <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> metodo.  
  
 In scenari di prestazioni, ad esempio un numero elevato di oggetti simili, l'animazione gestisce la propria <xref:System.Windows.Media.Animation.Clock> utilizzare può offrire i vantaggi di prestazioni.  
  
<a name="timemanager"></a>   
## <a name="clocks-and-the-time-manager"></a>Orologi e gestore del tempo  
 Quando si aggiunge un'animazione oggetti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è il gestore del tempo che gestisce il <xref:System.Windows.Media.MediaPlayer.Clock%2A> gli oggetti creati per le sequenze temporali. Il gestore del tempo è la radice di una struttura ad albero di oggetti <xref:System.Windows.Media.MediaPlayer.Clock%2A> e controlla il flusso di tempo nella struttura.  Il gestore del tempo viene creato automaticamente per ogni applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ed è invisibile allo sviluppatore di applicazioni. Ogni secondo vengono emessi numerosi e il numero effettivo di tick emessi ogni secondo varia a seconda delle risorse di sistema disponibili. Durante ciascuno di questi segni di graduazione, viene calcolato lo stato di tutti <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> oggetti nell'albero della durata.  
  
 Nella figura seguente viene illustrata la relazione tra il gestore del tempo e <xref:System.Windows.Media.Animation.AnimationClock>e una proprietà di dipendenza animata.  
  
 ![Componenti del sistema di intervallo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
Animazione di una proprietà  
  
 Tick, viene aggiornata l'ora di ogni <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> nell'applicazione. Se il <xref:System.Windows.Media.Animation.Clock> è un <xref:System.Windows.Media.Animation.AnimationClock>, Usa il <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> metodo il <xref:System.Windows.Media.Animation.AnimationTimeline> da cui è stato creato per calcolare il corrente valore di output. Il <xref:System.Windows.Media.Animation.AnimationClock> fornisce il <xref:System.Windows.Media.Animation.AnimationTimeline> con l'ora locale corrente, un valore di input è in genere il valore della proprietà di base e un valore di destinazione predefinito. Quando si recupera il valore di un oggetto animato utilizzando proprietà di <xref:System.Windows.DependencyObject.GetValue%2A> metodo o la funzione di accesso CLR, si otterrà l'output del relativo <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="clock-groups"></a>Gruppi di orologi  
 Nella sezione precedente descritto esistono diversi tipi di <xref:System.Windows.Media.Animation.Clock> oggetti per i diversi tipi di sequenze temporali. Nella figura seguente viene illustrata la relazione tra il gestore del tempo, un <xref:System.Windows.Media.Animation.ClockGroup>, <xref:System.Windows.Media.Animation.AnimationClock>e una proprietà di dipendenza animata. Oggetto <xref:System.Windows.Media.Animation.ClockGroup> viene creato per le sequenze temporali che raggruppano altre sequenze, ad esempio il <xref:System.Windows.Media.Animation.Storyboard> (classe), che raggruppa animazioni e altre sequenze temporali.  
  
 ![Componenti del sistema di intervallo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
Gruppo di orologi  
  
#### <a name="composition"></a>Composizione  
 È possibile associare più orologi a una singola proprietà e in tal caso ogni orologio usa il valore di output dell'orologio precedente come valore di base. La figura seguente mostra tre <xref:System.Windows.Media.Animation.AnimationClock> oggetti applicata alla stessa proprietà. L'orologio1 usa il valore di base della proprietà animata come input e lo usa per generare l'output. L'orologio2 accetta l'output dall'orologio1 come input e lo usa per generare l'output. L'orologio3 accetta l'output dall'orologio2 come input e lo usa per generare l'output. Quando più orologi interessano contemporaneamente una stessa proprietà, formano una catena di composizione.  
  
 ![Componenti del sistema di intervallo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
Catena di composizione  
  
 Si noti che anche se viene creata una relazione tra l'input e output del <xref:System.Windows.Media.Animation.AnimationClock> oggetti nella catena di composizione, i comportamenti di temporizzazione non sono interessati; <xref:System.Windows.Media.Animation.Clock> oggetti (inclusi <xref:System.Windows.Media.Animation.AnimationClock> oggetti) presentano una dipendenza gerarchica padre <xref:System.Windows.Media.Animation.Clock> oggetti.  
  
 Per applicare più orologi alla stessa proprietà, utilizzare il <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> quando si applica un <xref:System.Windows.Media.Animation.Storyboard>, animazione, o <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="ticks-and-event-consolidation"></a>Tick e consolidamento degli eventi  
 Oltre a calcolare i valori di output, a ogni tick il gestore del tempo determina lo stato di ogni orologio e genera gli eventi appropriati.  
  
 Sebbene gli eventi tick siano piuttosto frequenti, è possibile che tra essi avvengano vari eventi. Ad esempio, un <xref:System.Windows.Media.Animation.Clock> potrebbe essere arrestato, avviato e nuovamente interrotta, nel qual caso il <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> valore verrà cambiato tre volte. In teoria, il <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento può essere generato più volte in un singolo tick; tuttavia, il motore di temporizzazione consente di consolidare gli eventi, in modo che il <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento può essere generato più di una volta per tick. Questo vale per tutti gli eventi di temporizzazione: al massimo un evento di ogni tipo viene generato per un determinato <xref:System.Windows.Media.Animation.Clock> oggetto.  
  
 Quando un <xref:System.Windows.Media.Animation.Clock> modifica gli Stati e torna allo stato originale tra segni di graduazione (ad esempio la modifica da <xref:System.Windows.Media.Animation.ClockState.Active> a <xref:System.Windows.Media.Animation.ClockState.Stopped> e al <xref:System.Windows.Media.Animation.ClockState.Active>), viene comunque generato l'evento associato.  
  
 Per altre informazioni sugli eventi di temporizzazione, vedere [Cenni preliminari sugli eventi di tempo](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## <a name="current-values-and-base-values-of-properties"></a>Valori correnti e valori di base delle proprietà  
 A una proprietà che è possibile animare possono essere associati due valori, uno di base e uno corrente. Quando si imposta proprietà utilizzando la funzione di accesso CLR o <xref:System.Windows.DependencyObject.SetValue%2A> (metodo), impostare il valore di base. Quando una proprietà non è animata, i valori di base e corrente corrispondono.  
  
 Quando si aggiunge un'animazione, una proprietà di <xref:System.Windows.Media.Animation.AnimationClock> imposta la proprietà *corrente* valore. Il recupero del valore della proprietà tramite la funzione di accesso CLR o <xref:System.Windows.DependencyObject.GetValue%2A> il metodo restituisce l'output del <xref:System.Windows.Media.Animation.AnimationClock> quando il <xref:System.Windows.Media.Animation.AnimationClock> è <xref:System.Windows.Media.Animation.ClockState.Active> o <xref:System.Windows.Media.Animation.ClockState.Filling>. È possibile recuperare il valore della proprietà base utilizzando il <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sugli eventi di tempo](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)  
 [Cenni preliminari sui comportamenti temporali](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
