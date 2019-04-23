---
title: 'Procedura: Applicare un oggetto Material alle parti anteriore e posteriore di un oggetto tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 1d3f6a0622b5e0ccccf14af99782bb78dfe87ccb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168051"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a>Procedura: Applicare un oggetto Material alle parti anteriore e posteriore di un oggetto tridimensionale
Nell'esempio seguente viene illustrato come applicare un <xref:System.Windows.Media.Media3D.Material> nella parte anteriore e posteriore di un oggetto 3D dell'oggetto e animare l'oggetto in modo da visualizzare entrambi i lati dell'oggetto. Il <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di un <xref:System.Windows.Media.Media3D.GeometryModel3D> viene usato per applicare una linea rossa <xref:System.Windows.Media.Brush> per il lato anteriore di oggetto e il <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> proprietà del <xref:System.Windows.Media.Media3D.GeometryModel3D> viene usato per applicare un blu <xref:System.Windows.Media.Brush> per il lato posteriore dell'oggetto. Il codice seguente viene illustrata l'applicazione dei materiali all'oggetto:  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Creare una scena tridimensionale](how-to-create-a-3-d-scene.md)
- [Panoramica sulla grafica tridimensionale](3-d-graphics-overview.md)
- [Animare le proprietà Material in una scena tridimensionale](how-to-animate-material-properties-in-a-3-d-scene.md)
- [Applicare materiale con componente emissiva a un oggetto tridimensionale](how-to-apply-emissive-material-to-a-3-d-object.md)
