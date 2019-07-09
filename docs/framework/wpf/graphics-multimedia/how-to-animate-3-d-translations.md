---
title: "Procedura: Aggiungere un'animazione alle conversioni tridimensionali"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 6d7e0b422d6e76d5d0e25ad276550613f264e9bc
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661194"
---
# <a name="how-to-animate-3-d-translations"></a>Procedura: Aggiungere un'animazione alle conversioni tridimensionali
In questo argomento viene illustrato come aggiungere un'animazione a una trasformazione di traslazione impostato su un modello 3D.  
  
 Il codice seguente viene illustrata l'applicazione di un <xref:System.Windows.Media.Media3D.TranslateTransform3D> dell'oggetto per il <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> proprietà di un <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 Il <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> proprietà di questo oggetto <xref:System.Windows.Media.Media3D.TranslateTransform3D> oggetto animato usando il codice seguente.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Creare una scena tridimensionale](how-to-create-a-3-d-scene.md)
- [Panoramica sulla grafica tridimensionale](3-d-graphics-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
