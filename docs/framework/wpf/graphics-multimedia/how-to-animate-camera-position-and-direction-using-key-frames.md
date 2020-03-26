---
title: 'Procedura: animare la posizione e la direzione di una fotocamera tramite fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112167"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Procedura: animare la posizione e la direzione di una fotocamera tramite fotogrammi chiave
Nell'esempio seguente, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> viene utilizzato per <xref:System.Windows.Media.Media3D.PerspectiveCamera> animare la posizione di un in una scena 3D. Inoltre, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> viene utilizzato per animare la direzione in cui la videocamera punta nella scena 3D. Entrambe queste animazioni utilizzano diversi fotogrammi chiave che creano una serie di effetti di animazione:  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>e <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> vengono utilizzati per creare un'interpolazione lineare uniforme tra i valori.  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>e <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> vengono utilizzati per creare improvvisi "salti" tra i valori (nessuna interpolazione).  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>e <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> vengono utilizzati per creare una <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> transizione variabile tra i valori a seconda della proprietà. Nell'esempio seguente, l'animazione inizia lentamente ma verso la fine del segmento di tempo, accelera in modo esponenziale.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Animare la posizione e la direzione di una fotocamera in una scena tridimensionale](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
