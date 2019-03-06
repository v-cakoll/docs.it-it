---
title: "Procedura: Ricevere una notifica quando uno stato dell'orologio viene modificato"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
ms.openlocfilehash: dc3fffb88ce59ceb908d6febd2f078820513b641
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363137"
---
# <a name="how-to-receive-notification-when-a-clocks-state-changes"></a>Procedura: Ricevere una notifica quando uno stato dell'orologio viene modificato
Un orologio <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento si verifica quando il <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> diventa valido, ad esempio quando l'orologio viene avviato o interrotto. È possibile registrarsi per questo evento con direttamente tramite un <xref:System.Windows.Media.Animation.Clock>, oppure è possibile registrarsi con un <xref:System.Windows.Media.Animation.Timeline>.  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.Animation.Storyboard> e due <xref:System.Windows.Media.Animation.DoubleAnimation> oggetti vengono utilizzati per aggiungere un'animazione alla larghezza di due rettangoli. Il <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento viene utilizzato per l'ascolto delle modifiche dello stato dell'orologio.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 La figura seguente illustra i diversi stati le animazioni immettere come sequenza temporale padre (*Storyboard*) avanzamento.  
  
 ![Stati di clock per uno Storyboard con due animazioni](./media/graphicsmm-3timelines.png "graphicsmm_3timelines")  
  
 Nella tabella seguente vengono mostrati i tempi in cui *Animazione1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> viene generato l'evento:  
  
||||||||  
|-|-|-|-|-|-|-|  
|Tempo (secondi)|1|10|19|21|30|39|  
|Stato|Attivo|Attivo|Arrestato|Attivo|Attivo|Arrestato|  
  
 Nella tabella seguente vengono mostrati i tempi in cui *Animazione2*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> viene generato l'evento:  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Tempo (secondi)|1|9|11|19|21|29|31|39|  
|Stato|Attivo|La compilazione|Attivo|Arrestato|Attivo|La compilazione|Attivo|Arrestato|  
  
 Si noti che *Animazione1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento viene generato su 10 secondi, anche se lo stato rimane <xref:System.Windows.Media.Animation.ClockState.Active>. Perché il relativo stato modificato su 10 secondi, ma è stato modificato da <xref:System.Windows.Media.Animation.ClockState.Active> al <xref:System.Windows.Media.Animation.ClockState.Filling> e quindi nuovamente <xref:System.Windows.Media.Animation.ClockState.Active> nello stesso ciclo.
