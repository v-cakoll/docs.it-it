---
title: "Procedura: Aggiungere un'animazione a una rotazione tridimensionale usando quaternioni"
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: d994ac2ae67fd366f27f123d5bd15f14d5ac7abe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762124"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a>Procedura: Aggiungere un'animazione a una rotazione tridimensionale usando quaternioni
In questo esempio illustra come animare una rotazione di un oggetto 3D tramite quaternioni.  
  
 Il codice seguente mostra una <xref:System.Windows.Media.Media3D.QuaternionRotation3D> utilizzato come valore per il <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> proprietà di un <xref:System.Windows.Media.Media3D.RotateTransform3D>.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 Ciò <xref:System.Windows.Media.Media3D.QuaternionRotation3D> viene aggiunta un'animazione con una <xref:System.Windows.Media.Animation.QuaternionAnimation> all'interno di un <xref:System.Windows.Media.Animation.Storyboard> usando il codice seguente.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Creare una scena tridimensionale](how-to-create-a-3-d-scene.md)
- [Panoramica sulla grafica tridimensionale](3-d-graphics-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Animare una rotazione tridimensionale usando gli storyboard](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
