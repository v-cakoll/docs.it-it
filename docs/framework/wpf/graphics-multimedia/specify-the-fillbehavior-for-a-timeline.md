---
title: 'Procedura: Specificare FillBehavior per un oggetto Timeline che ha raggiunto la fine del periodo di attività'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 9f03c5b8d4585c32e0a9f119649dd15a23523033
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973667"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="3db5d-102">Procedura: Specificare FillBehavior per un oggetto Timeline che ha raggiunto la fine del periodo di attività</span><span class="sxs-lookup"><span data-stu-id="3db5d-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="3db5d-103">In questo esempio viene illustrato come specificare il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> per l'oggetto inattivo <xref:System.Windows.Media.Animation.Timeline> di una proprietà animata.</span><span class="sxs-lookup"><span data-stu-id="3db5d-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3db5d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3db5d-104">Example</span></span>  
 <span data-ttu-id="3db5d-105">Il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> determina ciò che accade sul valore di una proprietà animata quando non viene animata, vale a dire quando la <xref:System.Windows.Media.Animation.Timeline> non è attivo ma il relativo elemento padre <xref:System.Windows.Media.Animation.Timeline> si trova all'interno di attività o periodo di attesa.</span><span class="sxs-lookup"><span data-stu-id="3db5d-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="3db5d-106">Ad esempio, una proprietà animata resta comunque sul proprio lato dopo che l'animazione termina o se viene ripristinato il valore che aveva prima dell'inizio dell'animazione?</span><span class="sxs-lookup"><span data-stu-id="3db5d-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="3db5d-107">L'esempio seguente usa un' <xref:System.Windows.Media.Animation.DoubleAnimation> animare il <xref:System.Windows.FrameworkElement.Width%2A> di due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="3db5d-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="3db5d-108">Ogni rettangolo viene utilizzato un diverso <xref:System.Windows.Media.Animation.Timeline> oggetto.</span><span class="sxs-lookup"><span data-stu-id="3db5d-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="3db5d-109">Uno <xref:System.Windows.Media.Animation.Timeline> ha un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> che è impostato su <xref:System.Windows.Media.Animation.FillBehavior.Stop>, in modo che la larghezza del rettangolo per tornare al relativo non-animati valore quando il <xref:System.Windows.Media.Animation.Timeline> termina.</span><span class="sxs-lookup"><span data-stu-id="3db5d-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="3db5d-110">L'altra <xref:System.Windows.Media.Animation.Timeline> ha un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> dei <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, in modo che la larghezza deve rimanere sul proprio lato valore quando il <xref:System.Windows.Media.Animation.Timeline> termina.</span><span class="sxs-lookup"><span data-stu-id="3db5d-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="3db5d-111">Per l'esempio completo, vedere [raccolta di esempi di animazione](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="3db5d-111">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db5d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3db5d-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="3db5d-113">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="3db5d-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3db5d-114">Animazione e temporizzazione procedure</span><span class="sxs-lookup"><span data-stu-id="3db5d-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
