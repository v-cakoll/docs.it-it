---
title: "Procedura: ripetere un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141549"
---
# <a name="how-to-repeat-an-animation"></a>Procedura: ripetere un'animazione
In questo esempio viene <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> illustrato <xref:System.Windows.Media.Animation.Timeline> come utilizzare la proprietà di un oggetto per controllare il comportamento di ripetizione di un'animazione.  
  
## <a name="example"></a>Esempio  
 La <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà <xref:System.Windows.Media.Animation.Timeline> di un controllo controlla quante volte un'animazione ripete la durata semplice. Utilizzando <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, è possibile <xref:System.Windows.Media.Animation.Timeline> specificare che un oggetto si ripeta per un determinato numero di volte (conteggio delle iterazioni) o per un periodo di tempo specificato. In entrambi i casi, l'animazione attraversa tutte le esecuzioni dall'inizio alla fine necessarie per riempire il conteggio o la durata richiesta.  
  
 Per impostazione predefinita, le sequenze temporali hanno un numero di ripetizioni pari a 1,0, il che significa che vengono riprodotte una sola volta e non vengono ripetute. Tuttavia, se <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> si imposta <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>la proprietà di a su , la sequenza temporale viene ripetuta per un tempo indefinito.  
  
 Nell'esempio seguente viene <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> illustrato come utilizzare la proprietà per controllare il comportamento di ripetizione di un'animazione. L'esempio anima <xref:System.Windows.FrameworkElement.Width%2A> la proprietà di cinque rettangoli con ogni rettangolo utilizzando un diverso tipo di comportamento di ripetizione.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Per l'esempio completo, consultate Esempio di [comportamento di temporizzazione animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).  
  
## <a name="see-also"></a>Vedere anche

- [Accumulare valori di animazione durante i cicli ripetuti](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Specificare se una sequenza temporale viene invertita automaticamente](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Esempio di comportamento temporale di un'animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
