---
title: "Procedura: Aggiungere un'animazione a un oggetto usando fotogrammi chiave"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: ffbe1845b634c8f94eb6a10dfa44fcf9903e0cd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933914"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="edb55-102">Procedura: Aggiungere un'animazione a un oggetto usando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="edb55-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="edb55-103">Questo esempio illustra come animare un oggetto, che in questo esempio è la <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo, usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="edb55-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edb55-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="edb55-104">Example</span></span>  
 <span data-ttu-id="edb55-105">Nell'esempio seguente viene usata <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> la classe per aggiungere un'animazione alle modifiche <xref:System.Windows.Controls.Page.Background%2A> dei colori per <xref:System.Windows.Controls.Page> la proprietà di un controllo.</span><span class="sxs-lookup"><span data-stu-id="edb55-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="edb55-106">L'animazione di esempio viene modificata in un pennello dello sfondo diverso a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="edb55-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="edb55-107">Questa animazione usa la <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> classe per creare tre fotogrammi chiave diversi.</span><span class="sxs-lookup"><span data-stu-id="edb55-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="edb55-108">L'animazione usa i fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="edb55-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="edb55-109">Alla fine del primo secondo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.LinearGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="edb55-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="edb55-110">Questa sezione dell'esempio applica una sfumatura lineare al colore di sfondo, in modo che il colore passi da giallo a arancione a rosso.</span><span class="sxs-lookup"><span data-stu-id="edb55-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="edb55-111">Alla fine del secondo successivo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.RadialGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="edb55-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="edb55-112">Questa sezione dell'esempio applica una sfumatura radiale al colore di sfondo, in modo che il colore passi da bianco a blu a nero.</span><span class="sxs-lookup"><span data-stu-id="edb55-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="edb55-113">Alla fine del terzo secondo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.DrawingBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="edb55-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="edb55-114">Questa sezione dell'esempio applica uno schema a scacchi allo sfondo.</span><span class="sxs-lookup"><span data-stu-id="edb55-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="edb55-115">L'animazione inizia di nuovo e si ripete per un tempo illimitato.</span><span class="sxs-lookup"><span data-stu-id="edb55-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="edb55-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>è l'unico tipo di fotogramma chiave che è possibile utilizzare con <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> la classe.</span><span class="sxs-lookup"><span data-stu-id="edb55-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="edb55-117">I fotogrammi <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> chiave come creano modifiche improvvise nei valori, ovvero le modifiche dei colori in questo esempio si verificano improvvisamente.</span><span class="sxs-lookup"><span data-stu-id="edb55-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="edb55-118">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="edb55-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb55-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edb55-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="edb55-120">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="edb55-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="edb55-121">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="edb55-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
