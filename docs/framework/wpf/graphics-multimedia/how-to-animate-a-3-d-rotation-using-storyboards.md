---
title: "Procedura: Aggiungere un'animazione a una rotazione tridimensionale usando gli storyboard"
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 03b01205f1a31426a01b09533b350682c384df4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146198"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Procedura: Aggiungere un'animazione a una rotazione tridimensionale usando gli storyboard
Nell'esempio seguente viene illustrato come far ruotare un oggetto 3D mentre "asse" animando la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> e <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> delle proprietà di un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto. Ciò <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto specifica la trasformazione di rotazione dell'oggetto 3D e l'animazione delle proprietà consente l'effetto di rotazione desiderato. All'interno dello Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> viene usato per animare la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> proprietà durante <xref:System.Windows.Media.Animation.Vector3DAnimation> viene usato per animare il <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Aggiungere un'animazione a una rotazione tridimensionale usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Cenni preliminari sulla grafica tridimensionale](3-d-graphics-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
