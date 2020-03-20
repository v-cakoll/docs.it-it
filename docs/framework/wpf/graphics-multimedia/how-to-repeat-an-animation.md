---
title: "Procedura: ripetere un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141549"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="73f12-102">Procedura: ripetere un'animazione</span><span class="sxs-lookup"><span data-stu-id="73f12-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="73f12-103">In questo esempio viene <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> illustrato <xref:System.Windows.Media.Animation.Timeline> come utilizzare la proprietà di un oggetto per controllare il comportamento di ripetizione di un'animazione.</span><span class="sxs-lookup"><span data-stu-id="73f12-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73f12-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="73f12-104">Example</span></span>  
 <span data-ttu-id="73f12-105">La <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà <xref:System.Windows.Media.Animation.Timeline> di un controllo controlla quante volte un'animazione ripete la durata semplice.</span><span class="sxs-lookup"><span data-stu-id="73f12-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="73f12-106">Utilizzando <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, è possibile <xref:System.Windows.Media.Animation.Timeline> specificare che un oggetto si ripeta per un determinato numero di volte (conteggio delle iterazioni) o per un periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="73f12-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="73f12-107">In entrambi i casi, l'animazione attraversa tutte le esecuzioni dall'inizio alla fine necessarie per riempire il conteggio o la durata richiesta.</span><span class="sxs-lookup"><span data-stu-id="73f12-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="73f12-108">Per impostazione predefinita, le sequenze temporali hanno un numero di ripetizioni pari a 1,0, il che significa che vengono riprodotte una sola volta e non vengono ripetute.</span><span class="sxs-lookup"><span data-stu-id="73f12-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="73f12-109">Tuttavia, se <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> si imposta <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>la proprietà di a su , la sequenza temporale viene ripetuta per un tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="73f12-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="73f12-110">Nell'esempio seguente viene <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> illustrato come utilizzare la proprietà per controllare il comportamento di ripetizione di un'animazione.</span><span class="sxs-lookup"><span data-stu-id="73f12-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="73f12-111">L'esempio anima <xref:System.Windows.FrameworkElement.Width%2A> la proprietà di cinque rettangoli con ogni rettangolo utilizzando un diverso tipo di comportamento di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="73f12-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="73f12-112">Per l'esempio completo, consultate Esempio di [comportamento di temporizzazione animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span><span class="sxs-lookup"><span data-stu-id="73f12-112">For the complete sample, see [Animation Timing Behavior Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f12-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73f12-113">See also</span></span>

- [<span data-ttu-id="73f12-114">Accumulare valori di animazione durante i cicli ripetuti</span><span class="sxs-lookup"><span data-stu-id="73f12-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="73f12-115">Specificare se una sequenza temporale viene invertita automaticamente</span><span class="sxs-lookup"><span data-stu-id="73f12-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="73f12-116">Procedure relative all'animazione e al sistema di temporizzazione</span><span class="sxs-lookup"><span data-stu-id="73f12-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="73f12-117">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="73f12-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="73f12-118">Esempio di comportamento temporale di un'animazione</span><span class="sxs-lookup"><span data-stu-id="73f12-118">Animation Timing Behavior Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
