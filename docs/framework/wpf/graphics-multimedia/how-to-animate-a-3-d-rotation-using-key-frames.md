---
title: 'Procedura: Animare una rotazione 3D utilizzando i fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 129b672411edf03dc5b98d1568c49704e66bea25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663635"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="8788c-102">Procedura: Animare una rotazione 3D utilizzando i fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="8788c-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="8788c-103">Nell'esempio seguente, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> viene utilizzato per far ruotare un oggetto 3D mentre l'asse di rotazione consente di animare generando un "oscillazione".</span><span class="sxs-lookup"><span data-stu-id="8788c-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="8788c-104">Questa animazione Usa i fotogrammi chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="8788c-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="8788c-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> Consente di creare un'interpolazione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="8788c-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="8788c-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> Consente di creare "improvvisi" tra due valori (nessuna interpolazione).</span><span class="sxs-lookup"><span data-stu-id="8788c-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="8788c-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> è possibile creare una transizione variabile tra i valori a seconda di <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="8788c-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="8788c-108">Nell'esempio seguente, questa parte dell'animazione viene avviato lentamente ma verso la fine dell'intervallo di tempo, accelera in modo esponenziale.</span><span class="sxs-lookup"><span data-stu-id="8788c-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8788c-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8788c-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8788c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8788c-110">See also</span></span>
- [<span data-ttu-id="8788c-111">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="8788c-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="8788c-112">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="8788c-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="8788c-113">Animare una rotazione tridimensionale usando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="8788c-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="8788c-114">Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="8788c-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="8788c-115">Aggiungere un'animazione a una rotazione tridimensionale usando quaternioni</span><span class="sxs-lookup"><span data-stu-id="8788c-115">Animate a 3-D Rotation Using Quaternions</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="8788c-116">Animare a una rotazione tridimensionale usando i fotogrammi chiave (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="8788c-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
