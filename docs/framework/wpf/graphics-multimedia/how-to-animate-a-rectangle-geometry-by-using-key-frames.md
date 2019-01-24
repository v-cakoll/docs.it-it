---
title: 'Procedura: Animare un rettangolo utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: 8e3da6ddf5a49ce690dfe1fc08732376a0998d67
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645072"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="0c1b8-102">Procedura: Animare un rettangolo utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="0c1b8-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="0c1b8-103">In questo esempio illustra come animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry> usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="0c1b8-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c1b8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c1b8-104">Example</span></span>  
 <span data-ttu-id="0c1b8-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="0c1b8-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="0c1b8-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0c1b8-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="0c1b8-107">Durante i primi due secondi, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearRectKeyFrame> classe per animare una modifica graduale nella posizione, larghezza e altezza di un rettangolo.</span><span class="sxs-lookup"><span data-stu-id="0c1b8-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="0c1b8-108">Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearRectKeyFrame> creano una transizione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="0c1b8-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="0c1b8-109">Alla fine del successivo mezzo secondo viene usata un'istanza del <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> classe per diminuire rapidamente l'altezza del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="0c1b8-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="0c1b8-110">Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> creano cambiamenti improvvisi tra valori, vale a dire, la diminuzione di altezza si verifica rapidamente e risulta immediatamente evidente.</span><span class="sxs-lookup"><span data-stu-id="0c1b8-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="0c1b8-111">I due secondi finali viene usata un'istanza del <xref:System.Windows.Media.Animation.SplineRectKeyFrame> classe per il rettangolo di ripristinare le dimensioni e la posizione originale.</span><span class="sxs-lookup"><span data-stu-id="0c1b8-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="0c1b8-112">Ad esempio i fotogrammi chiave spline <xref:System.Windows.Media.Animation.SplineRectKeyFrame> creano una transizione variabile tra i valori a seconda dei valori del <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0c1b8-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="0c1b8-113">In questo esempio l'animazione inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.</span><span class="sxs-lookup"><span data-stu-id="0c1b8-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="0c1b8-114">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="0c1b8-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c1b8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c1b8-115">See also</span></span>
- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="0c1b8-116">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="0c1b8-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="0c1b8-117">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="0c1b8-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
