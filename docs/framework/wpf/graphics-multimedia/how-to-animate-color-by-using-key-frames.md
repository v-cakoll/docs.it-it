---
title: 'Procedura: animare il colore utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344742"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="ffefb-102">Procedura: animare il colore utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="ffefb-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="ffefb-103">In questo esempio viene <xref:System.Windows.Media.SolidColorBrush.Color%2A> illustrato <xref:System.Windows.Media.SolidColorBrush> come animare l'oggetto di oggetto utilizzando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="ffefb-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffefb-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ffefb-104">Example</span></span>  
 <span data-ttu-id="ffefb-105">Nell'esempio riportato di seguito viene utilizzata la <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà di un <xref:System.Windows.Media.SolidColorBrush>oggetto .</span><span class="sxs-lookup"><span data-stu-id="ffefb-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="ffefb-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ffefb-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="ffefb-107">Durante i primi due secondi, <xref:System.Windows.Media.Animation.LinearColorKeyFrame> utilizza un'istanza della classe per modificare gradualmente il colore da verde a rosso.</span><span class="sxs-lookup"><span data-stu-id="ffefb-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="ffefb-108">I fotogrammi <xref:System.Windows.Media.Animation.LinearColorKeyFrame> chiave lineari come creano una transizione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="ffefb-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="ffefb-109">Durante la fine del mezzo secondo successivo, <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> utilizza un'istanza della classe per modificare rapidamente il colore da rosso a giallo.</span><span class="sxs-lookup"><span data-stu-id="ffefb-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="ffefb-110">I fotogrammi <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> chiave discreti come creano cambiamenti improvvisi tra i valori, ovvero il cambiamento di colore in questa parte dell'animazione si verifica rapidamente e non è sottile.</span><span class="sxs-lookup"><span data-stu-id="ffefb-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="ffefb-111">Durante gli ultimi due secondi, <xref:System.Windows.Media.Animation.SplineColorKeyFrame> usa un'istanza della classe per cambiare nuovamente il colore, questa volta da giallo a verde.</span><span class="sxs-lookup"><span data-stu-id="ffefb-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="ffefb-112">I fotogrammi <xref:System.Windows.Media.Animation.SplineColorKeyFrame> chiave della spline, ad esempio, <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> creano una transizione variabile tra i valori in base ai valori della proprietà.</span><span class="sxs-lookup"><span data-stu-id="ffefb-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="ffefb-113">In questo esempio, il cambio di colore inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.</span><span class="sxs-lookup"><span data-stu-id="ffefb-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="ffefb-114">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="ffefb-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffefb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffefb-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="ffefb-116">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="ffefb-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="ffefb-117">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="ffefb-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
