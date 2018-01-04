---
title: "Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2c1d65ec9fad94fed02bee1f018ae1aa00a8591
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="efcc5-102">Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività</span><span class="sxs-lookup"><span data-stu-id="efcc5-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="efcc5-103">In questo esempio viene illustrato come specificare il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> per l'oggetto inattivo <xref:System.Windows.Media.Animation.Timeline> di una proprietà animata.</span><span class="sxs-lookup"><span data-stu-id="efcc5-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efcc5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="efcc5-104">Example</span></span>  
 <span data-ttu-id="efcc5-105">Il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> determina cosa accade per il valore di una proprietà animata quando non viene animata, vale a dire quando il <xref:System.Windows.Media.Animation.Timeline> è inattivo ma il relativo elemento padre <xref:System.Windows.Media.Animation.Timeline> si trova all'interno di attività o periodo di attesa.</span><span class="sxs-lookup"><span data-stu-id="efcc5-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="efcc5-106">Ad esempio, una proprietà animata rimane alla fine dopo l'animazione termina o se viene ripristinato il valore che aveva prima dell'inizio dell'animazione?</span><span class="sxs-lookup"><span data-stu-id="efcc5-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="efcc5-107">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.Animation.DoubleAnimation> per animare la <xref:System.Windows.FrameworkElement.Width%2A> di due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="efcc5-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="efcc5-108">Ogni rettangolo utilizza un altro <xref:System.Windows.Media.Animation.Timeline> oggetto.</span><span class="sxs-lookup"><span data-stu-id="efcc5-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="efcc5-109">Un <xref:System.Windows.Media.Animation.Timeline> ha un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> che è impostato su <xref:System.Windows.Media.Animation.FillBehavior.Stop>, che comporta la larghezza del rettangolo per tornare al relativo non animati valore quando il <xref:System.Windows.Media.Animation.Timeline> termina.</span><span class="sxs-lookup"><span data-stu-id="efcc5-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="efcc5-110">L'altro <xref:System.Windows.Media.Animation.Timeline> ha un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> di <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, che comporta la larghezza di rimanere al termine valore quando il <xref:System.Windows.Media.Animation.Timeline> termina.</span><span class="sxs-lookup"><span data-stu-id="efcc5-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="efcc5-111">Per l'esempio completo, vedere [raccolta](http://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="efcc5-111">For the complete sample, see [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efcc5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efcc5-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [<span data-ttu-id="efcc5-113">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="efcc5-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="efcc5-114">Animazione e temporizzazione</span><span class="sxs-lookup"><span data-stu-id="efcc5-114">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="efcc5-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="efcc5-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
