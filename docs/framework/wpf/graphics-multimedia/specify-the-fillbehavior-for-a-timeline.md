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
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="60a03-102">Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività</span><span class="sxs-lookup"><span data-stu-id="60a03-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="60a03-103">In questo esempio viene <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> illustrato come <xref:System.Windows.Media.Animation.Timeline> specificare l'oggetto per l'inattività di una proprietà animata.</span><span class="sxs-lookup"><span data-stu-id="60a03-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60a03-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="60a03-104">Example</span></span>  
 <span data-ttu-id="60a03-105">La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà <xref:System.Windows.Media.Animation.Timeline> di un oggetto determina cosa accade al valore di una proprietà <xref:System.Windows.Media.Animation.Timeline> animata quando <xref:System.Windows.Media.Animation.Timeline> non viene animata, ovvero quando l'oggetto è inattivo ma l'elemento padre si trova all'interno del periodo attivo o di attesa.</span><span class="sxs-lookup"><span data-stu-id="60a03-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="60a03-106">Ad esempio, una proprietà animata rimane al valore finale dopo la fine dell'animazione o ripristina il valore che aveva prima dell'inizio dell'animazione?</span><span class="sxs-lookup"><span data-stu-id="60a03-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="60a03-107">Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation> viene <xref:System.Windows.FrameworkElement.Width%2A> utilizzato un per animare il di due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="60a03-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="60a03-108">Ogni rettangolo <xref:System.Windows.Media.Animation.Timeline> utilizza un oggetto diverso.</span><span class="sxs-lookup"><span data-stu-id="60a03-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="60a03-109">Uno <xref:System.Windows.Media.Animation.Timeline> ha <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> un oggetto <xref:System.Windows.Media.Animation.FillBehavior.Stop>che è impostato su , che fa sì che <xref:System.Windows.Media.Animation.Timeline> la larghezza del rettangolo per tornare al suo valore non animato quando termina.</span><span class="sxs-lookup"><span data-stu-id="60a03-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="60a03-110"><xref:System.Windows.Media.Animation.Timeline> L'altro <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> ha <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>un di , che fa sì <xref:System.Windows.Media.Animation.Timeline> che la larghezza rimanga al suo valore finale quando termina.</span><span class="sxs-lookup"><span data-stu-id="60a03-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="60a03-111">Per l'esempio completo, vedere Raccolta di esempi di [animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="60a03-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a03-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60a03-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="60a03-113">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="60a03-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="60a03-114">Procedure relative all'animazione e al sistema di temporizzazione</span><span class="sxs-lookup"><span data-stu-id="60a03-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
