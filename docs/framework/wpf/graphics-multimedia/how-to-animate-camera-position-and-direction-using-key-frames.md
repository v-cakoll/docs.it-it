---
title: 'Procedura: animare la posizione e la direzione di una fotocamera tramite fotogrammi chiave'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dbac99770b5cbb7dacb0468e1a892956fda6b79c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="803e8-102">Procedura: animare la posizione e la direzione di una fotocamera tramite fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="803e8-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="803e8-103">Nell'esempio seguente, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> viene utilizzato per animare la posizione di un <xref:System.Windows.Media.Media3D.PerspectiveCamera> in una scena 3D.</span><span class="sxs-lookup"><span data-stu-id="803e8-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="803e8-104">Inoltre, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> viene utilizzato per animare la direzione in cui punta la camera nella scena 3D.</span><span class="sxs-lookup"><span data-stu-id="803e8-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="803e8-105">Entrambe le animazioni utilizzare molti fotogrammi chiave che crea una serie di effetti di animazione:</span><span class="sxs-lookup"><span data-stu-id="803e8-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1.  <span data-ttu-id="803e8-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>e <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> vengono utilizzati per creare un'interpolazione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="803e8-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="803e8-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>e <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> consentono di creare "improvvisi" tra due valori (nessuna interpolazione).</span><span class="sxs-lookup"><span data-stu-id="803e8-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="803e8-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>e <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> vengono utilizzati per creare una transizione tra i valori in base alle variabile di <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="803e8-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="803e8-109">Nell'esempio seguente, l'animazione viene avviato lentamente, ma verso la fine dell'intervallo di tempo, consente di velocizzare in modo esponenziale.</span><span class="sxs-lookup"><span data-stu-id="803e8-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="803e8-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="803e8-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="803e8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="803e8-111">See Also</span></span>  
 [<span data-ttu-id="803e8-112">Animare la posizione e la direzione di una fotocamera in una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="803e8-112">Animate Camera Position and Direction in a 3D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)  
 [<span data-ttu-id="803e8-113">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="803e8-113">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
