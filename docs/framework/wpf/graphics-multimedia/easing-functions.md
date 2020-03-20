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
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186491"
---
# <a name="easing-functions"></a><span data-ttu-id="43155-102">Funzioni di interpolazione</span><span class="sxs-lookup"><span data-stu-id="43155-102">Easing Functions</span></span>
<span data-ttu-id="43155-103">Le funzioni di interpolazione consentono di applicare formule matematiche personalizzate alle animazioni.</span><span class="sxs-lookup"><span data-stu-id="43155-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="43155-104">Si può ad esempio fare in modo che un oggetto rimbalzi in modo realistico o si comporti come se fosse su una molla.</span><span class="sxs-lookup"><span data-stu-id="43155-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="43155-105">È possibile usare animazioni con fotogrammi chiave o anche animazioni From/To/By per simulare questi effetti, ma l'operazione richiederebbe una quantità significativa di lavoro e l'animazione risulterebbe meno accurata rispetto all'uso di una formula matematica.</span><span class="sxs-lookup"><span data-stu-id="43155-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="43155-106">Oltre a creare una funzione di andamento <xref:System.Windows.Media.Animation.EasingFunctionBase>personalizzata ereditando da , è possibile utilizzare una delle diverse funzioni di andamento fornite dal runtime per creare effetti comuni.</span><span class="sxs-lookup"><span data-stu-id="43155-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="43155-107"><xref:System.Windows.Media.Animation.BackEase>: ritrae leggermente il movimento di un'animazione prima che inizi ad animarsi nel tracciato indicato.</span><span class="sxs-lookup"><span data-stu-id="43155-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="43155-108"><xref:System.Windows.Media.Animation.BounceEase>: crea un effetto di rimbalzo.</span><span class="sxs-lookup"><span data-stu-id="43155-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="43155-109"><xref:System.Windows.Media.Animation.CircleEase>: crea un'animazione che accelera e/o decelera utilizzando una funzione circolare.</span><span class="sxs-lookup"><span data-stu-id="43155-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="43155-110"><xref:System.Windows.Media.Animation.CubicEase>: crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) : *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="43155-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="43155-111"><xref:System.Windows.Media.Animation.ElasticEase>: crea un'animazione che assomiglia a una molla che oscilla avanti e indietro fino a quando non si ferma.</span><span class="sxs-lookup"><span data-stu-id="43155-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="43155-112"><xref:System.Windows.Media.Animation.ExponentialEase>: crea un'animazione che accelera e/o decelera utilizzando una formula esponenziale.</span><span class="sxs-lookup"><span data-stu-id="43155-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="43155-113"><xref:System.Windows.Media.Animation.PowerEase>: crea un'animazione che accelera e/o decelera utilizzando la formula <xref:System.Windows.Media.Animation.PowerEase.Power%2A> *f*(*t*) - *t*<sup>p</sup> dove p è uguale alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="43155-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="43155-114"><xref:System.Windows.Media.Animation.QuadraticEase>: crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) : *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="43155-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="43155-115"><xref:System.Windows.Media.Animation.QuarticEase>: crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) : *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="43155-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="43155-116"><xref:System.Windows.Media.Animation.QuinticEase>: consente di creare un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) : *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="43155-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="43155-117"><xref:System.Windows.Media.Animation.SineEase>: crea un'animazione che accelera e/o decelera utilizzando una formula sinusoidale.</span><span class="sxs-lookup"><span data-stu-id="43155-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="43155-118">Per applicare una funzione di andamento `EasingFunction` a un'animazione, utilizzare la proprietà dell'animazione specificare la funzione di andamento da applicare all'animazione.</span><span class="sxs-lookup"><span data-stu-id="43155-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="43155-119">Nell'esempio seguente <xref:System.Windows.Media.Animation.BounceEase> viene applicata <xref:System.Windows.Media.Animation.DoubleAnimation> una funzione di andamento a un oggetto per creare un effetto di rimbalzo.</span><span class="sxs-lookup"><span data-stu-id="43155-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="43155-120">Nell'esempio precedente la funzione di interpolazione è applicata a un'animazione From/To/By.</span><span class="sxs-lookup"><span data-stu-id="43155-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="43155-121">Queste funzioni di interpolazione possono essere applicate anche ad animazioni con fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="43155-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="43155-122">L'esempio seguente illustra come usare i fotogrammi chiave con funzioni di interpolazione a essi associate per creare l'animazione di un rettangolo che si contrae verso l'alto, rallenta, poi si espande verso il basso (come se cadesse) e rimbalza fino ad arrestarsi.</span><span class="sxs-lookup"><span data-stu-id="43155-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="43155-123">È possibile <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> utilizzare la proprietà per modificare il modo in cui si comporta la funzione di interpolazione, ovvero modificare la modalità di interpolazione dell'animazione.</span><span class="sxs-lookup"><span data-stu-id="43155-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="43155-124">Ci sono tre possibili valori <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>che puoi dare per:</span><span class="sxs-lookup"><span data-stu-id="43155-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="43155-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: l'interpolazione segue la formula matematica associata alla funzione di interpolazione.</span><span class="sxs-lookup"><span data-stu-id="43155-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="43155-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: l'interpolazione segue l'interpolazione al 100% meno l'output della formula associata alla funzione di interpolazione.</span><span class="sxs-lookup"><span data-stu-id="43155-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="43155-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: l'interpolazione viene utilizzata <xref:System.Windows.Media.Animation.EasingMode.EaseIn> per <xref:System.Windows.Media.Animation.EasingMode.EaseOut> la prima metà dell'animazione e per la seconda metà.</span><span class="sxs-lookup"><span data-stu-id="43155-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="43155-128">I grafici seguenti illustrano <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> i diversi valori di dove *f*(*x*) rappresenta lo stato di avanzamento dell'animazione e *t* rappresenta il tempo.</span><span class="sxs-lookup"><span data-stu-id="43155-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="43155-129">![Grafici di EasingMode per BackEase.](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="43155-130">![Grafici di EasingMode per BounceEase.](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="43155-131">![Grafici di EasingMode per CircleEase.](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="43155-132">![Grafici di EasingMode per CubicEase.](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="43155-133">![ElasticEase con grafici di EasingMode diversi.](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="43155-134">![Grafici di ExponentialEase con EasingMode diversi.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="43155-135">![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="43155-136">![QuadraticEase con grafici di diversi asinisti](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="43155-137">![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="43155-138">![QuinticEase con grafici di EasingMode diversi.](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="43155-139">![SineEase per valori EasingMode diversi](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="43155-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43155-140">È possibile <xref:System.Windows.Media.Animation.PowerEase> utilizzare per creare <xref:System.Windows.Media.Animation.CubicEase> <xref:System.Windows.Media.Animation.QuadraticEase>lo <xref:System.Windows.Media.Animation.QuarticEase>stesso <xref:System.Windows.Media.Animation.QuinticEase> comportamento <xref:System.Windows.Media.Animation.PowerEase.Power%2A> di , , e utilizzando la proprietà .</span><span class="sxs-lookup"><span data-stu-id="43155-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="43155-141">Ad esempio, se si <xref:System.Windows.Media.Animation.PowerEase> desidera <xref:System.Windows.Media.Animation.CubicEase>utilizzare per <xref:System.Windows.Media.Animation.PowerEase.Power%2A> sostituire , specificare un valore pari a 3.</span><span class="sxs-lookup"><span data-stu-id="43155-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="43155-142">Oltre a utilizzare le funzioni di andamento incluse in fase di esecuzione, è possibile <xref:System.Windows.Media.Animation.EasingFunctionBase>creare funzioni di andamento personalizzate ereditando da .</span><span class="sxs-lookup"><span data-stu-id="43155-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="43155-143">L'esempio seguente illustra come creare una semplice funzione di interpolazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="43155-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="43155-144">È possibile aggiungere la propria logica matematica per il modo in <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> cui si comporta la funzione di andamento eseguendo l'override del metodo.</span><span class="sxs-lookup"><span data-stu-id="43155-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
