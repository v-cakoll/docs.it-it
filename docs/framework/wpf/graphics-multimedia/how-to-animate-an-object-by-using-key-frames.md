---
title: 'Procedura: animare un oggetto utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344712"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="c4d4f-102">Procedura: animare un oggetto utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="c4d4f-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="c4d4f-103">In questo esempio viene illustrato come animare <xref:System.Windows.Controls.Page.Background%2A> un oggetto, che in questo esempio è la proprietà di un <xref:System.Windows.Controls.Page> controllo, utilizzando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4d4f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c4d4f-104">Example</span></span>  
 <span data-ttu-id="c4d4f-105">Nell'esempio seguente <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> viene utilizzata la <xref:System.Windows.Controls.Page.Background%2A> classe per <xref:System.Windows.Controls.Page> animare le modifiche di colore per la proprietà di un controllo.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="c4d4f-106">L'animazione di esempio diventa un pennello di sfondo diverso a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="c4d4f-107">Questa animazione <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> usa la classe per creare tre diversi fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="c4d4f-108">L'animazione utilizza i fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c4d4f-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="c4d4f-109">Alla fine del primo secondo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.LinearGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="c4d4f-110">Questa sezione dell'esempio applica una sfumatura lineare al colore di sfondo in modo che il colore si snoda dal giallo all'arancione al rosso.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="c4d4f-111">Alla fine del secondo successivo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.RadialGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="c4d4f-112">Questa sezione dell'esempio applica una sfumatura radiale al colore di sfondo in modo che il colore si snoda dal bianco al blu al nero.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="c4d4f-113">Alla fine del terzo secondo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.DrawingBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="c4d4f-114">Questa sezione dell'esempio applica un motivo a scacchiera allo sfondo.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="c4d4f-115">L'animazione ricomincia e si ripete all'infinito.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4d4f-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>è l'unico tipo di fotogramma <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> chiave che è possibile utilizzare con la classe.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="c4d4f-117">Fotogrammi <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> chiave come creare improvvisi cambiamenti nei valori, cioè i cambiamenti di colore in questo esempio si verificano improvvisamente.</span><span class="sxs-lookup"><span data-stu-id="c4d4f-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="c4d4f-118">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="c4d4f-118">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4d4f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4d4f-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="c4d4f-120">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="c4d4f-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="c4d4f-121">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="c4d4f-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
