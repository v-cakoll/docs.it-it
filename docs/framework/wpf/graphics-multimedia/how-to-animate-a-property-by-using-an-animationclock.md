---
title: "Procedura: animare una proprietà utilizzando un oggetto AnimationClock"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47df7aaad45000bc8c761a9bb9022d37e0f0828c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="c26b2-102">Procedura: animare una proprietà utilizzando un oggetto AnimationClock</span><span class="sxs-lookup"><span data-stu-id="c26b2-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="c26b2-103">In questo esempio viene illustrato come utilizzare <xref:System.Windows.Media.Animation.Clock> oggetti per aggiungere un'animazione a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="c26b2-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="c26b2-104">Esistono tre modi per animare una proprietà di dipendenza:</span><span class="sxs-lookup"><span data-stu-id="c26b2-104">There are three ways to animate a dependency property:</span></span>  
  
-   <span data-ttu-id="c26b2-105">Creare un <xref:System.Windows.Media.Animation.AnimationTimeline> e associarlo a tale proprietà utilizzando un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="c26b2-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
-   <span data-ttu-id="c26b2-106">Utilizzare l'oggetto <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo per applicare un singolo <xref:System.Windows.Media.Animation.AnimationTimeline> a una proprietà di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c26b2-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
-   <span data-ttu-id="c26b2-107">Creare un <xref:System.Windows.Media.Animation.AnimationClock> da un <xref:System.Windows.Media.Animation.AnimationTimeline> e applicarlo a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="c26b2-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="c26b2-108"><xref:System.Windows.Media.Animation.Storyboard>gli oggetti e <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo consente di animare le proprietà senza direttamente la creazione e la distribuzione di clock (per esempi, vedere [animazione di una proprietà utilizzando uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) e [aggiungere un'animazione a una proprietà senza Utilizzo di uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); orologi vengono creati e distribuiti automaticamente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c26b2-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c26b2-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c26b2-109">Example</span></span>  
 <span data-ttu-id="c26b2-110">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a due proprietà simili.</span><span class="sxs-lookup"><span data-stu-id="c26b2-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="c26b2-111">Per un esempio che illustra come controllare in modo interattivo un <xref:System.Windows.Media.Animation.Clock> dopo l'avvio, vedere [controllare in modo interattivo un orologio](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).</span><span class="sxs-lookup"><span data-stu-id="c26b2-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c26b2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c26b2-112">See Also</span></span>  
 [<span data-ttu-id="c26b2-113">Animare una proprietà utilizzando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="c26b2-113">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="c26b2-114">Animare una proprietà senza usare uno storyboard</span><span class="sxs-lookup"><span data-stu-id="c26b2-114">Animate a Property Without Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [<span data-ttu-id="c26b2-115">Cenni preliminari sulle tecniche di animazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="c26b2-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
