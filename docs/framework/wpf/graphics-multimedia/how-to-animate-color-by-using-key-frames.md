---
title: "Procedura: Aggiungere un'animazione al colore usando fotogrammi chiave"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: e579c4beb757ccf58eb1b9ca1f3852a5b96cac1a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59326086"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="6cf69-102">Procedura: Aggiungere un'animazione al colore usando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="6cf69-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="6cf69-103">In questo esempio illustra come animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="6cf69-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cf69-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6cf69-104">Example</span></span>  
 <span data-ttu-id="6cf69-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà di un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="6cf69-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="6cf69-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6cf69-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="6cf69-107">Durante i primi due secondi, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearColorKeyFrame> classe a modificare gradualmente il colore da verde a rosso.</span><span class="sxs-lookup"><span data-stu-id="6cf69-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="6cf69-108">Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearColorKeyFrame> creano una transizione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="6cf69-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="6cf69-109">Alla fine del successivo mezzo secondo viene usata un'istanza del <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> classe per modificare rapidamente il colore da rosso a giallo.</span><span class="sxs-lookup"><span data-stu-id="6cf69-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="6cf69-110">Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> creano cambiamenti improvvisi tra valori, vale a dire, la modifica di colore in questa parte dell'animazione eseguite più rapidamente e risulta immediatamente evidente.</span><span class="sxs-lookup"><span data-stu-id="6cf69-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="6cf69-111">I due secondi finali viene usata un'istanza del <xref:System.Windows.Media.Animation.SplineColorKeyFrame> classe modificare nuovamente il colore, questa volta da giallo a verde.</span><span class="sxs-lookup"><span data-stu-id="6cf69-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="6cf69-112">Ad esempio i fotogrammi chiave spline <xref:System.Windows.Media.Animation.SplineColorKeyFrame> creano una transizione variabile tra i valori a seconda dei valori del <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="6cf69-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="6cf69-113">In questo esempio, il cambio di colore inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.</span><span class="sxs-lookup"><span data-stu-id="6cf69-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="6cf69-114">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="6cf69-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf69-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cf69-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="6cf69-116">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="6cf69-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="6cf69-117">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="6cf69-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
