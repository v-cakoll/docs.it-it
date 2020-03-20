---
title: 'Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141173"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività
In questo esempio viene <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> illustrato come <xref:System.Windows.Media.Animation.Timeline> specificare l'oggetto per l'inattività di una proprietà animata.  
  
## <a name="example"></a>Esempio  
 La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà <xref:System.Windows.Media.Animation.Timeline> di un oggetto determina cosa accade al valore di una proprietà <xref:System.Windows.Media.Animation.Timeline> animata quando <xref:System.Windows.Media.Animation.Timeline> non viene animata, ovvero quando l'oggetto è inattivo ma l'elemento padre si trova all'interno del periodo attivo o di attesa. Ad esempio, una proprietà animata rimane al valore finale dopo la fine dell'animazione o ripristina il valore che aveva prima dell'inizio dell'animazione?  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation> viene <xref:System.Windows.FrameworkElement.Width%2A> utilizzato un per animare il di due rettangoli. Ogni rettangolo <xref:System.Windows.Media.Animation.Timeline> utilizza un oggetto diverso.  
  
 Uno <xref:System.Windows.Media.Animation.Timeline> ha <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> un oggetto <xref:System.Windows.Media.Animation.FillBehavior.Stop>che è impostato su , che fa sì che <xref:System.Windows.Media.Animation.Timeline> la larghezza del rettangolo per tornare al suo valore non animato quando termina. <xref:System.Windows.Media.Animation.Timeline> L'altro <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> ha <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>un di , che fa sì <xref:System.Windows.Media.Animation.Timeline> che la larghezza rimanga al suo valore finale quando termina.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Per l'esempio completo, vedere Raccolta di esempi di [animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
