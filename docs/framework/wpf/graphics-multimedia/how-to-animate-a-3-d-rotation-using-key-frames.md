---
title: 'Procedura: animare una rotazione 3D utilizzando fotogrammi chiaveHow to: Animate a 3D Rotation Using Key Frames'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112310"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a>Procedura: animare una rotazione 3D utilizzando fotogrammi chiaveHow to: Animate a 3D Rotation Using Key Frames
Nell'esempio seguente, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> viene utilizzato per far ruotare un oggetto 3D mentre il relativo asse di rotazione viene animato generando un "wobble". Questa animazione utilizza i seguenti fotogrammi chiave:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>viene utilizzato per creare un'interpolazione lineare uniforme tra i valori.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>viene utilizzato per creare improvvisi "salti" tra i valori (nessuna interpolazione).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>viene utilizzato per creare una transizione <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> variabile tra i valori a seconda della proprietà. Nell'esempio seguente, questa parte dell'animazione inizia lentamente ma verso la fine del segmento di tempo, accelera in modo esponenziale.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Animare una rotazione 3D usando gli storyboard](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animare una rotazione 3D usando Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animare una rotazione 3D usando i quaternioni](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animare una rotazione 3D usando i fotogrammi chiave (QuaternionAnimationUsingKeyFrames)](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
