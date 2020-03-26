---
title: 'Procedura: animare le proprietà dei materiali in una scena 3DHow to: Animate Material Properties in a 3D Scene'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112193"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a>Procedura: animare le proprietà dei materiali in una scena 3DHow to: Animate Material Properties in a 3D Scene
In questo esempio viene <xref:System.Windows.Media.Brush.Opacity%2A> illustrato <xref:System.Windows.Media.Media3D.Material> come animare la proprietà dell'oggetto applicato a un modello 3D.  
  
 Nell'esempio di codice <xref:System.Windows.Media.LinearGradientBrush> riportato <xref:System.Windows.Media.Media3D.Material> di seguito viene definito l'oggetto utilizzato come applicato all'oggetto 3D.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 La <xref:System.Windows.Media.Brush.Opacity%2A> proprietà <xref:System.Windows.Media.LinearGradientBrush> di questo viene animata utilizzando l'esempio di codice riportato di seguito.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
