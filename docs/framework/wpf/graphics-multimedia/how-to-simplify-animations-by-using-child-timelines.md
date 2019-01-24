---
title: 'Procedura: Semplificare le animazioni utilizzando oggetti Timeline figlio'
ms.date: 03/30/2017
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
ms.openlocfilehash: b5af20ce791c442eada0774cd46f52205e5b93e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648193"
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>Procedura: Semplificare le animazioni utilizzando oggetti Timeline figlio
Questo esempio illustra come semplificare le animazioni usando figlio <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti. Oggetto <xref:System.Windows.Media.Animation.Storyboard> è un tipo di <xref:System.Windows.Media.Animation.Timeline> che fornisce informazioni di destinazione per le sequenze temporali in esso contenuti. Usare un <xref:System.Windows.Media.Animation.Storyboard> per fornire informazioni, comprese quelle di oggetti e proprietà di destinazione degli oggetti timeline.  
  
 Per iniziare un'animazione, usare uno o più <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti come elementi figlio annidati di una <xref:System.Windows.Media.Animation.Storyboard>. Questi <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti possono contenere altre animazioni e pertanto possono incapsulare meglio le sequenze temporali in animazioni complesse. Ad esempio, se si animano un <xref:System.Windows.Controls.TextBlock> e diverse forme nella stessa <xref:System.Windows.Media.Animation.Storyboard>, è possibile separare le animazioni per il <xref:System.Windows.Controls.TextBlock> e le forme, inserendo ogni elemento in un oggetto separato <xref:System.Windows.Media.Animation.ParallelTimeline>. Poiché ogni <xref:System.Windows.Media.Animation.ParallelTimeline> ha il proprio <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> e tutti gli elementi figlio delle <xref:System.Windows.Media.Animation.ParallelTimeline> inizio rispetto a ciò <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, viene migliorato l'incapsulamento.  
  
 L'esempio seguente anima due parti di testo (<xref:System.Windows.Controls.TextBlock> oggetti) all'interno della stessa <xref:System.Windows.Media.Animation.Storyboard>. Oggetto <xref:System.Windows.Media.Animation.ParallelTimeline> incapsula le animazioni di uno del <xref:System.Windows.Controls.TextBlock> oggetti.  
  
 **Nota sulle prestazioni:** Sebbene sia possibile annidare <xref:System.Windows.Media.Animation.Storyboard> sequenze temporali all'interno di altre, <xref:System.Windows.Media.Animation.ParallelTimeline>sono più adatti per l'annidamento, poiché richiedono un sovraccarico inferiore. (Il <xref:System.Windows.Media.Animation.Storyboard> classe eredita dal <xref:System.Windows.Media.Animation.ParallelTimeline> classe.)  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Specificare HandoffBehavior tra le animazioni storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
