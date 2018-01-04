---
title: 'Procedura: accumulare valori di animazione durante i cicli ripetuti'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a91856cdfcf1ca7ae87e8e571306170feecb7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="b7caa-102">Procedura: accumulare valori di animazione durante i cicli ripetuti</span><span class="sxs-lookup"><span data-stu-id="b7caa-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="b7caa-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà per accumulare i valori di animazione nei cicli ripetuti.</span><span class="sxs-lookup"><span data-stu-id="b7caa-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7caa-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7caa-104">Example</span></span>  
 <span data-ttu-id="b7caa-105">Utilizzare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà per accumulare i valori di base di un'animazione nei cicli ripetuti.</span><span class="sxs-lookup"><span data-stu-id="b7caa-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="b7caa-106">Ad esempio, se si imposta un'animazione per ripetere 9 volte (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") e si imposta la proprietà da animare tra 10 e 15 (da = 10 a = 15), la proprietà viene animata da 10 a 15 durante il primo ciclo, da 15 a 20 durante il secondo ciclo , da 20 a 25 durante il ciclo terzo e così via.</span><span class="sxs-lookup"><span data-stu-id="b7caa-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="b7caa-107">Di conseguenza, ogni ciclo di animazione utilizza il valore di animazione finale dal ciclo di animazione precedente come valore di base.</span><span class="sxs-lookup"><span data-stu-id="b7caa-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="b7caa-108">È possibile utilizzare il `IsCumulative` proprietà con le animazioni di base e la maggior parte delle animazioni di fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="b7caa-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="b7caa-109">Per ulteriori informazioni, vedere [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) e [Cenni preliminari sulle animazioni di fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b7caa-109">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="b7caa-110">Nell'esempio seguente viene illustrato questo comportamento aggiungendo un'animazione alla larghezza di quattro rettangoli.</span><span class="sxs-lookup"><span data-stu-id="b7caa-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="b7caa-111">Esempio:</span><span class="sxs-lookup"><span data-stu-id="b7caa-111">The example:</span></span>  
  
-   <span data-ttu-id="b7caa-112">Aggiunge un'animazione al primo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="b7caa-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="b7caa-113">Aggiunge un'animazione con il secondo rettangolo <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà sul valore predefinito di `false`.</span><span class="sxs-lookup"><span data-stu-id="b7caa-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
-   <span data-ttu-id="b7caa-114">Aggiunge un'animazione il terzo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="b7caa-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="b7caa-115">Aggiunge un'animazione l'ultimo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="b7caa-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b7caa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7caa-116">See Also</span></span>  
 [<span data-ttu-id="b7caa-117">Aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione</span><span class="sxs-lookup"><span data-stu-id="b7caa-117">Add an Animation Output Value to an Animation Starting Value</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [<span data-ttu-id="b7caa-118">Ripetere un'animazione</span><span class="sxs-lookup"><span data-stu-id="b7caa-118">Repeat an Animation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [<span data-ttu-id="b7caa-119">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="b7caa-119">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="b7caa-120">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="b7caa-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="b7caa-121">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b7caa-121">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
