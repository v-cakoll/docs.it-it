---
title: 'Procedura: Applicare un disegno a un modello tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 8ac24fdf8d7e407e10764c17fcc12121aa5f51d7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662808"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Procedura: Applicare un disegno a un modello tridimensionale
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.DrawingBrush> come il <xref:System.Windows.Media.Media3D.Material> applicato a un modello 3D.  
  
 Il codice seguente definisce una <xref:System.Windows.Media.DrawingGroup> come contenuto di un <xref:System.Windows.Media.DrawingBrush>.  Il <xref:System.Windows.Media.DrawingBrush> viene impostato come i <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> proprietà del <xref:System.Windows.Media.Media3D.DiffuseMaterial> applicata a un piano 3D.  
  
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
