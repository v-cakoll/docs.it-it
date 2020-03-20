---
title: Cenni preliminari sull'animazione e sul sistema di temporizzazione
ms.date: 03/30/2017
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
ms.openlocfilehash: d0ac2a8160a1e6f9bcdb333593ec207954b391aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187713"
---
# <a name="animation-and-timing-system-overview"></a>Cenni preliminari sull'animazione e sul sistema di temporizzazione
In questo argomento viene descritto come <xref:System.Windows.Media.Animation.Timeline>il <xref:System.Windows.Media.Animation.Clock> sistema di temporizzazione utilizza l'animazione, , e le classi per animare le proprietà.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per la comprensione di questo argomento, è necessario essere in grado di usare le animazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per animare le proprietà, come descritto in [Cenni preliminari sull'animazione](animation-overview.md). È anche utile conoscere le proprietà di dipendenza. Per altre informazioni, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>
## <a name="timelines-and-clocks"></a>Sequenze temporali e orologi  
 Il Cenni preliminari sull'animazione descrive come un [Animation Overview](animation-overview.md) <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline> rappresenta un segmento di tempo e un'animazione è un tipo di che produce valori di output. Di per <xref:System.Windows.Media.Animation.Timeline>sé, un oggetto , non fa altro che descrivere un segmento di tempo. È l'oggetto della <xref:System.Windows.Media.Animation.Clock> linea temporale che fa il lavoro reale. Analogamente, l'animazione non anima effettivamente le proprietà: una classe di <xref:System.Windows.Media.Animation.Clock> animazione descrive come devono essere calcolati i valori di output, ma è l'oggetto che è stato creato per l'animazione che guida l'output dell'animazione e lo applica alle proprietà.  
  
 Un <xref:System.Windows.Media.Animation.Clock> oggetto è un tipo speciale di oggetto che mantiene <xref:System.Windows.Media.Animation.Timeline>lo stato di runtime correlato alla temporizzazione per l'oggetto . Fornisce tre bit di informazioni che sono essenziali per <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A> <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>il <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>sistema di animazione e temporizzazione: , , e . Un <xref:System.Windows.Media.Animation.Clock> oggetto determina l'ora corrente, lo stato di <xref:System.Windows.Media.Animation.Timeline>avanzamento e lo stato utilizzando i comportamenti di temporizzazione descritti dai relativi : <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>e così via.  
  
 Nella maggior parte <xref:System.Windows.Media.Animation.Clock> dei casi, viene creato automaticamente un oggetto per la sequenza temporale. Quando si aggiunge <xref:System.Windows.Media.Animation.Storyboard> un'animazione utilizzando un o il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo , gli orologi vengono creati automaticamente per le sequenze temporali e le animazioni e applicati alle proprietà di destinazione. È inoltre possibile <xref:System.Windows.Media.Animation.Clock> creare un <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> oggetto <xref:System.Windows.Media.Animation.Timeline>in modo esplicito utilizzando il metodo dell'oggetto . Il <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> metodo crea un clock del <xref:System.Windows.Media.Animation.Timeline> tipo appropriato per il su cui viene chiamato. Se <xref:System.Windows.Media.Animation.Timeline> l'oggetto contiene sequenze temporali figlio, crea <xref:System.Windows.Media.Animation.Clock> anche oggetti per loro. Gli <xref:System.Windows.Media.Animation.Clock> oggetti risultanti sono disposti in <xref:System.Windows.Media.Animation.Timeline> alberi che corrispondono alla struttura dell'albero degli oggetti da cui vengono creati.  
  
 Esistono tipi di orologi diversi per tipi di sequenze temporali diversi. Nella tabella seguente <xref:System.Windows.Media.Animation.Clock> vengono illustrati i tipi <xref:System.Windows.Media.Animation.Timeline> che corrispondono ad alcuni dei diversi tipi.  
  
