---
title: "Procedura: Aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 3f1110880b7a8d4bcef40bcb66bcade6597a15dc
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303361"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="22032-102">Procedura: Aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione</span><span class="sxs-lookup"><span data-stu-id="22032-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="22032-103">In questo esempio viene illustrato come aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione.</span><span class="sxs-lookup"><span data-stu-id="22032-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22032-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="22032-104">Example</span></span>  
 <span data-ttu-id="22032-105">Il <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà consente di specificare se si desidera che il valore di output di un'animazione aggiunto al valore inizio (valore di base) di una proprietà animata.</span><span class="sxs-lookup"><span data-stu-id="22032-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="22032-106">È possibile usare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà con più semplici animazioni e la maggior parte delle animazioni con fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="22032-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="22032-107">Per altre informazioni, vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) e [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="22032-107">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="22032-108">L'esempio seguente illustra l'effetto dell'uso di <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimation> e usando la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="22032-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="22032-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22032-109">See also</span></span>
- [<span data-ttu-id="22032-110">Accumulare valori di animazione durante i cicli ripetuti</span><span class="sxs-lookup"><span data-stu-id="22032-110">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="22032-111">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="22032-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="22032-112">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="22032-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="22032-113">Animazione e temporizzazione procedure</span><span class="sxs-lookup"><span data-stu-id="22032-113">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
