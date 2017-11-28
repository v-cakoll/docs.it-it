---
title: 'Procedura: animare rotazioni tridimensionali tramite storyboard'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 56839dfc5382f5dd56ec0b26d4aabe42536bf04e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Procedura: animare rotazioni tridimensionali tramite storyboard
Nell'esempio seguente viene illustrato come far ruotare che "oscilla" aggiungendo un'animazione un oggetto 3D il <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> e <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> le proprietà di un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto. Questo <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto specifica la trasformazione di rotazione dell'oggetto 3D, l'animazione delle relative proprietà consente l'effetto di rotazione desiderato. All'interno dello Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> viene utilizzato per animare la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> proprietà durante <xref:System.Windows.Media.Animation.Vector3DAnimation> viene utilizzato per animare la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [Animare a una rotazione tridimensionale usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [Panoramica sulla grafica tridimensionale](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
