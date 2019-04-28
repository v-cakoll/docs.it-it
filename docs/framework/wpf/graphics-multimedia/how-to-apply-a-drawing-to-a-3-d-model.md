---
title: 'Procedura: Applicare un disegno a un modello tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: a20b89a7359fc85d9790ac02dd2b173452df8c22
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699110"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Procedura: Applicare un disegno a un modello tridimensionale
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.DrawingBrush> come il <xref:System.Windows.Media.Media3D.Material> applicati a un [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modello.  
  
 Il codice seguente definisce una <xref:System.Windows.Media.DrawingGroup> come contenuto di un <xref:System.Windows.Media.DrawingBrush>.  Il <xref:System.Windows.Media.DrawingBrush> viene impostata come la <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> proprietà delle <xref:System.Windows.Media.Media3D.DiffuseMaterial> applicato a un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] piano.  
  
 **Nota:** È spesso consigliabile definire gli oggetti complessi e valori, ad esempio il disegno sotto come le risorse che possono essere riutilizzate e semplificano il codice. Visualizzare [risorse XAML](../advanced/xaml-resources.md) per altre informazioni.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'intero esempio.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../advanced/xaml-resources.md)
- [Creare una scena tridimensionale](how-to-create-a-3-d-scene.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Panoramica sulla grafica tridimensionale](3-d-graphics-overview.md)
