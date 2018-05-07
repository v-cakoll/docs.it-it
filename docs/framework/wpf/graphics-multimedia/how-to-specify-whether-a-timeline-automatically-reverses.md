---
title: 'Procedura: specificare se una sequenza temporale viene automaticamente invertita o meno'
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 498aefa16b8a76262c01965b8992ef9a94b7ce28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>Procedura: specificare se una sequenza temporale viene automaticamente invertita o meno
Una sequenza temporale <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà determina se viene riprodotto in senso inverso dopo il completamento di un'iterazione in avanti. L'esempio seguente illustra numerose animazioni con durata identica e valori di destinazione, ma con diversi <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> impostazioni. Per illustrare come <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> comportamento della proprietà con diversi <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , alcune animazioni vengono impostati da ripetere. Nell'ultima animazione viene come <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà funziona su sequenze temporali annidate.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
