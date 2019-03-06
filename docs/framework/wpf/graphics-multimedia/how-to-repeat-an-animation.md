---
title: "Procedura: Ripetere un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: a098c912289f59f8be48edeec0f066b7f94b9fda
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354002"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="1b1f6-102">Procedura: Ripetere un'animazione</span><span class="sxs-lookup"><span data-stu-id="1b1f6-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="1b1f6-103">Questo esempio illustra come usare il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> per controllare il comportamento di ripetizione di un'animazione.</span><span class="sxs-lookup"><span data-stu-id="1b1f6-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b1f6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1b1f6-104">Example</span></span>  
 <span data-ttu-id="1b1f6-105">Il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> controlla il numero di volte un'animazione si ripete la propria durata semplice.</span><span class="sxs-lookup"><span data-stu-id="1b1f6-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="1b1f6-106">Usando <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, è possibile specificare che un <xref:System.Windows.Media.Animation.Timeline> si ripete per un determinato numero di volte in cui (un conteggio di iterazione) o per un periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="1b1f6-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="1b1f6-107">In entrambi i casi, l'animazione esegue tante esecuzioni inizio-to-end necessari per riempire il conteggio richiesto o la durata.</span><span class="sxs-lookup"><span data-stu-id="1b1f6-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="1b1f6-108">Per impostazione predefinita, le sequenze temporali presentano un numero di ripetizioni pari a 1,0, che indica che essi svolgono una sola volta e non si ripetono.</span><span class="sxs-lookup"><span data-stu-id="1b1f6-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="1b1f6-109">Tuttavia, se si imposta la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> a <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, la sequenza temporale viene ripetuta all'infinito.</span><span class="sxs-lookup"><span data-stu-id="1b1f6-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="1b1f6-110">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà per controllare il comportamento di ripetizione di un'animazione.</span><span class="sxs-lookup"><span data-stu-id="1b1f6-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="1b1f6-111">L'esempio anima il <xref:System.Windows.FrameworkElement.Width%2A> proprietà dei cinque rettangoli con ogni rettangolo utilizzando un diverso tipo di comportamento di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="1b1f6-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="1b1f6-112">Per l'esempio completo, vedere [esempio di comportamento temporale di animazione](https://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="1b1f6-112">For the complete sample, see [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1f6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b1f6-113">See also</span></span>
- [<span data-ttu-id="1b1f6-114">Accumulare valori di animazione durante i cicli ripetuti</span><span class="sxs-lookup"><span data-stu-id="1b1f6-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="1b1f6-115">Specificare se una sequenza temporale viene invertita automaticamente</span><span class="sxs-lookup"><span data-stu-id="1b1f6-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="1b1f6-116">Animazione e temporizzazione procedure</span><span class="sxs-lookup"><span data-stu-id="1b1f6-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="1b1f6-117">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="1b1f6-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="1b1f6-118">Esempio di comportamento temporale di un'animazione</span><span class="sxs-lookup"><span data-stu-id="1b1f6-118">Animation Timing Behavior Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159970)
