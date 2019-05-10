---
title: 'Procedura: Accumulare valori di animazione durante i cicli ripetuti'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: bccdc9b7bf2d5a0ea476e39e8d54107854db7ae3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591464"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="fb399-102">Procedura: Accumulare valori di animazione durante i cicli ripetuti</span><span class="sxs-lookup"><span data-stu-id="fb399-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="fb399-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà da accumulare valori di animazione durante i cicli ripetuti.</span><span class="sxs-lookup"><span data-stu-id="fb399-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb399-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb399-104">Example</span></span>  
 <span data-ttu-id="fb399-105">Usare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà accumulare valori di base di un'animazione durante i cicli ripetuti.</span><span class="sxs-lookup"><span data-stu-id="fb399-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="fb399-106">Ad esempio, se si imposta un'animazione per ripetere 9 volte (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "x 9") e si imposta la proprietà da animare compreso tra 10 e 15 (da = 10 a = 15), la proprietà viene animata da 10 a 15 durante il primo ciclo, da 15 a 20 durante il secondo ciclo , da 20 a 25 durante il ciclo di terzo e così via.</span><span class="sxs-lookup"><span data-stu-id="fb399-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="fb399-107">Di conseguenza, ogni ciclo di animazione Usa il valore finale dell'animazione dal ciclo di animazione precedente come valore di base.</span><span class="sxs-lookup"><span data-stu-id="fb399-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="fb399-108">È possibile usare il `IsCumulative` proprietà con più semplici animazioni e la maggior parte delle animazioni con fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="fb399-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="fb399-109">Per altre informazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md) e [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fb399-109">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="fb399-110">Nell'esempio seguente viene illustrato questo comportamento aggiungendo un'animazione alla larghezza di quattro rettangoli.</span><span class="sxs-lookup"><span data-stu-id="fb399-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="fb399-111">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fb399-111">The example:</span></span>  
  
- <span data-ttu-id="fb399-112">Aggiunge un'animazione con il primo rettangolo <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="fb399-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="fb399-113">Aggiunge un'animazione con secondo rettangolo <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà sul valore predefinito di `false`.</span><span class="sxs-lookup"><span data-stu-id="fb399-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
- <span data-ttu-id="fb399-114">Anima il terzo rettangolo <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="fb399-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="fb399-115">Anima il rettangolo con ultimo <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="fb399-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="fb399-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb399-116">See also</span></span>

- [<span data-ttu-id="fb399-117">Aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione</span><span class="sxs-lookup"><span data-stu-id="fb399-117">Add an Animation Output Value to an Animation Starting Value</span></span>](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="fb399-118">Ripetere un'animazione</span><span class="sxs-lookup"><span data-stu-id="fb399-118">Repeat an Animation</span></span>](how-to-repeat-an-animation.md)
- [<span data-ttu-id="fb399-119">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="fb399-119">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="fb399-120">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="fb399-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="fb399-121">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="fb399-121">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
