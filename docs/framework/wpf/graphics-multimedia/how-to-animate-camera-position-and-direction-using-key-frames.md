---
title: 'Procedura: Animare la posizione e la direzione di una fotocamera utilizzando i fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 5df3a201eaae4ddcf2e5d5aac3de6e0d5013947c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353400"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="0bc34-102">Procedura: Animare la posizione e la direzione di una fotocamera utilizzando i fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="0bc34-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="0bc34-103">Nell'esempio riportato di seguito <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> consente di animare la posizione di un <xref:System.Windows.Media.Media3D.PerspectiveCamera> in una scena 3D.</span><span class="sxs-lookup"><span data-stu-id="0bc34-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="0bc34-104">Inoltre, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> viene usato per animare la direzione della fotocamera fa riferimento nella scena 3D.</span><span class="sxs-lookup"><span data-stu-id="0bc34-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="0bc34-105">Entrambe queste animazioni usare molti fotogrammi chiave che crea una serie di effetti di animazione:</span><span class="sxs-lookup"><span data-stu-id="0bc34-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1.  <span data-ttu-id="0bc34-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> e <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> vengono usati per creare un'interpolazione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="0bc34-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="0bc34-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> e <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> vengono usati per creare "improvvisi" tra due valori (nessuna interpolazione).</span><span class="sxs-lookup"><span data-stu-id="0bc34-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="0bc34-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> e <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> vengono usati per creare una transizione variabile tra i valori a seconda di <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0bc34-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="0bc34-109">Nell'esempio seguente, l'animazione inizia lentamente ma verso la fine dell'intervallo di tempo, accelera in modo esponenziale.</span><span class="sxs-lookup"><span data-stu-id="0bc34-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bc34-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="0bc34-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0bc34-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bc34-111">See also</span></span>
- [<span data-ttu-id="0bc34-112">Animare la posizione e la direzione di una fotocamera in una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="0bc34-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="0bc34-113">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="0bc34-113">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