|Tipo di sequenza temporale|Tipo di orologio|Scopo dell'orologio|  
|-------------------|----------------|-------------------|  
|Animazione (eredita <xref:System.Windows.Media.Animation.AnimationTimeline>da )|<xref:System.Windows.Media.Animation.AnimationClock>|Genera valori di output per una proprietà di dipendenza.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Elabora un file multimediale.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Raggruppa e controlla <xref:System.Windows.Media.Animation.Clock> i relativi oggetti figlio|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Raggruppa e controlla <xref:System.Windows.Media.Animation.Clock> i relativi oggetti figlio|  
  
 È possibile <xref:System.Windows.Media.Animation.AnimationClock> applicare qualsiasi oggetto creato alle proprietà <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> di dipendenza compatibili utilizzando il metodo .  
  
 In scenari che richiedono un uso intensivo delle prestazioni, <xref:System.Windows.Media.Animation.Clock> ad esempio l'animazione di un numero elevato di oggetti simili, la gestione del proprio utilizzo può offrire vantaggi in termini di prestazioni.  
  
<a name="timemanager"></a>
## <a name="clocks-and-the-time-manager"></a>Orologi e gestore del tempo  
 Quando si animano gli oggetti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è <xref:System.Windows.Media.MediaPlayer.Clock%2A> il gestore del tempo che gestisce gli oggetti creati per le sequenze temporali. Il gestore del tempo è la radice di una struttura ad albero di oggetti <xref:System.Windows.Media.MediaPlayer.Clock%2A> e controlla il flusso di tempo nella struttura.  Il gestore del tempo viene creato automaticamente per ogni applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ed è invisibile allo sviluppatore di applicazioni. Ogni secondo vengono emessi numerosi e il numero effettivo di tick emessi ogni secondo varia a seconda delle risorse di sistema disponibili. Durante ognuno di questi segni di graduazione, <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> il gestore del tempo calcola lo stato di tutti gli oggetti nell'albero di temporizzazione.  
  
 Nella figura seguente viene illustrata la <xref:System.Windows.Media.Animation.AnimationClock>relazione tra il gestore del tempo e , e una proprietà di dipendenza animata.  
  
 ![Componenti del sistema di temporizzazione](./media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
Animazione di una proprietà  
  
 Quando il gestore del tempo spunta, aggiorna l'ora di ogni <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> nell'applicazione. Se <xref:System.Windows.Media.Animation.Clock> l'oggetto è un <xref:System.Windows.Media.Animation.AnimationClock>oggetto , viene utilizzato il <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> metodo dell'oggetto <xref:System.Windows.Media.Animation.AnimationTimeline> da cui è stato creato per calcolare il valore di output corrente. Fornisce <xref:System.Windows.Media.Animation.AnimationClock> l'oggetto <xref:System.Windows.Media.Animation.AnimationTimeline> con l'ora locale corrente, un valore di input, che in genere è il valore di base della proprietà, e un valore di destinazione predefinito. Quando si recupera il valore di <xref:System.Windows.DependencyObject.GetValue%2A> un oggetto animato dalla proprietà utilizzando <xref:System.Windows.Media.Animation.AnimationClock>il metodo o la relativa funzione di accesso CLR, si ottiene l'output del relativo oggetto .  
  
#### <a name="clock-groups"></a>Gruppi di orologi  
 Nella sezione precedente è stato descritto <xref:System.Windows.Media.Animation.Clock> come esistono diversi tipi di oggetti per diversi tipi di sequenze temporali. Nella figura seguente viene illustrata la <xref:System.Windows.Media.Animation.ClockGroup>relazione <xref:System.Windows.Media.Animation.AnimationClock>tra il gestore del tempo, un oggetto , un oggetto e una proprietà di dipendenza animata. Viene <xref:System.Windows.Media.Animation.ClockGroup> creato un oggetto per le sequenze <xref:System.Windows.Media.Animation.Storyboard> temporali che raggruppano altre sequenze temporali, ad esempio la classe, che raggruppa le animazioni e altre sequenze temporali.  
  
 ![Componenti del sistema di temporizzazione](./media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
Gruppo di orologi  
  
#### <a name="composition"></a>Composizione  
 È possibile associare più orologi a una singola proprietà e in tal caso ogni orologio usa il valore di output dell'orologio precedente come valore di base. Nella figura seguente <xref:System.Windows.Media.Animation.AnimationClock> vengono illustrati tre oggetti applicati alla stessa proprietà. L'orologio1 usa il valore di base della proprietà animata come input e lo usa per generare l'output. L'orologio2 accetta l'output dall'orologio1 come input e lo usa per generare l'output. L'orologio3 accetta l'output dall'orologio2 come input e lo usa per generare l'output. Quando più orologi interessano contemporaneamente una stessa proprietà, formano una catena di composizione.  
  
 ![Componenti del sistema di temporizzazione](./media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
Catena di composizione  
  
 Si noti che anche se viene creata <xref:System.Windows.Media.Animation.AnimationClock> una relazione tra l'input e l'output degli oggetti nella catena di composizione, i relativi comportamenti di temporizzazione non vengono influenzati; <xref:System.Windows.Media.Animation.Clock> gli oggetti <xref:System.Windows.Media.Animation.AnimationClock> (inclusi gli oggetti) hanno <xref:System.Windows.Media.Animation.Clock> una dipendenza gerarchica dai relativi oggetti padre.  
  
 Per applicare più orologi alla stessa <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> proprietà, utilizzare <xref:System.Windows.Media.Animation.Storyboard>il quando <xref:System.Windows.Media.Animation.AnimationClock>si applica un oggetto , un'animazione o un file .  
  
#### <a name="ticks-and-event-consolidation"></a>Tick e consolidamento degli eventi  
 Oltre a calcolare i valori di output, a ogni tick il gestore del tempo determina lo stato di ogni orologio e genera gli eventi appropriati.  
  
 Sebbene gli eventi tick siano piuttosto frequenti, è possibile che tra essi avvengano vari eventi. Ad esempio, <xref:System.Windows.Media.Animation.Clock> un oggetto potrebbe essere arrestato, avviato <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> e nuovamente, nel qual caso il relativo valore verrà modificato tre volte. In teoria, l'evento <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> potrebbe essere generato più volte in un singolo tick; Tuttavia, il motore di temporizzazione consolida gli eventi, in modo che l'evento <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> può essere generato al massimo una volta per tick. Questo vale per tutti gli eventi di temporizzazione: al <xref:System.Windows.Media.Animation.Clock> massimo un evento di ogni tipo viene generato per un determinato oggetto.  
  
 Quando <xref:System.Windows.Media.Animation.Clock> un cambia stato e torna allo stato originale tra <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Stopped> i segni <xref:System.Windows.Media.Animation.ClockState.Active>di graduazione (ad esempio, la modifica da e verso il controllo di ), si verifica comunque l'evento associato.  
  
 Per altre informazioni sugli eventi di temporizzazione, vedere [Cenni preliminari sugli eventi di tempo](timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>
## <a name="current-values-and-base-values-of-properties"></a>Valori correnti e valori di base delle proprietà  
 A una proprietà che è possibile animare possono essere associati due valori, uno di base e uno corrente. Quando si imposta la proprietà utilizzando <xref:System.Windows.DependencyObject.SetValue%2A> la relativa funzione di accesso CLR o il metodo, si imposta il relativo valore di base. Quando una proprietà non è animata, i valori di base e corrente corrispondono.  
  
 Quando si anima una <xref:System.Windows.Media.Animation.AnimationClock> proprietà, il imposta il valore *corrente* della proprietà. Il recupero del valore della proprietà tramite <xref:System.Windows.DependencyObject.GetValue%2A> la relativa funzione <xref:System.Windows.Media.Animation.AnimationClock> di <xref:System.Windows.Media.Animation.AnimationClock> <xref:System.Windows.Media.Animation.ClockState.Active> accesso <xref:System.Windows.Media.Animation.ClockState.Filling>CLR o il metodo restituisce l'output di quando l'oggetto è o . È possibile recuperare il valore di <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> base della proprietà utilizzando il metodo .  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli eventi di tempo](timing-events-overview.md)
- [Cenni preliminari sui comportamenti temporali](timing-behaviors-overview.md)
