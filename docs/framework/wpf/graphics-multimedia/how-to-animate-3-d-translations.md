---
title: 'Procedura: animare le traduzioni 3DHow to: Animate 3D Translations'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112258"
---
# <a name="how-to-animate-3d-translations"></a>Procedura: animare le traduzioni 3DHow to: Animate 3D Translations
In questo argomento viene illustrato come animare un set di trasformazioni di traslazione in un modello 3D.  
  
 Nel codice riportato di <xref:System.Windows.Media.Media3D.TranslateTransform3D> seguito <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> viene illustrata l'applicazione di un oggetto alla proprietà di un <xref:System.Windows.Media.Media3D.GeometryModel3D>oggetto .  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 La <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> proprietà <xref:System.Windows.Media.Media3D.TranslateTransform3D> di questo oggetto viene animata utilizzando il codice riportato di seguito.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
