---
title: 'Procedura: ricevere una notifica quando un orario in formato&#39;s modifiche stato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
ms.openlocfilehash: d0eaca4d2a05d01e686efc15dfceebb6de4f4b64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a>Procedura: ricevere una notifica quando un orario in formato&#39;s modifiche stato
Un clock <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento si verifica quando il relativo <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> diventa valido, ad esempio quando l'orologio avvia o arresta. È possibile registrare questo evento utilizzando direttamente un <xref:System.Windows.Media.Animation.Clock>, o eseguire la registrazione tramite un <xref:System.Windows.Media.Animation.Timeline>.  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.Animation.Storyboard> e due <xref:System.Windows.Media.Animation.DoubleAnimation> gli oggetti vengono utilizzati per animare la larghezza di due rettangoli. Il <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento viene utilizzato per l'ascolto dei cambiamenti di stato dell'orologio.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 La figura seguente mostra i diversi stati le animazioni immettere come la sequenza temporale padre (*Storyboard*) l'avanzamento.  
  
 ![Stati di clock per uno Storyboard con due animazioni](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")  
  
 Nella tabella seguente vengono mostrati i momenti in cui *Animazione1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> viene generato l'evento:  
  
||||||||  
|-|-|-|-|-|-|-|  
|Tempo (secondi)|1|10|19|21|30|39|  
|Stato|Attivo|Attivo|Arrestato|Attivo|Attivo|Arrestato|  
  
 Nella tabella seguente vengono mostrati i momenti in cui *Animazione2*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> viene generato l'evento:  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Tempo (secondi)|1|9|11|19|21|29|31|39|  
|Stato|Attivo|La compilazione|Attivo|Arrestato|Attivo|La compilazione|Attivo|Arrestato|  
  
 Si noti che *Animazione1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento viene generato a 10 secondi, anche se il relativo stato rimane <xref:System.Windows.Media.Animation.ClockState.Active>. Ciò accade perché lo stato è cambiato a 10 secondi, ma è stato modificato da <xref:System.Windows.Media.Animation.ClockState.Active> a <xref:System.Windows.Media.Animation.ClockState.Filling> e quindi nuovamente <xref:System.Windows.Media.Animation.ClockState.Active> nello stesso ciclo.
