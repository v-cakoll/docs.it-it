---
title: 'Procedura: Animare a una rotazione tridimensionale utilizzando i fotogrammi chiave (QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: b524e9a37f778243cdf25255461f7f6607051264
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354271"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="25f76-102">Procedura: Animare a una rotazione tridimensionale utilizzando i fotogrammi chiave (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="25f76-102">How to: Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="25f76-103">Nell'esempio seguente, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> viene utilizzato per far ruotare un oggetto 3D.</span><span class="sxs-lookup"><span data-stu-id="25f76-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="25f76-104">Questa animazione Usa i fotogrammi chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="25f76-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="25f76-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> Consente di creare un'interpolazione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="25f76-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="25f76-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> Consente di creare "improvvisi" tra due valori (nessuna interpolazione).</span><span class="sxs-lookup"><span data-stu-id="25f76-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="25f76-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> è possibile creare una transizione variabile tra i valori a seconda di <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="25f76-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="25f76-108">Nell'esempio seguente, questa parte dell'animazione viene avviato lentamente ma verso la fine dell'intervallo di tempo, accelera in modo esponenziale.</span><span class="sxs-lookup"><span data-stu-id="25f76-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25f76-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="25f76-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="25f76-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25f76-110">See also</span></span>
- [<span data-ttu-id="25f76-111">Animare una rotazione tridimensionale usando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="25f76-111">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="25f76-112">Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="25f76-112">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="25f76-113">Aggiungere un'animazione a una rotazione tridimensionale usando quaternioni</span><span class="sxs-lookup"><span data-stu-id="25f76-113">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="25f76-114">Animare a una rotazione tridimensionale usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="25f76-114">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="25f76-115">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="25f76-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="25f76-116">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="25f76-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
