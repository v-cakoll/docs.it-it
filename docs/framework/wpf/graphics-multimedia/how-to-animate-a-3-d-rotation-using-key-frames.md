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
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a>Procedura: Animare una rotazione 3D utilizzando i fotogrammi chiave
Nell'esempio seguente, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> viene utilizzato per far ruotare un oggetto 3D mentre l'asse di rotazione consente di animare generando un "oscillazione". Questa animazione Usa i fotogrammi chiave seguenti:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> Consente di creare un'interpolazione lineare uniforme tra i valori.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> Consente di creare "improvvisi" tra due valori (nessuna interpolazione).  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> è possibile creare una transizione variabile tra i valori a seconda di <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> proprietà. Nell'esempio seguente, questa parte dell'animazione viene avviato lentamente ma verso la fine dell'intervallo di tempo, accelera in modo esponenziale.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica sulla grafica tridimensionale](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [Animare una rotazione tridimensionale usando gli storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Aggiungere un'animazione a una rotazione tridimensionale usando quaternioni](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animare a una rotazione tridimensionale usando i fotogrammi chiave (QuaternionAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
