---
title: "Procedura: Aggiungere un'animazione alla posizione e alla direzione di una fotocamera usando i fotogrammi chiave"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 3be3fc8d82d9c3061891bd67605548c49230ef87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143234"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Procedura: Aggiungere un'animazione alla posizione e alla direzione di una fotocamera usando i fotogrammi chiave
Nell'esempio riportato di seguito <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> consente di animare la posizione di un <xref:System.Windows.Media.Media3D.PerspectiveCamera> in una scena 3D. Inoltre, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> viene usato per animare la direzione della fotocamera fa riferimento nella scena 3D. Entrambe queste animazioni usare molti fotogrammi chiave che crea una serie di effetti di animazione:  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> e <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> vengono usati per creare un'interpolazione lineare uniforme tra i valori.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> e <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> vengono usati per creare "improvvisi" tra due valori (nessuna interpolazione).  
  
3.  <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> e <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> vengono usati per creare una transizione variabile tra i valori a seconda di <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> proprietà. Nell'esempio seguente, l'animazione inizia lentamente ma verso la fine dell'intervallo di tempo, accelera in modo esponenziale.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Aggiungere un'animazione alla posizione e alla direzione di una fotocamera in una scena tridimensionale](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [Cenni preliminari sulla grafica tridimensionale](3-d-graphics-overview.md)
