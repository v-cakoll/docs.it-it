---
title: 'Procedura: controllare la durata delle animazioni con fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: d65bf6f7643adf1d98d468853ae8017a4a6554ac
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43892678"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="fa6c9-102">Procedura: controllare la durata delle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="fa6c9-102">How to: Control Key-Frame Animation Timing</span></span>
<span data-ttu-id="fa6c9-103">In questo esempio viene illustrato come controllare l'intervallo di fotogrammi chiave all'interno di un'animazione con fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="fa6c9-104">Analogamente alle altre animazioni, animazioni con fotogrammi chiave hanno un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="fa6c9-105">Oltre a specificare la durata di un'animazione, è necessario specificare quale parte di tale durata viene assegnata a ciascuno dei relativi fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="fa6c9-106">Per assegnare l'ora, specificare un <xref:System.Windows.Media.Animation.KeyTime> per ogni fotogramma chiave l'animazione.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>  
  
 <span data-ttu-id="fa6c9-107">Il <xref:System.Windows.Media.Animation.KeyTime> per ogni fotogramma chiave specifica quando termina un fotogramma chiave (non specifica la durata di riproduzione di un fotogramma chiave).</span><span class="sxs-lookup"><span data-stu-id="fa6c9-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="fa6c9-108">È possibile specificare una <xref:System.Windows.Media.Animation.KeyTime> come un <xref:System.TimeSpan> valore, come una percentuale o il <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valore speciale.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa6c9-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa6c9-109">Example</span></span>  
 <span data-ttu-id="fa6c9-110">L'esempio seguente usa un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> per animare un rettangolo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="fa6c9-111">Le chiavi temporali i fotogrammi chiave sono impostate con <xref:System.TimeSpan> valori.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 <span data-ttu-id="fa6c9-112">La figura seguente illustra quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-112">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="fa6c9-113">![I valori di chiave vengono raggiunti a 3, 4 e 10 secondi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="fa6c9-113">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>  
  
 <span data-ttu-id="fa6c9-114">L'esempio seguente illustra un'animazione che è identica, ad eccezione del fatto che le chiavi temporali i fotogrammi chiave sono impostate con i valori in percentuale.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 <span data-ttu-id="fa6c9-115">La figura seguente illustra quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-115">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="fa6c9-116">![I valori di chiave vengono raggiunti a 3, 4 e 10 secondi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="fa6c9-116">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>  
  
 <span data-ttu-id="fa6c9-117">L'esempio seguente usa <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ora i valori di chiave.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 <span data-ttu-id="fa6c9-118">La figura seguente illustra quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-118">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="fa6c9-119">![I valori di chiave vengono raggiunti 3.3,6.6 e 9,9 secondi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="fa6c9-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>  
  
 <span data-ttu-id="fa6c9-120">L'esempio finale Usa <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> ora i valori di chiave.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 <span data-ttu-id="fa6c9-121">La figura seguente illustra quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-121">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="fa6c9-122">![I valori di chiave vengono raggiunti a 0, 5 e 10 secondi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="fa6c9-122">![Key values are reached at 0, 5, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>  
  
 <span data-ttu-id="fa6c9-123">Per semplicità, le versioni di codice di questo esempio Usa le animazioni locali, non gli storyboard, perché si applichino solo una singola animazione a una singola proprietà, ma gli esempi possono essere modificati per usare invece gli storyboard.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="fa6c9-124">Per un esempio che illustra come dichiarare uno storyboard nel codice, vedere [animare una proprietà utilizzando uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="fa6c9-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="fa6c9-125">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="fa6c9-125">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="fa6c9-126">Per altre informazioni sulle animazioni con fotogrammi chiave, vedere la [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fa6c9-126">For more information about key frame animations, see the [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6c9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa6c9-127">See Also</span></span>  
 [<span data-ttu-id="fa6c9-128">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="fa6c9-128">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="fa6c9-129">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="fa6c9-129">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="fa6c9-130">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="fa6c9-130">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
