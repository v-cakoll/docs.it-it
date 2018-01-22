---
title: "Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b890d121cf06dc377a3bbc1dc569d9dac7c011b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività
In questo esempio viene illustrato come specificare il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> per l'oggetto inattivo <xref:System.Windows.Media.Animation.Timeline> di una proprietà animata.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> determina cosa accade per il valore di una proprietà animata quando non viene animata, vale a dire quando il <xref:System.Windows.Media.Animation.Timeline> è inattivo ma il relativo elemento padre <xref:System.Windows.Media.Animation.Timeline> si trova all'interno di attività o periodo di attesa. Ad esempio, una proprietà animata rimane alla fine dopo l'animazione termina o se viene ripristinato il valore che aveva prima dell'inizio dell'animazione?  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.Animation.DoubleAnimation> per animare la <xref:System.Windows.FrameworkElement.Width%2A> di due rettangoli. Ogni rettangolo utilizza un altro <xref:System.Windows.Media.Animation.Timeline> oggetto.  
  
 Un <xref:System.Windows.Media.Animation.Timeline> ha un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> che è impostato su <xref:System.Windows.Media.Animation.FillBehavior.Stop>, che comporta la larghezza del rettangolo per tornare al relativo non animati valore quando il <xref:System.Windows.Media.Animation.Timeline> termina. L'altro <xref:System.Windows.Media.Animation.Timeline> ha un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> di <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, che comporta la larghezza di rimanere al termine valore quando il <xref:System.Windows.Media.Animation.Timeline> termina.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Per l'esempio completo, vedere [raccolta](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Animazione e temporizzazione](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
