---
title: 'Procedura: Animare le modifiche di dimensione utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 967537bb1828d323f1dcaa8d049604a1a6e30fa4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374187"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="59a2e-102">Procedura: Animare le modifiche di dimensione utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="59a2e-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="59a2e-103">Questo esempio mostra come animare le modifiche di dimensione usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="59a2e-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59a2e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="59a2e-104">Example</span></span>  
 <span data-ttu-id="59a2e-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.ArcSegment.Size%2A> proprietà di un <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="59a2e-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="59a2e-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="59a2e-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="59a2e-107">Il primo mezzo secondo dell'animazione, viene usata un'istanza del <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> classe per aumentare gradualmente la dimensione dell'arco. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> creano una transizione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="59a2e-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="59a2e-108">Alla fine del successivo mezzo secondo viene usata un'istanza del <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> classe improvvisamente aumentare la dimensione dell'arco. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> creano salti improvvisi tra valori, vale a dire, le modifiche di dimensione si verificano improvvisamente e risultano immediatamente evidenti.</span><span class="sxs-lookup"><span data-stu-id="59a2e-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3.  <span data-ttu-id="59a2e-109">Tramite i due secondi finali viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> classe per aumentare la dimensione dell'arco. Ad esempio i fotogrammi chiave spline <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> creano una transizione variabile tra i valori a seconda dei valori del <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="59a2e-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="59a2e-110">In questo esempio la dimensione dell'arco aumenta lentamente all'inizio e quindi aumenta in misura esponenziale verso la fine dell'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="59a2e-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="59a2e-111">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="59a2e-111">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a2e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59a2e-112">See also</span></span>
- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="59a2e-113">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="59a2e-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="59a2e-114">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="59a2e-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
