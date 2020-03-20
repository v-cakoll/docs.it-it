---
title: Cenni preliminari sugli eventi di tempo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
ms.openlocfilehash: ee45441e9ad09c60d8b61ecce4ef08b0027ce29e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145410"
---
# <a name="timing-events-overview"></a>Cenni preliminari sugli eventi di tempo
In questo argomento viene descritto come utilizzare <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> i cinque eventi di temporizzazione disponibili su e gli oggetti.  
  
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere questo argomento è necessario sapere come creare e usare le animazioni. Per iniziare a usare l'animazione, vedere [Cenni preliminari sull'animazione.](animation-overview.md)  
  
 Esistono diversi modi per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]animare le proprietà in :  
  
- **Utilizzo di oggetti storyboard** (markup <xref:System.Windows.Media.Animation.Storyboard> e codice): è possibile utilizzare oggetti per disporre e distribuire animazioni a uno o più oggetti. Per un esempio, consultate [Animare una proprietà utilizzando uno Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).  
  
- **Uso di animazioni locali** (solo codice): è possibile applicare <xref:System.Windows.Media.Animation.AnimationTimeline> gli oggetti direttamente alle proprietà che animano. Per un esempio, consultate [Animare una proprietà senza usare uno Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
- **Uso di orologi** (solo codice): è possibile gestire la creazione di orologi in modo esplicito e distribuire direttamente gli orologi di animazione.  Per un esempio, consultate [Animare una proprietà utilizzando un AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Poiché è possibile utilizzarli nel markup e <xref:System.Windows.Media.Animation.Storyboard> nel codice, gli esempi in questa panoramica usano oggetti. I concetti descritti possono tuttavia essere applicati ad altri metodi di animazione delle proprietà.  
  
### <a name="what-is-a-clock"></a>Che cos'è un orologio?  
 Una sequenza temporale, da sola, in realtà non fa altro che descrivere un intervallo di tempo. È l'oggetto della <xref:System.Windows.Media.Animation.Clock> sequenza temporale che esegue il lavoro reale: mantiene lo stato di runtime correlato alla temporizzazione per la sequenza temporale. Nella maggior parte dei casi, ad esempio quando si usano gli storyboard, viene creato automaticamente un orologio per la sequenza temporale. È anche possibile <xref:System.Windows.Media.Animation.Clock> creare un <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> oggetto in modo esplicito utilizzando il metodo . Per ulteriori <xref:System.Windows.Media.Animation.Clock> informazioni sugli oggetti, vedere Cenni preliminari sul [sistema di animazione e temporizzazione](animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>Perché usare gli eventi?  
 Fatta eccezione di una (ricerca allineata all'ultimo tick), tutte le operazioni di tempo interattive sono asincrone. Non è possibile sapere esattamente quando verranno eseguite. Questo può essere un problema quando è presente altro codice dipendente dall'operazione di tempo. Si supponga che si desidera interrompere una sequenza temporale che ha aggiunto un'animazione a un rettangolo. Dopo l'interruzione della sequenza temporale, viene modificato il colore del rettangolo.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 Nell'esempio precedente la seconda riga di codice potrebbe essere eseguita prima dell'interruzione dello storyboard. Ciò avviene perché l'interruzione è un'operazione asincrona. L'indicazione per l'interruzione di una sequenza temporale o di un orologio crea una "richiesta di interruzione" di ordinamenti che non viene elaborata fino al tick successivo del motore di temporizzazione.  
  
 Per eseguire i comandi dopo il completamento di una sequenza temporale, usare gli eventi di tempo. Nell'esempio seguente, un gestore eventi viene usato per modificare il colore di un rettangolo dopo l'interruzione della riproduzione dello storyboard.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Per un esempio più completo, vedere [Ricevere notifiche quando cambia lo stato di un orologio](how-to-receive-notification-when-clock-state-changes.md).  
  
## <a name="public-events"></a>Eventi pubblici  
 Le <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> classi e forniscono entrambi cinque eventi di temporizzazione. Nella tabella seguente sono elencati questi eventi e le condizioni che li attivano.  
  
|Event|Operazione interattiva di attivazione|Altri trigger|  
|-----------|--------------------------------------|--------------------|  
|**Operazione completata**|Passaggio al riempimento|L'orologio viene completato.|  
|**CurrentGlobalSpeedInvalidated**|Sospensione, ripresa, ricerca, impostazione di frequenza velocità, passaggio al riempimento, interruzione|L'orologio viene invertito, accelerato, avviato o interrotto.|  
|**CurrentStateInvalidated**|Inizio, passaggio al riempimento, interruzione|L'orologio viene avviato, interrotto, riempito.|  
|**CurrentTimeInvalidated**|Inizio, ricerca, passaggio al riempimento, interruzione|L'orologio avanza.|  
|**RemoveRequested**|Rimuovere||  
  
## <a name="ticking-and-event-consolidation"></a>Tick e consolidamento degli eventi  
 Quando si animano gli oggetti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è il motore di temporizzazione che gestisce le animazioni. Il motore di temporizzazione tiene traccia dell'avanzamento del tempo e calcola lo stato di ogni animazione. Esegue numerosi passaggi di valutazione in un secondo. Questi passaggi di valutazione sono noti come "tick".  
  
 Sebbene gli eventi tick siano piuttosto frequenti, è possibile che tra essi avvengano vari eventi. Una sequenza temporale può essere ad esempio interrotta, avviata e interrotta nuovamente, nel qual caso lo stato corrente verrà cambiato tre volte. In teoria l'evento può essere generato più volte in un singolo tick. Il motore di temporizzazione consolida tuttavia gli eventi in modo che ogni evento possa essere generato al massimo una volta per tick.  
  
## <a name="registering-for-events"></a>Registrazione per gli eventi  
 Esistono due modi per registrarsi per gli eventi di tempo: è possibile registrarsi con la sequenza temporale o con l'orologio creato dalla sequenza temporale. La registrazione per un evento direttamente con un orologio è piuttosto semplice, anche se può essere eseguita solo dal codice. È possibile registrarsi per gli eventi con una sequenza temporale dal codice o dal markup. La sezione successiva descrive come registrarsi per gli eventi di orologio con una sequenza temporale.  
  
<a name="registeringforclockeventswithatimeline"></a>
## <a name="registering-for-clock-events-with-a-timeline"></a>Registrazione per gli eventi di orologio con una sequenza temporale  
 Sebbene gli <xref:System.Windows.Media.Animation.Timeline.Completed>eventi <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated> <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> , e di una sequenza temporale sembrino essere associati alla <xref:System.Windows.Media.Animation.Clock> sequenza temporale, la registrazione per questi eventi associa effettivamente un gestore eventi all'oggetto creato per la sequenza temporale.  
  
 Quando ti registri <xref:System.Windows.Media.Animation.Timeline.Completed> per l'evento in una sequenza temporale, ad <xref:System.Windows.Media.Animation.Clock.Completed> esempio, stai effettivamente dicendo al sistema di registrarsi per l'evento di ogni orologio creato per la sequenza temporale. Nel codice, è necessario registrarsi <xref:System.Windows.Media.Animation.Clock> per questo evento prima che venga creato l'oggetto per questa sequenza temporale; in caso contrario, non riceverai una notifica. Questo avviene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]automaticamente in ; il parser si registra automaticamente <xref:System.Windows.Media.Animation.Clock> per l'evento prima della creazione dell'oggetto .  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sui comportamenti temporali](timing-behaviors-overview.md)
