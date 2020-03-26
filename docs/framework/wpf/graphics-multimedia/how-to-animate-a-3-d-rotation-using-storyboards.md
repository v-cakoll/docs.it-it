---
title: 'Procedura: animare una rotazione 3D tramite storyboardHow to: Animate a 3D Rotation Using Storyboards'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112214"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a>Procedura: animare una rotazione 3D tramite storyboardHow to: Animate a 3D Rotation Using Storyboards
L'esempio seguente mostra come far ruotare un oggetto 3D mentre <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> "oscilla" animando le proprietà e <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> di un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto. Questo <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto specifica la trasformazione di rotazione dell'oggetto 3D e pertanto l'animazione delle relative proprietà crea l'effetto di rotazione desiderato. All'interno <xref:System.Windows.Media.Animation.DoubleAnimation> di Storyboard, <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> viene <xref:System.Windows.Media.Animation.Vector3DAnimation> utilizzato per animare la proprietà while viene utilizzato per animare la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Animare una rotazione 3D usando Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animare una rotazione 3D usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
