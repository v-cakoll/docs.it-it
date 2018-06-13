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
ms.locfileid: "33560065"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="f847b-102">Procedura: specificare se una sequenza temporale viene automaticamente invertita o meno</span><span class="sxs-lookup"><span data-stu-id="f847b-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="f847b-103">Una sequenza temporale <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà determina se viene riprodotto in senso inverso dopo il completamento di un'iterazione in avanti.</span><span class="sxs-lookup"><span data-stu-id="f847b-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="f847b-104">L'esempio seguente illustra numerose animazioni con durata identica e valori di destinazione, ma con diversi <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f847b-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="f847b-105">Per illustrare come <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> comportamento della proprietà con diversi <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , alcune animazioni vengono impostati da ripetere.</span><span class="sxs-lookup"><span data-stu-id="f847b-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="f847b-106">Nell'ultima animazione viene come <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà funziona su sequenze temporali annidate.</span><span class="sxs-lookup"><span data-stu-id="f847b-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f847b-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="f847b-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
