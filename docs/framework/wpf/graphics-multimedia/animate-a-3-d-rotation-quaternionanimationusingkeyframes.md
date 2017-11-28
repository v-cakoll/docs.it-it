---
title: 'Procedura: animare una rotazione tridimensionale tramite i fotogrammi chiave (QuaternionAnimationUsingKeyFrames)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61968c13d395187d1190c7a2eaaa2bfe3f6072e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>Procedura: animare una rotazione tridimensionale tramite i fotogrammi chiave (QuaternionAnimationUsingKeyFrames)
Nell'esempio seguente, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> viene utilizzato per far ruotare un oggetto 3D. Questa animazione utilizza i fotogrammi chiave seguenti:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>viene utilizzato per creare un'interpolazione lineare uniforme tra i valori.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>viene utilizzato per creare "improvvisi" tra due valori (nessuna interpolazione).  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>è possibile creare una transizione tra i valori in base alle variabile di <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> proprietà. Nell'esempio seguente, questa parte dell'animazione viene avviato lentamente, ma verso la fine dell'intervallo di tempo, consente di velocizzare in modo esponenziale.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Animare una rotazione tridimensionale usando gli storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [Aggiungere un'animazione a una rotazione tridimensionale usando quaternioni](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [Animare a una rotazione tridimensionale usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [Panoramica sulla grafica tridimensionale](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
