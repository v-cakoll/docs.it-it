---
title: Cenni preliminari sull'animazione e sul sistema di temporizzazione
ms.date: 03/30/2017
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
ms.openlocfilehash: f64431e7804ba6e068a3d05f512c6ead089d7712
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079318"
---
# <a name="animation-and-timing-system-overview"></a>Cenni preliminari sull'animazione e sul sistema di temporizzazione
In questo argomento viene descritto l'utilizzo di animazione, il sistema di temporizzazione <xref:System.Windows.Media.Animation.Timeline>, e <xref:System.Windows.Media.Animation.Clock> alle classi di animazione di proprietà.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per la comprensione di questo argomento, è necessario essere in grado di usare le animazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per animare le proprietà, come descritto in [Cenni preliminari sull'animazione](animation-overview.md). È anche utile conoscere le proprietà di dipendenza. Per altre informazioni, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>   
## <a name="timelines-and-clocks"></a>Sequenze temporali e orologi  
 Il [Cenni preliminari sull'animazione](animation-overview.md) descritta come un <xref:System.Windows.Media.Animation.Timeline> rappresenta un segmento di tempo e un'animazione è un tipo di <xref:System.Windows.Media.Animation.Timeline> che produce valori di output. Di per sé un <xref:System.Windows.Media.Animation.Timeline>, non esegue alcuna operazione oltre limita a descrivere un intervallo di tempo. Si tratta della sequenza temporale <xref:System.Windows.Media.Animation.Clock> oggetto che esegue il lavoro effettivo. Analogamente, animazione non anima le proprietà: una classe di animazione descrive il calcolo di valori di output, ma è il <xref:System.Windows.Media.Animation.Clock> che è stato creato per l'animazione che l'output di animazione e ad applicarlo alle proprietà.  
  
 Oggetto <xref:System.Windows.Media.Animation.Clock> è un tipo speciale di oggetto che gestisce lo stato di runtime correlato al tempo per il <xref:System.Windows.Media.Animation.Timeline>. Specifica tre informazioni essenziali per il sistema di temporizzazione e animazione: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>, e <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>. Oggetto <xref:System.Windows.Media.Animation.Clock> determina l'ora corrente, lo stato di avanzamento e stato utilizzando i comportamenti di temporizzazione descritti dal relativo <xref:System.Windows.Media.Animation.Timeline>: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>e così via.  
  
 Nella maggior parte dei casi, un <xref:System.Windows.Media.Animation.Clock> viene creato automaticamente per la sequenza temporale. Quando esegue un'animazione tramite un <xref:System.Windows.Media.Animation.Storyboard> o il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo orologi vengono automaticamente creati per le sequenze temporali e le animazioni e applicati alle proprietà di destinazione. È anche possibile creare un <xref:System.Windows.Media.Animation.Clock> in modo esplicito tramite il <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> metodo le <xref:System.Windows.Media.Animation.Timeline>. Il <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> metodo crea un orologio del tipo appropriato per il <xref:System.Windows.Media.Animation.Timeline> sul quale viene chiamato. Se il <xref:System.Windows.Media.Animation.Timeline> contiene le sequenze temporali figlio, viene creato <xref:System.Windows.Media.Animation.Clock> oggetti anche per loro. Risultante <xref:System.Windows.Media.Animation.Clock> oggetti siano disposti in strutture ad albero che corrisponde alla struttura del <xref:System.Windows.Media.Animation.Timeline> della struttura ad albero di oggetti da cui sono stati creati.  
  
 Esistono tipi di orologi diversi per tipi di sequenze temporali diversi. La tabella seguente illustra il <xref:System.Windows.Media.Animation.Clock> i tipi corrispondenti ad alcuni dei diversi <xref:System.Windows.Media.Animation.Timeline> tipi.  
  
|Tipo di sequenza temporale|Tipo di orologio|Scopo dell'orologio|  
|-------------------|----------------|-------------------|  
|Animazione (eredita da <xref:System.Windows.Media.Animation.AnimationTimeline>)|<xref:System.Windows.Media.Animation.AnimationClock>|Genera valori di output per una proprietà di dipendenza.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Elabora un file multimediale.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Raggruppa e controlla figlio <xref:System.Windows.Media.Animation.Clock> oggetti|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Raggruppa e controlla figlio <xref:System.Windows.Media.Animation.Clock> oggetti|  
  
 È possibile applicare qualsiasi <xref:System.Windows.Media.Animation.AnimationClock> oggetti crei alle proprietà di dipendenza compatibili tramite le <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> (metodo).  
  
 In scenari a elevato utilizzo di prestazioni, ad esempio l'animazione di un numero elevato di oggetti simili, gestire il proprio <xref:System.Windows.Media.Animation.Clock> uso può offrire i vantaggi delle prestazioni.  
  
<a name="timemanager"></a>   
## <a name="clocks-and-the-time-manager"></a>Orologi e gestore del tempo  
 Quando si animano oggetti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è il gestore del tempo che gestisce il <xref:System.Windows.Media.MediaPlayer.Clock%2A> gli oggetti creati per le sequenze temporali. Il gestore del tempo è la radice di una struttura ad albero di oggetti <xref:System.Windows.Media.MediaPlayer.Clock%2A> e controlla il flusso di tempo nella struttura.  Il gestore del tempo viene creato automaticamente per ogni applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ed è invisibile allo sviluppatore di applicazioni. Ogni secondo vengono emessi numerosi e il numero effettivo di tick emessi ogni secondo varia a seconda delle risorse di sistema disponibili. Durante ogni tick, viene calcolato lo stato di tutti i <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> oggetti nell'albero di temporizzazione.  
  
 Nella figura seguente mostra la relazione tra il gestore del tempo, e <xref:System.Windows.Media.Animation.AnimationClock>e una proprietà di dipendenza animata.  
  
 ![Componenti del sistema di temporizzazione](./media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
Animazione di una proprietà  
  
 Quando il tick viene aggiornata l'ora di ogni <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> nell'applicazione. Se il <xref:System.Windows.Media.Animation.Clock> è un <xref:System.Windows.Media.Animation.AnimationClock>, Usa le <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> metodo del <xref:System.Windows.Media.Animation.AnimationTimeline> da cui è stata creata per la quale calcolare il corrente valore di output. Il <xref:System.Windows.Media.Animation.AnimationClock> fornisce il <xref:System.Windows.Media.Animation.AnimationTimeline> con l'ora locale corrente, un valore di input, che è in genere il valore della proprietà di base e un valore di destinazione predefinito. Quando si recupera il valore di una proprietà con il <xref:System.Windows.DependencyObject.GetValue%2A> metodo o la funzione di accesso CLR, si otterrà l'output del relativo <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="clock-groups"></a>Gruppi di orologi  
 Nella sezione precedente descrive che esistono diversi tipi di <xref:System.Windows.Media.Animation.Clock> oggetti per i diversi tipi di sequenze temporali. Nella figura seguente mostra la relazione tra il gestore del tempo, un <xref:System.Windows.Media.Animation.ClockGroup>, un <xref:System.Windows.Media.Animation.AnimationClock>e una proprietà di dipendenza animata. Oggetto <xref:System.Windows.Media.Animation.ClockGroup> viene creato per le sequenze temporali che raggruppano altre sequenze, ad esempio il <xref:System.Windows.Media.Animation.Storyboard> (classe), che raggruppa animazioni e le altre sequenze temporali.  
  
 ![Componenti del sistema di temporizzazione](./media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
Gruppo di orologi  
  
#### <a name="composition"></a>Composizione  
 È possibile associare più orologi a una singola proprietà e in tal caso ogni orologio usa il valore di output dell'orologio precedente come valore di base. La figura seguente mostra tre <xref:System.Windows.Media.Animation.AnimationClock> oggetti applicati alla stessa proprietà. L'orologio1 usa il valore di base della proprietà animata come input e lo usa per generare l'output. L'orologio2 accetta l'output dall'orologio1 come input e lo usa per generare l'output. L'orologio3 accetta l'output dall'orologio2 come input e lo usa per generare l'output. Quando più orologi interessano contemporaneamente una stessa proprietà, formano una catena di composizione.  
  
 ![Componenti del sistema di temporizzazione](./media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
Catena di composizione  
  
 Si noti che anche se viene creata una relazione tra l'input e output del <xref:System.Windows.Media.Animation.AnimationClock> oggetti nella catena di composizione, i comportamenti di temporizzazione non sono interessati; <xref:System.Windows.Media.Animation.Clock> oggetti (inclusi <xref:System.Windows.Media.Animation.AnimationClock> oggetti) presentano una dipendenza gerarchica nel relativo elemento padre <xref:System.Windows.Media.Animation.Clock> oggetti.  
  
 Per applicare più orologi alla stessa proprietà, usare il <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> quando si applica un <xref:System.Windows.Media.Animation.Storyboard>, animazione, o <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="ticks-and-event-consolidation"></a>Tick e consolidamento degli eventi  
 Oltre a calcolare i valori di output, a ogni tick il gestore del tempo determina lo stato di ogni orologio e genera gli eventi appropriati.  
  
 Sebbene gli eventi tick siano piuttosto frequenti, è possibile che tra essi avvengano vari eventi. Ad esempio, un <xref:System.Windows.Media.Animation.Clock> potrebbe essere stato arrestato, avviato e interrotta nuovamente, nel qual caso relativo <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> valore verrà cambiato tre volte. In teoria, il <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento potrebbe essere generato più volte in un singolo segno di graduazione; tuttavia, il motore di temporizzazione consolida gli eventi, in modo che il <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento può essere generato al massimo una volta per tick. Questo vale per tutti gli eventi di temporizzazione: al massimo un evento di ogni tipo viene generato per un determinato <xref:System.Windows.Media.Animation.Clock> oggetto.  
  
 Quando un <xref:System.Windows.Media.Animation.Clock> modifica gli Stati e torna allo stato originale tra segni di graduazione (ad esempio la modifica da <xref:System.Windows.Media.Animation.ClockState.Active> al <xref:System.Windows.Media.Animation.ClockState.Stopped> e tornare alla <xref:System.Windows.Media.Animation.ClockState.Active>), viene comunque generato l'evento associato.  
  
 Per altre informazioni sugli eventi di temporizzazione, vedere [Cenni preliminari sugli eventi di tempo](timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## <a name="current-values-and-base-values-of-properties"></a>Valori correnti e valori di base delle proprietà  
 A una proprietà che è possibile animare possono essere associati due valori, uno di base e uno corrente. Quando si imposta proprietà usando la relativa funzione di accesso CLR o <xref:System.Windows.DependencyObject.SetValue%2A> metodo, impostane il valore di base. Quando una proprietà non è animata, i valori di base e corrente corrispondono.  
  
 Quando si anima una proprietà, il <xref:System.Windows.Media.Animation.AnimationClock> imposta la proprietà *corrente* valore. Recuperare il valore della proprietà tramite la funzione di accesso CLR o il <xref:System.Windows.DependencyObject.GetValue%2A> metodo restituisce l'output del <xref:System.Windows.Media.Animation.AnimationClock> quando il <xref:System.Windows.Media.Animation.AnimationClock> viene <xref:System.Windows.Media.Animation.ClockState.Active> o <xref:System.Windows.Media.Animation.ClockState.Filling>. È possibile recuperare il valore della proprietà base usando la <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> (metodo).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli eventi di tempo](timing-events-overview.md)
- [Cenni preliminari sui comportamenti temporali](timing-behaviors-overview.md)
