---
title: 'Procedura: animare un valore Boolean utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344926"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="7d276-102">Procedura: animare un valore Boolean utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7d276-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="7d276-103">In questo esempio viene illustrato come <xref:System.Windows.Controls.Button> animare il valore della proprietà Boolean di un controllo utilizzando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="7d276-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d276-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d276-104">Example</span></span>  
 <span data-ttu-id="7d276-105">Nell'esempio seguente <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> viene utilizzata <xref:System.Windows.UIElement.IsEnabled%2A> la <xref:System.Windows.Controls.Button> classe per animare la proprietà di un controllo.</span><span class="sxs-lookup"><span data-stu-id="7d276-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="7d276-106">Tutti i fotogrammi chiave in questo <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> esempio usano un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="7d276-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="7d276-107">I fotogrammi <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> chiave discreti come creano salti improvvisi tra i valori, ovvero il movimento dell'animazione è a scatti.</span><span class="sxs-lookup"><span data-stu-id="7d276-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="7d276-108">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="7d276-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d276-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d276-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="7d276-110">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7d276-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="7d276-111">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7d276-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
