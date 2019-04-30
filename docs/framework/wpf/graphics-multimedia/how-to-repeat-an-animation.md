---
title: "Procedura: Ripetere un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: a80f72b0e67c13890d4befcbd5ab7c4a92a93fe7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942090"
---
# <a name="how-to-repeat-an-animation"></a>Procedura: Ripetere un'animazione
Questo esempio illustra come usare il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> per controllare il comportamento di ripetizione di un'animazione.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> controlla il numero di volte un'animazione si ripete la propria durata semplice. Usando <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, è possibile specificare che un <xref:System.Windows.Media.Animation.Timeline> si ripete per un determinato numero di volte in cui (un conteggio di iterazione) o per un periodo di tempo specificato. In entrambi i casi, l'animazione esegue tante esecuzioni inizio-to-end necessari per riempire il conteggio richiesto o la durata.  
  
 Per impostazione predefinita, le sequenze temporali presentano un numero di ripetizioni pari a 1,0, che indica che essi svolgono una sola volta e non si ripetono. Tuttavia, se si imposta la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> a <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, la sequenza temporale viene ripetuta all'infinito.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà per controllare il comportamento di ripetizione di un'animazione. L'esempio anima il <xref:System.Windows.FrameworkElement.Width%2A> proprietà dei cinque rettangoli con ogni rettangolo utilizzando un diverso tipo di comportamento di ripetizione.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Per l'esempio completo, vedere [esempio di comportamento temporale di animazione](https://go.microsoft.com/fwlink/?LinkID=159970).  
  
## <a name="see-also"></a>Vedere anche

- [Accumulare valori di animazione durante i cicli ripetuti](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Specificare se una sequenza temporale viene invertita automaticamente](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [Animazione e temporizzazione procedure](animation-and-timing-how-to-topics.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Esempio di comportamento temporale di un'animazione](https://go.microsoft.com/fwlink/?LinkID=159970)
