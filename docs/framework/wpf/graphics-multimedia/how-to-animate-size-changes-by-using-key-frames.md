---
title: 'Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30ee897efd01712bf4313da87e1050c5a16e4523
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="15aeb-102">Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="15aeb-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="15aeb-103">Questo esempio mostra come animare le modifiche di dimensione usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="15aeb-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15aeb-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="15aeb-104">Example</span></span>  
 <span data-ttu-id="15aeb-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Media.ArcSegment.Size%2A> proprietà di un <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="15aeb-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="15aeb-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="15aeb-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="15aeb-107">Durante il primo mezzo secondo dell'animazione, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> classe aumentare gradualmente la dimensione dell'arco. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> creare una transizione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="15aeb-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="15aeb-108">Alla fine della riga successiva viene utilizzata un'istanza di mezzo secondo, il <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> classe improvvisamente aumentare le dimensioni dell'arco. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> creano improvvisi tra due valori, ovvero le modifiche di dimensione si verificano improvvisamente e risultano immediatamente evidenti.</span><span class="sxs-lookup"><span data-stu-id="15aeb-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3.  <span data-ttu-id="15aeb-109">Su due secondi finali, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> classe per aumentare le dimensioni dell'arco. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> creare una transizione tra i valori in base ai valori delle variabile di <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="15aeb-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="15aeb-110">In questo esempio la dimensione dell'arco aumenta lentamente all'inizio e quindi aumenta in misura esponenziale verso la fine dell'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="15aeb-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="15aeb-111">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="15aeb-111">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15aeb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15aeb-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [<span data-ttu-id="15aeb-113">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="15aeb-113">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="15aeb-114">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="15aeb-114">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
