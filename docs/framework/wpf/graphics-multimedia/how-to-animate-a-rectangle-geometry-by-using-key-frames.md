---
title: 'Procedura: animare un rettangolo utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344685"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="f7fd9-102">Procedura: animare un rettangolo utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="f7fd9-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="f7fd9-103">In questo esempio viene <xref:System.Windows.Media.RectangleGeometry.Rect%2A> illustrato <xref:System.Windows.Media.RectangleGeometry> come animare la proprietà di un utilizzando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="f7fd9-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7fd9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f7fd9-104">Example</span></span>  
 <span data-ttu-id="f7fd9-105">Nell'esempio riportato di seguito viene utilizzata la <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry>oggetto .</span><span class="sxs-lookup"><span data-stu-id="f7fd9-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="f7fd9-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f7fd9-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="f7fd9-107">Durante i primi due secondi, <xref:System.Windows.Media.Animation.LinearRectKeyFrame> utilizza un'istanza della classe per animare una modifica graduale della posizione, larghezza e altezza di un rettangolo.</span><span class="sxs-lookup"><span data-stu-id="f7fd9-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="f7fd9-108">I fotogrammi <xref:System.Windows.Media.Animation.LinearRectKeyFrame> chiave lineari come creano una transizione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="f7fd9-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="f7fd9-109">Durante la fine del mezzo secondo successivo, <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> utilizza un'istanza della classe per ridurre improvvisamente l'altezza del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="f7fd9-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="f7fd9-110">Fotogrammi chiave <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> discreti come creano cambiamenti improvvisi tra i valori, cioè la diminuzione dell'altezza si verifica rapidamente e non è sottile.</span><span class="sxs-lookup"><span data-stu-id="f7fd9-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="f7fd9-111">Durante gli ultimi due secondi, <xref:System.Windows.Media.Animation.SplineRectKeyFrame> utilizza un'istanza della classe per riportare il rettangolo alle dimensioni e alla posizione originali.</span><span class="sxs-lookup"><span data-stu-id="f7fd9-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="f7fd9-112">I fotogrammi <xref:System.Windows.Media.Animation.SplineRectKeyFrame> chiave della spline, ad esempio, <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> creano una transizione variabile tra i valori in base ai valori della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7fd9-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="f7fd9-113">In questo esempio l'animazione inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.</span><span class="sxs-lookup"><span data-stu-id="f7fd9-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="f7fd9-114">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="f7fd9-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7fd9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7fd9-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="f7fd9-116">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="f7fd9-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="f7fd9-117">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="f7fd9-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
