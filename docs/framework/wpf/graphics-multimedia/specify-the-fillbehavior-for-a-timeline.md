---
title: 'Procedura: Specificare FillBehavior per un oggetto Timeline che ha raggiunto la fine del periodo di attività'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 9f03c5b8d4585c32e0a9f119649dd15a23523033
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091122"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Procedura: Specificare FillBehavior per un oggetto Timeline che ha raggiunto la fine del periodo di attività
In questo esempio viene illustrato come specificare il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> per l'oggetto inattivo <xref:System.Windows.Media.Animation.Timeline> di una proprietà animata.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> determina ciò che accade sul valore di una proprietà animata quando non viene animata, vale a dire quando la <xref:System.Windows.Media.Animation.Timeline> non è attivo ma il relativo elemento padre <xref:System.Windows.Media.Animation.Timeline> si trova all'interno di attività o periodo di attesa. Ad esempio, una proprietà animata resta comunque sul proprio lato dopo che l'animazione termina o se viene ripristinato il valore che aveva prima dell'inizio dell'animazione?  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.Animation.DoubleAnimation> animare il <xref:System.Windows.FrameworkElement.Width%2A> di due rettangoli. Ogni rettangolo viene utilizzato un diverso <xref:System.Windows.Media.Animation.Timeline> oggetto.  
  
 Uno <xref:System.Windows.Media.Animation.Timeline> ha un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> che è impostato su <xref:System.Windows.Media.Animation.FillBehavior.Stop>, in modo che la larghezza del rettangolo per tornare al relativo non-animati valore quando il <xref:System.Windows.Media.Animation.Timeline> termina. L'altra <xref:System.Windows.Media.Animation.Timeline> ha un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> dei <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, in modo che la larghezza deve rimanere sul proprio lato valore quando il <xref:System.Windows.Media.Animation.Timeline> termina.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Per l'esempio completo, vedere [raccolta di esempi di animazione](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Animazione e temporizzazione procedure](animation-and-timing-how-to-topics.md)
