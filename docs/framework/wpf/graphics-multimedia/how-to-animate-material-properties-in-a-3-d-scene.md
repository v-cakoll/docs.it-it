---
title: 'Procedura: animare proprietà materiali in una scena tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: ed4bbb3b22b09c24ed40b72a483db38b35038759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a>Procedura: animare proprietà materiali in una scena tridimensionale
In questo esempio viene illustrato come animare la <xref:System.Windows.Media.Brush.Opacity%2A> proprietà del <xref:System.Windows.Media.Media3D.Material> applicato a un [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modello.  
  
 L'esempio di codice seguente definisce il <xref:System.Windows.Media.LinearGradientBrush> utilizzato come il <xref:System.Windows.Media.Media3D.Material> applicato all'oggetto 3D.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 Il <xref:System.Windows.Media.Brush.Opacity%2A> proprietà di questo <xref:System.Windows.Media.LinearGradientBrush> utilizzando l'esempio di codice riportato di seguito.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato l'esempio completo.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Creare una scena tridimensionale](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [Panoramica sulla grafica tridimensionale](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
