---
title: "Procedura: Aggiungere un'animazione alle conversioni tridimensionali"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 3e27c2d5f0cd44235a1d897b1b8f057808ae6bd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762202"
---
# <a name="how-to-animate-3-d-translations"></a>Procedura: Aggiungere un'animazione alle conversioni tridimensionali
In questo argomento viene illustrato come aggiungere un'animazione a una trasformazione di traslazione impostata su un [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modello.  
  
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
