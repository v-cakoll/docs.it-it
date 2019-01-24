---
title: "Procedura: Ripetere un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 213fca0796840ae87035be4f474cfdf4648460a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609642"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="57256-102">Procedura: Ripetere un'animazione</span><span class="sxs-lookup"><span data-stu-id="57256-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="57256-103">Questo esempio illustra come usare il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> per controllare il comportamento di ripetizione di un'animazione.</span><span class="sxs-lookup"><span data-stu-id="57256-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57256-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="57256-104">Example</span></span>  
 <span data-ttu-id="57256-105">Il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> controlla il numero di volte un'animazione si ripete la propria durata semplice.</span><span class="sxs-lookup"><span data-stu-id="57256-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="57256-106">Usando <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, è possibile specificare che un <xref:System.Windows.Media.Animation.Timeline> si ripete per un determinato numero di volte in cui (un conteggio di iterazione) o per un periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="57256-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="57256-107">In entrambi i casi, l'animazione esegue tante esecuzioni inizio-to-end necessari per riempire il conteggio richiesto o la durata.</span><span class="sxs-lookup"><span data-stu-id="57256-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="57256-108">Per impostazione predefinita, le sequenze temporali presentano un numero di ripetizioni pari a 1,0, che indica che essi svolgono una sola volta e non si ripetono.</span><span class="sxs-lookup"><span data-stu-id="57256-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="57256-109">Tuttavia, se si imposta la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> a <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, la sequenza temporale viene ripetuta all'infinito.</span><span class="sxs-lookup"><span data-stu-id="57256-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="57256-110">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà per controllare il comportamento di ripetizione di un'animazione.</span><span class="sxs-lookup"><span data-stu-id="57256-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="57256-111">L'esempio anima il <xref:System.Windows.FrameworkElement.Width%2A> proprietà dei cinque rettangoli con ogni rettangolo utilizzando un diverso tipo di comportamento di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="57256-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="57256-112">Per l'esempio completo, vedere [esempio di comportamento temporale di animazione](https://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="57256-112">For the complete sample, see [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57256-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57256-113">See also</span></span>
- [<span data-ttu-id="57256-114">Accumulare valori di animazione durante i cicli ripetuti</span><span class="sxs-lookup"><span data-stu-id="57256-114">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="57256-115">Specificare se una sequenza temporale viene invertita automaticamente</span><span class="sxs-lookup"><span data-stu-id="57256-115">Specify Whether a Timeline Automatically Reverses</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="57256-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="57256-116">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="57256-117">Animazione e temporizzazione</span><span class="sxs-lookup"><span data-stu-id="57256-117">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [<span data-ttu-id="57256-118">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="57256-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="57256-119">Esempio di comportamento temporale di un'animazione</span><span class="sxs-lookup"><span data-stu-id="57256-119">Animation Timing Behavior Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159970)
