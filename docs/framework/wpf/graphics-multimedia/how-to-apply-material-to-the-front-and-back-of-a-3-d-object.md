---
title: 'Procedura: applicare materiale alla parte anteriore e posteriore di un oggetto 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112141"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a>Procedura: applicare materiale alla parte anteriore e posteriore di un oggetto 3D
Nell'esempio seguente viene <xref:System.Windows.Media.Media3D.Material> illustrato come applicare a alla parte anteriore e posteriore di un oggetto 3D e animare l'oggetto per visualizzare entrambi i lati dell'oggetto. La <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà <xref:System.Windows.Media.Media3D.GeometryModel3D> di un oggetto <xref:System.Windows.Media.Brush> viene utilizzata per applicare un <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> rosso <xref:System.Windows.Media.Media3D.GeometryModel3D> sul lato anteriore dell'oggetto e la proprietà dell'oggetto viene utilizzata per applicare un blu <xref:System.Windows.Media.Brush> sul lato posteriore dell'oggetto. Il codice seguente mostra l'applicazione dei materiali all'oggetto:  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Animare le proprietà Material in una scena 3D](how-to-animate-material-properties-in-a-3-d-scene.md)
- [Applicare EmissiveMaterial a un oggetto 3D](how-to-apply-emissive-material-to-a-3-d-object.md)
