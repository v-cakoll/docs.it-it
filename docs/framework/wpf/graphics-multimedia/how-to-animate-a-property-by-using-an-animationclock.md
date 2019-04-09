---
title: "Procedura: Aggiungere un'animazione a una proprietà usando un oggetto AnimationClock"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: 4fa9efc593461d26eabaee5e2f62c1a17da1b543
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201364"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="b309a-102">Procedura: Aggiungere un'animazione a una proprietà usando un oggetto AnimationClock</span><span class="sxs-lookup"><span data-stu-id="b309a-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="b309a-103">In questo esempio viene illustrato come utilizzare <xref:System.Windows.Media.Animation.Clock> oggetti da animare una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b309a-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="b309a-104">Esistono tre modi per animare una proprietà di dipendenza:</span><span class="sxs-lookup"><span data-stu-id="b309a-104">There are three ways to animate a dependency property:</span></span>  
  
-   <span data-ttu-id="b309a-105">Creare un <xref:System.Windows.Media.Animation.AnimationTimeline> e associarlo a tale proprietà utilizzando un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="b309a-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
-   <span data-ttu-id="b309a-106">Usare l'oggetto <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> per applicare un singolo metodo <xref:System.Windows.Media.Animation.AnimationTimeline> a una proprietà di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b309a-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
-   <span data-ttu-id="b309a-107">Creare un <xref:System.Windows.Media.Animation.AnimationClock> da un <xref:System.Windows.Media.Animation.AnimationTimeline> e applicarlo a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b309a-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <xref:System.Windows.Media.Animation.Storyboard> <span data-ttu-id="b309a-108">gli oggetti e il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo consentono di animare le proprietà senza creare e distribuire orologi in modo direttamente (per alcuni esempi, vedere [animare una proprietà utilizzando uno Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) e [animare una proprietà senza Utilizzare uno Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); gli orologi vengono creati e distribuiti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b309a-108">objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b309a-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="b309a-109">Example</span></span>  
 <span data-ttu-id="b309a-110">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a due proprietà simili.</span><span class="sxs-lookup"><span data-stu-id="b309a-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="b309a-111">Per un esempio che illustra come controllare in modo interattivo un <xref:System.Windows.Media.Animation.Clock> dopo l'avvio, vedere [controllare in modo interattivo un oggetto Clock](how-to-interactively-control-a-clock.md).</span><span class="sxs-lookup"><span data-stu-id="b309a-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b309a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b309a-112">See also</span></span>

- [<span data-ttu-id="b309a-113">Aggiungere un'animazione a una proprietà usando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="b309a-113">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="b309a-114">Aggiungere un'animazione a una proprietà senza usare uno storyboard</span><span class="sxs-lookup"><span data-stu-id="b309a-114">Animate a Property Without Using a Storyboard</span></span>](how-to-animate-a-property-without-using-a-storyboard.md)
- [<span data-ttu-id="b309a-115">Cenni preliminari sulle tecniche di animazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="b309a-115">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
