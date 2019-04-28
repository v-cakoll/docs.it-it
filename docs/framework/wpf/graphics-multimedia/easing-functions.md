---
title: Funzioni di interpolazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: 456308e37bddc1df86b49085139a3810c4959a58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763104"
---
# <a name="easing-functions"></a><span data-ttu-id="db0c9-102">Funzioni di interpolazione</span><span class="sxs-lookup"><span data-stu-id="db0c9-102">Easing Functions</span></span>
<span data-ttu-id="db0c9-103">Le funzioni di interpolazione consentono di applicare formule matematiche personalizzate alle animazioni.</span><span class="sxs-lookup"><span data-stu-id="db0c9-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="db0c9-104">Si può ad esempio fare in modo che un oggetto rimbalzi in modo realistico o si comporti come se fosse su una molla.</span><span class="sxs-lookup"><span data-stu-id="db0c9-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="db0c9-105">È possibile usare animazioni con fotogrammi chiave o anche animazioni From/To/By per simulare questi effetti, ma l'operazione richiederebbe una quantità significativa di lavoro e l'animazione risulterebbe meno accurata rispetto all'uso di una formula matematica.</span><span class="sxs-lookup"><span data-stu-id="db0c9-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="db0c9-106">Oltre a creare una funzione di interpolazione personalizzata ereditando da <xref:System.Windows.Media.Animation.EasingFunctionBase>, è possibile usare una delle numerose funzioni di interpolazione fornite dal runtime per creare effetti di uso comune.</span><span class="sxs-lookup"><span data-stu-id="db0c9-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="db0c9-107"><xref:System.Windows.Media.Animation.BackEase>: Ritrae leggermente il movimento di un'animazione prima che inizi ad animarsi nel tracciato indicato.</span><span class="sxs-lookup"><span data-stu-id="db0c9-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="db0c9-108"><xref:System.Windows.Media.Animation.BounceEase>: Crea un effetto di rimbalzo.</span><span class="sxs-lookup"><span data-stu-id="db0c9-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="db0c9-109"><xref:System.Windows.Media.Animation.CircleEase>: Crea un'animazione che accelera e/o rallenta usando una funzione circolare.</span><span class="sxs-lookup"><span data-stu-id="db0c9-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="db0c9-110"><xref:System.Windows.Media.Animation.CubicEase>: Crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="db0c9-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="db0c9-111"><xref:System.Windows.Media.Animation.ElasticEase>: Crea un'animazione simile a una molla che oscilla avanti e indietro fino ad arrestarsi.</span><span class="sxs-lookup"><span data-stu-id="db0c9-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="db0c9-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Crea un'animazione che accelera e/o rallenta usando una formula esponenziale.</span><span class="sxs-lookup"><span data-stu-id="db0c9-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="db0c9-113"><xref:System.Windows.Media.Animation.PowerEase>: Crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>p</sup> dove p è uguale al <xref:System.Windows.Media.Animation.PowerEase.Power%2A>proprietà.</span><span class="sxs-lookup"><span data-stu-id="db0c9-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="db0c9-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="db0c9-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="db0c9-115"><xref:System.Windows.Media.Animation.QuarticEase>: Crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="db0c9-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="db0c9-116"><xref:System.Windows.Media.Animation.QuinticEase>: Creare un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="db0c9-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="db0c9-117"><xref:System.Windows.Media.Animation.SineEase>: Crea un'animazione che accelera e/o decelera usando una formula sinusoidale.</span><span class="sxs-lookup"><span data-stu-id="db0c9-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="db0c9-118">Per applicare una funzione di interpolazione a un'animazione, usare il `EasingFunction` proprietà dell'animazione specificare la funzione di interpolazione da applicare all'animazione.</span><span class="sxs-lookup"><span data-stu-id="db0c9-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="db0c9-119">L'esempio seguente applica un' <xref:System.Windows.Media.Animation.BounceEase> funzione di interpolazione un <xref:System.Windows.Media.Animation.DoubleAnimation> per creare un effetto di rimbalzo.</span><span class="sxs-lookup"><span data-stu-id="db0c9-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="db0c9-120">Nell'esempio precedente la funzione di interpolazione è applicata a un'animazione From/To/By.</span><span class="sxs-lookup"><span data-stu-id="db0c9-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="db0c9-121">Queste funzioni di interpolazione possono essere applicate anche ad animazioni con fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="db0c9-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="db0c9-122">L'esempio seguente illustra come usare i fotogrammi chiave con funzioni di interpolazione a essi associate per creare l'animazione di un rettangolo che si contrae verso l'alto, rallenta, poi si espande verso il basso (come se cadesse) e rimbalza fino ad arrestarsi.</span><span class="sxs-lookup"><span data-stu-id="db0c9-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="db0c9-123">È possibile usare il <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> proprietà per modificare l'interpolazione comportamento della funzione, vale a dire, modificare la modalità di interpolazione dell'animazione.</span><span class="sxs-lookup"><span data-stu-id="db0c9-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="db0c9-124">Esistono tre possibili valori è possibile concedere per <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="db0c9-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="db0c9-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: L'interpolazione segue la formula matematica associata alla funzione di interpolazione.</span><span class="sxs-lookup"><span data-stu-id="db0c9-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="db0c9-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: L'interpolazione segue l'interpolazione al 100% meno l'output della formula associata alla funzione di interpolazione.</span><span class="sxs-lookup"><span data-stu-id="db0c9-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="db0c9-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Usa l'interpolazione <xref:System.Windows.Media.Animation.EasingMode.EaseIn> nella prima metà dell'animazione e <xref:System.Windows.Media.Animation.EasingMode.EaseOut> per la seconda metà.</span><span class="sxs-lookup"><span data-stu-id="db0c9-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="db0c9-128">I grafici seguenti illustrano i diversi valori della <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> in cui *f*(*x*) rappresenta l'avanzamento dell'animazione e *t* rappresenta l'ora.</span><span class="sxs-lookup"><span data-stu-id="db0c9-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="db0c9-129">![Grafici di BackEase EasingMode.](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="db0c9-130">![Grafici di BounceEase EasingMode.](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="db0c9-131">![Grafici di CircleEase EasingMode.](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="db0c9-132">![Grafici di CubicEase EasingMode.](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="db0c9-133">![ElasticEase con grafici di EasingMode diversi.](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="db0c9-134">![Grafici ExponentialEase di EasingMode diversi.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="db0c9-135">![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="db0c9-136">![QuadraticEase con grafici di EasingMode diversi](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="db0c9-137">![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="db0c9-138">![QuinticEase con grafici di EasingMode diversi.](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="db0c9-139">![SineEase per valori di EasingMode diversi](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="db0c9-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db0c9-140">È possibile usare <xref:System.Windows.Media.Animation.PowerEase> per creare lo stesso comportamento <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, e <xref:System.Windows.Media.Animation.QuinticEase> usando la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="db0c9-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="db0c9-141">Ad esempio, se si desidera utilizzare <xref:System.Windows.Media.Animation.PowerEase> per sostituire <xref:System.Windows.Media.Animation.CubicEase>, specificare un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valore 3.</span><span class="sxs-lookup"><span data-stu-id="db0c9-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="db0c9-142">Oltre a usare le funzioni di interpolazione incluse in fase di esecuzione, è possibile creare funzioni di interpolazione personalizzate ereditando da <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span><span class="sxs-lookup"><span data-stu-id="db0c9-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="db0c9-143">L'esempio seguente illustra come creare una semplice funzione di interpolazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="db0c9-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="db0c9-144">È possibile aggiungere logica matematica personalizzata per determinare la funzione di interpolazione comportamento eseguendo l'override di <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="db0c9-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
