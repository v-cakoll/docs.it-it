---
title: 'Procedura: animare un oggetto utilizzando fotogrammi chiave'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f513cda540b3337f1510ee0c46419a12023bcb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="17ce2-102">Procedura: animare un oggetto utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="17ce2-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="17ce2-103">In questo esempio viene illustrato come aggiungere un'animazione a un oggetto, ovvero in questo esempio il <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo, usando i fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="17ce2-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17ce2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="17ce2-104">Example</span></span>  
 <span data-ttu-id="17ce2-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> modifiche di classe per l'animazione di colore per il <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo.</span><span class="sxs-lookup"><span data-stu-id="17ce2-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="17ce2-106">L'animazione di esempio modifica di un pennello di sfondo diversi a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="17ce2-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="17ce2-107">Viene utilizzata la <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> classe da creare tre fotogrammi chiave diversi.</span><span class="sxs-lookup"><span data-stu-id="17ce2-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="17ce2-108">I fotogrammi chiave vengono utilizzati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="17ce2-108">The animation uses key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="17ce2-109">Alla fine del primo secondo, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.LinearGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="17ce2-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="17ce2-110">Questa sezione dell'esempio si applica una sfumatura lineare per il colore di sfondo in modo che il colore passa dal giallo arancione in rosso.</span><span class="sxs-lookup"><span data-stu-id="17ce2-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2.  <span data-ttu-id="17ce2-111">Alla fine del secondo successivo, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.RadialGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="17ce2-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="17ce2-112">Questa sezione dell'esempio si applica una sfumatura radiale per il colore di sfondo in modo che il colore passa da bianco in blu in nero.</span><span class="sxs-lookup"><span data-stu-id="17ce2-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3.  <span data-ttu-id="17ce2-113">Al termine del terzo secondo animata un'istanza di <xref:System.Windows.Media.DrawingBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="17ce2-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="17ce2-114">Questa sezione dell'esempio si applica un motivo a scacchi allo sfondo.</span><span class="sxs-lookup"><span data-stu-id="17ce2-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4.  <span data-ttu-id="17ce2-115">L'animazione inizia nuovamente e viene ripetuta all'infinito.</span><span class="sxs-lookup"><span data-stu-id="17ce2-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17ce2-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>è l'unico tipo di un fotogramma chiave che è possibile utilizzare con la <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> classe.</span><span class="sxs-lookup"><span data-stu-id="17ce2-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="17ce2-117">Fotogrammi chiave come <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> creano modifiche improvvise nei valori, vale a dire, le modifiche di colore in questo esempio si verificano improvvisamente.</span><span class="sxs-lookup"><span data-stu-id="17ce2-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="17ce2-118">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="17ce2-118">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17ce2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17ce2-119">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [<span data-ttu-id="17ce2-120">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="17ce2-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="17ce2-121">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="17ce2-121">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
