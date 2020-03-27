---
title: 'Procedura: controllare la durata delle animazioni con fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344729"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="eed45-102">Procedura: controllare la durata delle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="eed45-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="eed45-103">Questo esempio mostra come controllare la temporizzazione dei fotogrammi chiave all'interno di un'animazione con fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="eed45-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="eed45-104">Come altre animazioni, le <xref:System.Windows.Media.Animation.Timeline.Duration%2A> animazioni con fotogrammi chiave hanno una proprietà.</span><span class="sxs-lookup"><span data-stu-id="eed45-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="eed45-105">Oltre a specificare la durata di un'animazione, è necessario specificare quale parte di tale durata viene assegnata a ciascuno dei relativi fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="eed45-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="eed45-106">Per allocare il tempo, <xref:System.Windows.Media.Animation.KeyTime> specificare un per ogni fotogramma chiave nell'animazione.</span><span class="sxs-lookup"><span data-stu-id="eed45-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="eed45-107">Il <xref:System.Windows.Media.Animation.KeyTime> per ogni fotogramma chiave specifica quando termina un fotogramma chiave (non specifica la durata di riproduzione di un fotogramma chiave).</span><span class="sxs-lookup"><span data-stu-id="eed45-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="eed45-108">È possibile <xref:System.Windows.Media.Animation.KeyTime> specificare <xref:System.TimeSpan> un valore, come percentuale o come <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> valore <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> o speciale.</span><span class="sxs-lookup"><span data-stu-id="eed45-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="eed45-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="eed45-109">Example</span></span>

<span data-ttu-id="eed45-110">Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> viene utilizzato un per animare un rettangolo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="eed45-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="eed45-111">I tempi chiave dei fotogrammi chiave sono impostati con <xref:System.TimeSpan> valori.</span><span class="sxs-lookup"><span data-stu-id="eed45-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="eed45-112">La figura seguente mostra quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="eed45-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="eed45-113">![I valori dei fotogrammi chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="eed45-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="eed45-114">L'esempio seguente mostra un'animazione identica, con la differenza che i tempi chiave dei fotogrammi chiave sono impostati con valori percentuali.</span><span class="sxs-lookup"><span data-stu-id="eed45-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="eed45-115">La figura seguente mostra quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="eed45-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="eed45-116">![I valori dei fotogrammi chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="eed45-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="eed45-117">Nell'esempio <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> successivo vengono utilizzati i valori di ora chiave.</span><span class="sxs-lookup"><span data-stu-id="eed45-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="eed45-118">La figura seguente mostra quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="eed45-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="eed45-119">![I valori dei fotogrammi chiave vengono raggiunti a 3,3, 6,6 e 9,9 secondi](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="eed45-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="eed45-120">Nell'esempio <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> finale vengono utilizzati valori temporali chiave.</span><span class="sxs-lookup"><span data-stu-id="eed45-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="eed45-121">La figura seguente mostra quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="eed45-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="eed45-122">![I valori dei fotogrammi chiave vengono raggiunti a 0, 5 e 10 secondi](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="eed45-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="eed45-123">Per semplicità, le versioni di codice di questo esempio usano animazioni locali, non storyboard, perché solo una singola animazione viene applicata a una singola proprietà, ma gli esempi possono essere modificati per usare gli storyboard.</span><span class="sxs-lookup"><span data-stu-id="eed45-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="eed45-124">Per un esempio che illustra come dichiarare uno storyboard nel codice, vedere [Animare una proprietà tramite uno Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="eed45-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="eed45-125">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="eed45-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="eed45-126">Per ulteriori informazioni sulle animazioni con fotogrammi chiave, consultate Cenni preliminari sulle animazioni con [fotogrammi chiave.](key-frame-animations-overview.md)</span><span class="sxs-lookup"><span data-stu-id="eed45-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eed45-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eed45-127">See also</span></span>

- [<span data-ttu-id="eed45-128">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="eed45-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="eed45-129">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="eed45-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="eed45-130">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="eed45-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
