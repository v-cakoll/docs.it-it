---
title: 'Procedura: animare la posizione e la direzione di una fotocamera tramite fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112167"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="aa8e7-102">Procedura: animare la posizione e la direzione di una fotocamera tramite fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="aa8e7-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="aa8e7-103">Nell'esempio seguente, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> viene utilizzato per <xref:System.Windows.Media.Media3D.PerspectiveCamera> animare la posizione di un in una scena 3D.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="aa8e7-104">Inoltre, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> viene utilizzato per animare la direzione in cui la videocamera punta nella scena 3D.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="aa8e7-105">Entrambe queste animazioni utilizzano diversi fotogrammi chiave che creano una serie di effetti di animazione:</span><span class="sxs-lookup"><span data-stu-id="aa8e7-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <span data-ttu-id="aa8e7-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>e <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> vengono utilizzati per creare un'interpolazione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="aa8e7-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>e <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> vengono utilizzati per creare improvvisi "salti" tra i valori (nessuna interpolazione).</span><span class="sxs-lookup"><span data-stu-id="aa8e7-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="aa8e7-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>e <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> vengono utilizzati per creare una <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> transizione variabile tra i valori a seconda della proprietà.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="aa8e7-109">Nell'esempio seguente, l'animazione inizia lentamente ma verso la fine del segmento di tempo, accelera in modo esponenziale.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa8e7-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa8e7-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="aa8e7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa8e7-111">See also</span></span>

- [<span data-ttu-id="aa8e7-112">Animare la posizione e la direzione di una fotocamera in una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="aa8e7-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="aa8e7-113">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="aa8e7-113">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
