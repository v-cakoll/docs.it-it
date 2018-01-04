---
title: 'Procedura: semplificare le animazioni utilizzando oggetti Timeline figlio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d3b8f1ca1dbf7ba5452acffc62fdf0b655c9c12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>Procedura: semplificare le animazioni utilizzando oggetti Timeline figlio
In questo esempio viene illustrato come semplificare le animazioni utilizzando figlio <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti. Oggetto <xref:System.Windows.Media.Animation.Storyboard> è un tipo di <xref:System.Windows.Media.Animation.Timeline> che fornisce informazioni per le sequenze in essa contenute. Utilizzare un <xref:System.Windows.Media.Animation.Storyboard> per fornire informazioni, incluse le informazioni oggetto e proprietà di destinazione degli oggetti timeline.  
  
 Per avviare un'animazione, utilizzare uno o più <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti come elementi figlio annidati di un <xref:System.Windows.Media.Animation.Storyboard>. Questi <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti possono contenere altre animazioni e pertanto può incapsulare meglio le sequenze temporali di animazioni complesse. Ad esempio, se sta aggiungendo un'animazione un <xref:System.Windows.Controls.TextBlock> e diverse forme nella stessa <xref:System.Windows.Media.Animation.Storyboard>, è possibile separare le animazioni per il <xref:System.Windows.Controls.TextBlock> e forme, inserendole ognuna in un apposito <xref:System.Windows.Media.Animation.ParallelTimeline>. Poiché ogni <xref:System.Windows.Media.Animation.ParallelTimeline> dispone di una propria <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> e tutti gli elementi figlio del <xref:System.Windows.Media.Animation.ParallelTimeline> iniziano in base a questo <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, intervallo incapsulata in modo migliore.  
  
 Nell'esempio seguente aggiunge un'animazione due parti di testo (<xref:System.Windows.Controls.TextBlock> oggetti) all'interno dello stesso <xref:System.Windows.Media.Animation.Storyboard>. Oggetto <xref:System.Windows.Media.Animation.ParallelTimeline> incapsula le animazioni di uno del <xref:System.Windows.Controls.TextBlock> oggetti.  
  
 **Nota sulle prestazioni:** anche se è possibile annidare <xref:System.Windows.Media.Animation.Storyboard> sequenze temporali all'interno di altri, <xref:System.Windows.Media.Animation.ParallelTimeline>sono più adatti per la nidificazione perché richiedono meno overhead. (Il <xref:System.Windows.Media.Animation.Storyboard> classe eredita la <xref:System.Windows.Media.Animation.ParallelTimeline> classe.)  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Specificare HandoffBehavior tra le animazioni storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
