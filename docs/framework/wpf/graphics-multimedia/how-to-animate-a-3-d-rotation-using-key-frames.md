---
title: 'Procedura: animare una rotazione tridimensionale tramite fotogrammi chiave'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8dad8934dacd64f31cf65d7517d8c48114522505
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="a0392-102">Procedura: animare una rotazione tridimensionale tramite fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="a0392-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="a0392-103">Nell'esempio seguente, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> viene utilizzato per far ruotare un oggetto 3D mentre l'asse di rotazione aggiunge un'animazione generando un'oscillazione"".</span><span class="sxs-lookup"><span data-stu-id="a0392-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="a0392-104">Questa animazione utilizza i fotogrammi chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0392-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="a0392-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>viene utilizzato per creare un'interpolazione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="a0392-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="a0392-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>viene utilizzato per creare "improvvisi" tra due valori (nessuna interpolazione).</span><span class="sxs-lookup"><span data-stu-id="a0392-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="a0392-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>è possibile creare una transizione tra i valori in base alle variabile di <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a0392-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="a0392-108">Nell'esempio seguente, questa parte dell'animazione viene avviato lentamente, ma verso la fine dell'intervallo di tempo, consente di velocizzare in modo esponenziale.</span><span class="sxs-lookup"><span data-stu-id="a0392-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0392-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0392-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a0392-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0392-110">See Also</span></span>  
 [<span data-ttu-id="a0392-111">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="a0392-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="a0392-112">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="a0392-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="a0392-113">Animare una rotazione tridimensionale usando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="a0392-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="a0392-114">Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="a0392-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="a0392-115">Aggiungere un'animazione a una rotazione tridimensionale usando quaternioni</span><span class="sxs-lookup"><span data-stu-id="a0392-115">Animate a 3-D Rotation Using Quaternions</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [<span data-ttu-id="a0392-116">Animare a una rotazione tridimensionale usando i fotogrammi chiave (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="a0392-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
