---
title: 'Procedura: animare il colore utilizzando fotogrammi chiave'
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
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d117d57e5cc761aa2f31fd6531bff8d96ea30dc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="83429-102">Procedura: animare il colore utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="83429-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="83429-103">In questo esempio viene illustrato come animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> utilizzando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="83429-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83429-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="83429-104">Example</span></span>  
 <span data-ttu-id="83429-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà di un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="83429-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="83429-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="83429-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="83429-107">Durante i primi due secondi, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearColorKeyFrame> classe per modificare gradualmente il colore da verde a rosso.</span><span class="sxs-lookup"><span data-stu-id="83429-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="83429-108">Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearColorKeyFrame> creare una transizione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="83429-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="83429-109">Durante la fine della riga successiva viene utilizzata un'istanza di mezzo secondo, il <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> classe per modificare rapidamente il colore da rosso a giallo.</span><span class="sxs-lookup"><span data-stu-id="83429-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="83429-110">Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> creano modifiche improvvise tra valori, vale a dire, la modifica del colore in questa parte dell'animazione avviene in modo rapido e risulta immediatamente evidente.</span><span class="sxs-lookup"><span data-stu-id="83429-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="83429-111">Durante i due secondi finali, viene utilizzata un'istanza del <xref:System.Windows.Media.Animation.SplineColorKeyFrame> classe per modificare nuovamente il colore, questa volta da giallo a verde.</span><span class="sxs-lookup"><span data-stu-id="83429-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="83429-112">Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineColorKeyFrame> creare una transizione tra i valori in base ai valori delle variabile di <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="83429-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="83429-113">In questo esempio, il cambio di colore inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.</span><span class="sxs-lookup"><span data-stu-id="83429-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="83429-114">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="83429-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83429-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83429-115">See Also</span></span>  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [<span data-ttu-id="83429-116">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="83429-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="83429-117">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="83429-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
