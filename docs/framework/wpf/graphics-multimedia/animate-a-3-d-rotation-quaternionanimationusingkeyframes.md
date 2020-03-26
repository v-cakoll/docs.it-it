---
title: 'Procedura: animare una rotazione 3D usando fotogrammi chiave (QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112297"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="b4bce-102">Procedura: animare una rotazione 3D usando fotogrammi chiave (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="b4bce-102">How to: Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="b4bce-103">Nell'esempio seguente, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> viene utilizzato per far ruotare un oggetto 3D.</span><span class="sxs-lookup"><span data-stu-id="b4bce-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="b4bce-104">Questa animazione utilizza i seguenti fotogrammi chiave:</span><span class="sxs-lookup"><span data-stu-id="b4bce-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="b4bce-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>viene utilizzato per creare un'interpolazione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="b4bce-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="b4bce-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>viene utilizzato per creare improvvisi "salti" tra i valori (nessuna interpolazione).</span><span class="sxs-lookup"><span data-stu-id="b4bce-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="b4bce-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>viene utilizzato per creare una transizione <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> variabile tra i valori a seconda della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b4bce-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="b4bce-108">Nell'esempio seguente, questa parte dell'animazione inizia lentamente ma verso la fine del segmento di tempo, accelera in modo esponenziale.</span><span class="sxs-lookup"><span data-stu-id="b4bce-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4bce-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4bce-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b4bce-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4bce-110">See also</span></span>

- [<span data-ttu-id="b4bce-111">Animare una rotazione 3D usando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="b4bce-111">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="b4bce-112">Animare una rotazione 3D usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="b4bce-112">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="b4bce-113">Animare una rotazione 3D usando i quaternioni</span><span class="sxs-lookup"><span data-stu-id="b4bce-113">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="b4bce-114">Animare una rotazione 3D usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="b4bce-114">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="b4bce-115">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="b4bce-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="b4bce-116">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="b4bce-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
