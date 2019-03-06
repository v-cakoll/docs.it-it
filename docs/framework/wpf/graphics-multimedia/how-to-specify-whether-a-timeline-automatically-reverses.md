---
title: 'Procedura: Specificare se una sequenza temporale viene invertita automaticamente'
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354206"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="e1376-102">Procedura: Specificare se una sequenza temporale viene invertita automaticamente</span><span class="sxs-lookup"><span data-stu-id="e1376-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="e1376-103">Una sequenza temporale <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà determina se viene riprodotto in senso inverso dopo il completamento di un'iterazione in avanti.</span><span class="sxs-lookup"><span data-stu-id="e1376-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="e1376-104">L'esempio seguente illustra numerose animazioni con durata identica e valori di destinazione, ma con diverse <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e1376-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="e1376-105">Per illustrare come le <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> comportamento della proprietà con diversi <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , alcune animazioni sono impostati in modo da ripetere.</span><span class="sxs-lookup"><span data-stu-id="e1376-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="e1376-106">Nell'ultima animazione di seguito viene illustrato come il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà funziona su sequenze temporali annidate.</span><span class="sxs-lookup"><span data-stu-id="e1376-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1376-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1376-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
