---
title: 'Procedura: aggiungere un valore di output dell''animazione a un valore iniziale dell''animazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a670a29e4bd982418ac92ef0e2ac65635763671
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="4ab27-102">Procedura: aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione</span><span class="sxs-lookup"><span data-stu-id="4ab27-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="4ab27-103">In questo esempio viene illustrato come aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione.</span><span class="sxs-lookup"><span data-stu-id="4ab27-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ab27-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ab27-104">Example</span></span>  
 <span data-ttu-id="4ab27-105">Il <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà consente di specificare se si desidera che il valore di output di un'animazione aggiunto al valore iniziale (valore di base) di una proprietà animata.</span><span class="sxs-lookup"><span data-stu-id="4ab27-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="4ab27-106">È possibile utilizzare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà con le animazioni di base e la maggior parte delle animazioni di fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="4ab27-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="4ab27-107">Per ulteriori informazioni, vedere [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) e [Cenni preliminari sulle animazioni di fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4ab27-107">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="4ab27-108">Nell'esempio seguente viene illustrato l'effetto dell'uso di <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimation> e l'utilizzo di <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="4ab27-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4ab27-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ab27-109">See Also</span></span>  
 [<span data-ttu-id="4ab27-110">Accumulare valori di animazione durante i cicli ripetuti</span><span class="sxs-lookup"><span data-stu-id="4ab27-110">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="4ab27-111">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="4ab27-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="4ab27-112">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="4ab27-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="4ab27-113">Animazione e temporizzazione</span><span class="sxs-lookup"><span data-stu-id="4ab27-113">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="4ab27-114">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="4ab27-114">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
