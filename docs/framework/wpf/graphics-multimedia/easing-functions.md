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
ms.openlocfilehash: 3ce7c1824dc53c154ba1091ea62c1b8950b757c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557563"
---
# <a name="easing-functions"></a><span data-ttu-id="1767e-102">Funzioni di interpolazione</span><span class="sxs-lookup"><span data-stu-id="1767e-102">Easing Functions</span></span>
<span data-ttu-id="1767e-103">Le funzioni di interpolazione consentono di applicare formule matematiche personalizzate alle animazioni.</span><span class="sxs-lookup"><span data-stu-id="1767e-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="1767e-104">Si può ad esempio fare in modo che un oggetto rimbalzi in modo realistico o si comporti come se fosse su una molla.</span><span class="sxs-lookup"><span data-stu-id="1767e-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="1767e-105">È possibile usare animazioni con fotogrammi chiave o anche animazioni From/To/By per simulare questi effetti, ma l'operazione richiederebbe una quantità significativa di lavoro e l'animazione risulterebbe meno accurata rispetto all'uso di una formula matematica.</span><span class="sxs-lookup"><span data-stu-id="1767e-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="1767e-106">Oltre a creare la propria funzione di interpolazione personalizzata tramite l'eredità da <xref:System.Windows.Media.Animation.EasingFunctionBase>, è possibile utilizzare una delle numerose funzioni di interpolazione fornite dal runtime per creare effetti comuni.</span><span class="sxs-lookup"><span data-stu-id="1767e-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
-   <span data-ttu-id="1767e-107"><xref:System.Windows.Media.Animation.BackEase>: Ritira il movimento di un'animazione leggermente prima di iniziare un'animazione nel percorso indicato.</span><span class="sxs-lookup"><span data-stu-id="1767e-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
-   <span data-ttu-id="1767e-108"><xref:System.Windows.Media.Animation.BounceEase>: Crea un effetto di rimbalzo.</span><span class="sxs-lookup"><span data-stu-id="1767e-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
-   <span data-ttu-id="1767e-109"><xref:System.Windows.Media.Animation.CircleEase>: Consente di creare un'animazione che accelera e/o decelera, usando una funzione circolare.</span><span class="sxs-lookup"><span data-stu-id="1767e-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
-   <span data-ttu-id="1767e-110"><xref:System.Windows.Media.Animation.CubicEase>: Crea un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="1767e-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
-   <span data-ttu-id="1767e-111"><xref:System.Windows.Media.Animation.ElasticEase>: Consente di creare un'animazione che è simile a una molla oscilla avanti e indietro fino ad arrestarsi.</span><span class="sxs-lookup"><span data-stu-id="1767e-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
-   <span data-ttu-id="1767e-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Consente di creare un'animazione che accelera e/o decelera, usando una formula esponenziale.</span><span class="sxs-lookup"><span data-stu-id="1767e-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
-   <span data-ttu-id="1767e-113"><xref:System.Windows.Media.Animation.PowerEase>: Crea un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>p</sup> dove p è uguale al <xref:System.Windows.Media.Animation.PowerEase.Power%2A>proprietà.</span><span class="sxs-lookup"><span data-stu-id="1767e-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
-   <span data-ttu-id="1767e-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Crea un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="1767e-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
-   <span data-ttu-id="1767e-115"><xref:System.Windows.Media.Animation.QuarticEase>: Crea un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="1767e-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
-   <span data-ttu-id="1767e-116"><xref:System.Windows.Media.Animation.QuinticEase>: Creare un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="1767e-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
-   <span data-ttu-id="1767e-117"><xref:System.Windows.Media.Animation.SineEase>: Consente di creare un'animazione che accelera e/o decelera, usando una formula seno.</span><span class="sxs-lookup"><span data-stu-id="1767e-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="1767e-118">È possibile esplorare il comportamento di queste funzioni di interpolazione con l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1767e-118">You can explore the behavior of these easing functions with the following sample.</span></span>  
  
 [<span data-ttu-id="1767e-119">Eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1767e-119">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 <span data-ttu-id="1767e-120">Per applicare una funzione di interpolazione a un'animazione, utilizzare il `EasingFunction` proprietà dell'animazione specificare la funzione di interpolazione per applicare l'animazione.</span><span class="sxs-lookup"><span data-stu-id="1767e-120">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="1767e-121">Nell'esempio seguente viene applicato un <xref:System.Windows.Media.Animation.BounceEase> interpolazione funzione da un <xref:System.Windows.Media.Animation.DoubleAnimation> per creare un effetto di rimbalzo.</span><span class="sxs-lookup"><span data-stu-id="1767e-121">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [<span data-ttu-id="1767e-122">Eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1767e-122">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="1767e-123">Nell'esempio precedente la funzione di interpolazione è applicata a un'animazione From/To/By.</span><span class="sxs-lookup"><span data-stu-id="1767e-123">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="1767e-124">Queste funzioni di interpolazione possono essere applicate anche ad animazioni con fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="1767e-124">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="1767e-125">L'esempio seguente illustra come usare i fotogrammi chiave con funzioni di interpolazione a essi associate per creare l'animazione di un rettangolo che si contrae verso l'alto, rallenta, poi si espande verso il basso (come se cadesse) e rimbalza fino ad arrestarsi.</span><span class="sxs-lookup"><span data-stu-id="1767e-125">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [<span data-ttu-id="1767e-126">Eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1767e-126">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="1767e-127">È possibile utilizzare il <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> proprietà per modificare la funzione di interpolazione comportamento, vale a dire, modificare la modalità di interpolazione l'animazione.</span><span class="sxs-lookup"><span data-stu-id="1767e-127">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="1767e-128">Esistono tre possibili valori è possibile fornire per <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="1767e-128">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
-   <span data-ttu-id="1767e-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolazione segue la formula matematica associata alla funzione di interpolazione.</span><span class="sxs-lookup"><span data-stu-id="1767e-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="1767e-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolazione segue interpolazione al 100% meno l'output della formula associata alla funzione di interpolazione.</span><span class="sxs-lookup"><span data-stu-id="1767e-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="1767e-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Usa interpolazione <xref:System.Windows.Media.Animation.EasingMode.EaseIn> per la prima metà dell'animazione e <xref:System.Windows.Media.Animation.EasingMode.EaseOut> per la seconda metà.</span><span class="sxs-lookup"><span data-stu-id="1767e-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="1767e-132">Le immagini seguenti vengono illustrati i diversi valori di <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> in *f*(*x*) rappresenta l'avanzamento dell'animazione e *t* rappresenta il tempo.</span><span class="sxs-lookup"><span data-stu-id="1767e-132">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="1767e-133">![Grafici di BackEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-133">![BackEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="1767e-134">![Grafici di BounceEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-134">![BounceEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="1767e-135">![Grafici di CircleEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-135">![CircleEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="1767e-136">![Grafici di CubicEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-136">![CubicEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="1767e-137">![ElasticEase con grafici di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-137">![ElasticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="1767e-138">![Grafici ExponentialEase di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-138">![ExponentialEase graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="1767e-139">![QuarticEase con grafici di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-139">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="1767e-140">![QuadraticEase con grafici di EasingMode diversi](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-140">![QuadraticEase with graphs of different easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="1767e-141">![QuarticEase con grafici di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-141">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="1767e-142">![QuinticEase con grafici di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-142">![QuinticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="1767e-143">![SineEase per valori di EasingMode diversi](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="1767e-143">![SineEase for different EasingMode values](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1767e-144">È possibile utilizzare <xref:System.Windows.Media.Animation.PowerEase> per creare lo stesso comportamento di <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, e <xref:System.Windows.Media.Animation.QuinticEase> utilizzando il <xref:System.Windows.Media.Animation.PowerEase.Power%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1767e-144">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="1767e-145">Ad esempio, se si desidera utilizzare <xref:System.Windows.Media.Animation.PowerEase> da sostituire per <xref:System.Windows.Media.Animation.CubicEase>, specificare un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valore 3.</span><span class="sxs-lookup"><span data-stu-id="1767e-145">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="1767e-146">Oltre a utilizzare le funzioni di interpolazione incluse in fase di esecuzione, è possibile creare funzioni di interpolazione personalizzate ereditando dalla <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span><span class="sxs-lookup"><span data-stu-id="1767e-146">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="1767e-147">L'esempio seguente illustra come creare una semplice funzione di interpolazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1767e-147">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="1767e-148">È possibile aggiungere la propria logica matematica per determinare la funzione di interpolazione comportamento eseguendo l'override di <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="1767e-148">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>  
  
 [<span data-ttu-id="1767e-149">Eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1767e-149">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
