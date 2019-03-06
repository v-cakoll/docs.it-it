---
title: 'Procedura: Animare un Boolean utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 503e8ec8bdaf88bcba4093075b1e7216b7cd3746
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361955"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="bff5b-102">Procedura: Animare un Boolean utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="bff5b-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="bff5b-103">In questo esempio illustra come animare il valore booleano della proprietà di un <xref:System.Windows.Controls.Button> controllo usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="bff5b-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bff5b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bff5b-104">Example</span></span>  
 <span data-ttu-id="bff5b-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.UIElement.IsEnabled%2A> proprietà di un <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="bff5b-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="bff5b-106">Tutti i fotogrammi chiave in questo esempio usano un'istanza di <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> classe.</span><span class="sxs-lookup"><span data-stu-id="bff5b-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="bff5b-107">Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> creano salti improvvisi tra valori, vale a dire, lo spostamento dell'animazione è a scatti.</span><span class="sxs-lookup"><span data-stu-id="bff5b-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="bff5b-108">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="bff5b-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bff5b-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bff5b-109">See also</span></span>
- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="bff5b-110">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="bff5b-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="bff5b-111">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="bff5b-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
