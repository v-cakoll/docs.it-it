---
title: 'Procedura: Animare una proprietà senza utilizzare uno storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: f2cb3533010579f912da62cb2f7fe28d982890c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678135"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a><span data-ttu-id="05dc3-102">Procedura: Animare una proprietà senza utilizzare uno storyboard</span><span class="sxs-lookup"><span data-stu-id="05dc3-102">How to: Animate a Property Without Using a Storyboard</span></span>
<span data-ttu-id="05dc3-103">In questo esempio illustra un modo per applicare un'animazione a una proprietà senza utilizzare un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="05dc3-103">This example shows one way to apply an animation to a property without using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05dc3-104">La funzionalità non è disponibile in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05dc3-104">This functionality is not available in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="05dc3-105">Per informazioni sull'animazione di proprietà in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [animare una proprietà utilizzando uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="05dc3-105">For information about animating a property in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="05dc3-106">Per applicare un'animazione locale a una proprietà, usare il <xref:System.Windows.UIElement.BeginAnimation%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="05dc3-106">To apply a local animation to a property, use the <xref:System.Windows.UIElement.BeginAnimation%2A> method.</span></span> <span data-ttu-id="05dc3-107">Questo metodo accetta due parametri: un <xref:System.Windows.DependencyProperty> che specifica la proprietà da animare e l'animazione da applicare a tale proprietà.</span><span class="sxs-lookup"><span data-stu-id="05dc3-107">This method takes two parameters: a <xref:System.Windows.DependencyProperty> that specifies the property to animate, and the animation to apply to that property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05dc3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="05dc3-108">Example</span></span>  
 <span data-ttu-id="05dc3-109">Nell'esempio seguente illustra come animare il colore di larghezza e lo sfondo di un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="05dc3-109">The following example shows how to animate the width and background color of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 <span data-ttu-id="05dc3-110">Un'ampia gamma di classi di animazione di <xref:System.Windows.Media.Animation> dello spazio dei nomi presente per l'animazione di diversi tipi di proprietà.</span><span class="sxs-lookup"><span data-stu-id="05dc3-110">A variety of animation classes in the <xref:System.Windows.Media.Animation> namespace exist for animating different types of properties.</span></span> <span data-ttu-id="05dc3-111">Per altre informazioni sulle proprietà di animazione vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="05dc3-111">For more information about animating properties, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="05dc3-112">Per altre informazioni sulle proprietà di dipendenza (il tipo di proprietà che vengono visualizzate in questi esempi) e le relative funzionalità vedere [Cenni preliminari sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="05dc3-112">For more information about dependency properties (the type of properties that are shown in these examples) and their features, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="05dc3-113">Esistono altri modi per aggiungere un'animazione senza usare <xref:System.Windows.Media.Animation.Storyboard> oggetti; per altre informazioni, vedere [Cenni preliminari sulle tecniche di animazione di proprietà](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span><span class="sxs-lookup"><span data-stu-id="05dc3-113">There are other ways to animate without using <xref:System.Windows.Media.Animation.Storyboard> objects; for more information, see [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05dc3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05dc3-114">See also</span></span>
- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="05dc3-115">Cenni preliminari sulle tecniche di animazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="05dc3-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
- [<span data-ttu-id="05dc3-116">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="05dc3-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
