---
title: 'Procedura: Animare la posizione e la direzione di una fotocamera in una scena tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 459b668c134e31afe295dd311094ac9cf84d884a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374024"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>Procedura: Animare la posizione e la direzione di una fotocamera in una scena tridimensionale
Nell'esempio seguente viene illustrato come animare la posizione della fotocamera e la direzione in cui che fa riferimento in una scena 3D. Questa operazione viene eseguita tramite <xref:System.Windows.Media.Animation.Point3DAnimation> e <xref:System.Windows.Media.Animation.Vector3DAnimation> animare il <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> e <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> rispettivamente del <xref:System.Windows.Media.Media3D.PerspectiveCamera>. Si potrebbe usare un'animazione simile al seguente per modificare la visualizzazione del spettatore di una scena in risposta a un evento.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [Animare la posizione e la direzione di una fotocamera usando i fotogrammi chiave](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [Panoramica sulla grafica tridimensionale](3-d-graphics-overview.md)
