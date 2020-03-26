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
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>Procedura: animare una rotazione 3D usando fotogrammi chiave (QuaternionAnimationUsingKeyFrames)
Nell'esempio seguente, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> viene utilizzato per far ruotare un oggetto 3D. Questa animazione utilizza i seguenti fotogrammi chiave:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>viene utilizzato per creare un'interpolazione lineare uniforme tra i valori.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>viene utilizzato per creare improvvisi "salti" tra i valori (nessuna interpolazione).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>viene utilizzato per creare una transizione <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> variabile tra i valori a seconda della proprietà. Nell'esempio seguente, questa parte dell'animazione inizia lentamente ma verso la fine del segmento di tempo, accelera in modo esponenziale.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Animare una rotazione 3D usando gli storyboard](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animare una rotazione 3D usando Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animare una rotazione 3D usando i quaternioni](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animare una rotazione 3D usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
