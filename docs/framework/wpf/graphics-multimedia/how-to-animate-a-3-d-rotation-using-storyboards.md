---
title: 'Procedura: Animare una rotazione tridimensionale utilizzando gli storyboard'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 0e5e0b4e2b991b15ff7a49da65bfe96485e66fcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589805"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Procedura: Animare una rotazione tridimensionale utilizzando gli storyboard
Nell'esempio seguente viene illustrato come far ruotare un oggetto 3D mentre "asse" animando la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> e <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> delle proprietà di un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto. Ciò <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto specifica la trasformazione di rotazione dell'oggetto 3D e l'animazione delle proprietà consente l'effetto di rotazione desiderato. All'interno dello Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> viene usato per animare la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> proprietà durante <xref:System.Windows.Media.Animation.Vector3DAnimation> viene usato per animare il <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- [Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animare a una rotazione tridimensionale usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Panoramica sulla grafica tridimensionale](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
